# 🔐 VPN & Tunneling 

VPNs and tunnels let you send traffic **securely** across untrusted networks.  
For DevOps, VPNs are tools for remote admin, secure access to private cloud networks, site-to-site connectivity, and encrypted service-to-service tunnels.

In this guide, I explain the concepts, common types of tunnels, and quick debugging tips. I have also written a **step-by-step example** to set up a simple VPN server on a **Free Tier AWS EC2 instance** (OpenVPN). The EC2/OpenVPN approach is friendly for learning and low-cost (fits Free Tier when using a t2.micro/t3.micro and default VPC).

> ⚠️ Security note: do not check private keys, `.ovpn` client files, or unredacted IPs into a public repo. Mask secrets before sharing.

---

## 🚀 Quick overview — What is a VPN / Tunnel?

- **VPN (Virtual Private Network)**: a secure, encrypted connection between two endpoints over an untrusted network (usually the Internet).  
- **Tunnel**: the logical encrypted channel inside which packets travel.
- **Use cases**: remote admin to private servers, secure service traffic, site-to-site links between datacenters/VPCs, bypassing NAT/firewalls for management.

---

## 🧩 Types of VPNs & Tunnels

| Type | What it does | Common protocols / tools |
|------|--------------|--------------------------|
| **Client VPN** | Individual users connect to a private network | OpenVPN, WireGuard, AWS Client VPN |
| **Site-to-Site VPN** | Two networks (office ↔ cloud) connected securely | IPsec, AWS VPN (VGW), StrongSwan |
| **SSH Tunnel** | Single-connection port forwarding or SOCKS proxy | `ssh -L`, `ssh -R`, `ssh -D` |
| **WireGuard** | Modern lightweight VPN, fast & simple | WireGuard protocol |
| **GRE / IP-in-IP** | Generic tunneling for routing between networks | GRE (no built-in encryption) |
| **TLS-based VPN** | Uses TLS (HTTPS) for tunnel | OpenVPN in TLS mode |

---

## 🔐 How VPNs work (high level)

1. Client authenticates to VPN server (certs, username/password, OTP).  
2. A secure channel (tunnel) is created using cryptographic protocols (TLS/IPsec/WireGuard keys).  
3. The client gets an IP on the VPN network (virtual interface).  
4. Traffic destined for private networks is routed into the tunnel and encrypted.  
5. Server decrypts and forwards packets on the private network. Responses return via the same tunnel.

---

## 🧰 SSH Tunneling Cheatsheet (super useful)

- **Local forward** (access remote DB as localhost):
  ```bash
  ssh -L 5432:db.private.internal:5432 ubuntu@bastion.example.com
  # Then connect to localhost:5432 on your machine


- **Remote forward (expose local service to remote):**

    `ssh -R 8080:localhost:8080 ubuntu@remote-server`

- **Dynamic (SOCKS) proxy:**

    `ssh -D 1080 ubuntu@jump-host`
     >Configure browser to use SOCKS5 localhost:1080

SSH tunnels are great for quick admin tasks and tight troubleshooting.

---

##  Step-by-step: Set up an OpenVPN server on AWS (Free Tier friendly)

>This guide uses a small Ubuntu EC2 (t2.micro / t3.micro). It is intended for learning and small personal use. For production, harden the instance, use proper certificate management, monitoring, and autoscaling.

**Pre-requisites**

- An AWS account and basic familiarity with the console.

- You will use the default VPC (simpler).

- A SSH keypair ready or can create one in the console.

- You will use the OpenVPN install script method for speed (well-known community scripts exist). You can adapt to manual easy-rsa setup if you prefer full control.

---

### A. Create the EC2 instance (Console)

1. Open AWS Console → EC2 → Instances → Launch instances.

2. Choose an AMI: Ubuntu Server 22.04 LTS (or 20.04).

3. Instance type: t2.micro or t3.micro (Free Tier eligible).

4. Key pair: choose existing or create a new one. Download .pem and keep it safe.

5. Network settings:

    - VPC: default

    - Subnet: any (default)

    - Auto-assign Public IP: Enable (so you can SSH)

6. Configure security group:

    - Allow **SSH (TCP 22)** from your IP (restrict to your office/home IP).

    - Allow **UDP 1194** (OpenVPN default) from your IP or 0.0.0.0/0 (for testing). For production restrict by source.

    - Optionally allow **TCP 443** if you plan to run OpenVPN over TCP or need HTTPS management.

7. Launch instance.

    >Record the instance Public IPv4 (or elastic IP if you attach one later). You will SSH to this.

    ---

### B. SSH into the instance (Terminal on your machine)

`bash`
make .pem private (only once)
`chmod 400 ~/path/to/mykey.pem`

SSH into instance
`ssh -i ~/path/to/mykey.pem ubuntu@<PUBLIC_IP>`

Replace <PUBLIC_IP> with the instance public IP.

---

### C. Update the instance and install OpenVPN (Ubuntu)

`bash`
update system
`sudo apt update && sudo apt upgrade -y`

install curl (if missing)
`sudo apt install -y curl`

>We will use a widely used install script to bootstrap OpenVPN quickly. 

`bash`

download and run the openvpn-install script

`curl -O` https://raw.githubusercontent.com/Nyr/openvpn-install/master/openvpn-install.

`chmod +x openvpn-install.sh`
`sudo ./openvpn-install.sh`

The script will ask interactive questions:

    - Public IPv4 or DNS name: it can auto-detect your public IP

    - Use UDP or TCP (UDP recommended)

    - Port: 1194 default (OK)

    - DNS for clients: choose cloudflare (1.1.1.1) or Google (8.8.8.8)

    - Client name: choose a name (e.g., dev-laptop)

The script will generate:

    - Server keys and certs

    - `~/clientname.ovpn` client config file — **download this securely**.

    >If the script is not desired, You can google for the manual easy-rsa steps (longer, more explicit).

---

### D. Enable IP forwarding and NAT (if the script did not handle it)

If you used the script, it usually configures forwarding and iptables. To manually ensure:

`bash`
enable IP forwarding now
`sudo sysctl -w net.ipv4.ip_forward=1`

make permanent
`echo 'net.ipv4.ip_forward=1' | sudo tee -a /etc/sysctl.conf`

NAT - adjust eth0 if your interface name differs (ip addr show)
`sudo iptables -t nat -A POSTROUTING -s 10.8.0.0/24 -o eth0 -j MASQUERADE`

persist iptables (install netfilter-persistent)
`sudo apt install -y netfilter-persistent`
`sudo netfilter-persistent save`

`10.8.0.0/24` is the common OpenVPN client subnet. Replace if different.

---

### E. Transfer the`.ovpn` client file to your workstation

From your local machine (not instance), use `scp`:

`bash`

on your workstation
`scp -i ~/path/to/mykey.pem ubuntu@<PUBLIC_IP>:/home/ubuntu/dev-laptop.ovpn ~/Downloads/`

    > Or use `cat` then copy-paste via terminal (less convenient).

---

### F. Connect from your client

- Install an OpenVPN client on your laptop:

    - Linux: `sudo apt install openvpn` then `sudo openvpn --config dev-laptop.ovpn`

- Import the `.ovpn` and connect.

- If ping to internal IPs works, VPN is up.


---

### G. Test & Troubleshoot

- From client, ping VPN gateway, e.g. `ping 10.8.0.1.`

- Check routing: `ip route` on client to ensure traffic to private subnets is via VPN.

- On server, check OpenVPN logs: `sudo journalctl -u openvpn` or `/var/log/openvpn.log`.

- If no internet over VPN, check iptables MASQUERADE and `net.ipv4.ip_forward=1`.


---

#### 🧾 Summary (cheat sheet)

| Step                  | Command / Action                                                      |
| --------------------- | --------------------------------------------------------------------- |
| Launch EC2            | Console: Ubuntu t2.micro, add SG for SSH + UDP 1194                   |
| SSH in                | `ssh -i key.pem ubuntu@<IP>`                                          |
| Install OpenVPN       | `curl -O ...openvpn-install.sh && sudo ./openvpn-install.sh`          |
| Enable forwarding     | `sudo sysctl -w net.ipv4.ip_forward=1`                                |
| NAT                   | `iptables -t nat -A POSTROUTING -s 10.8.0.0/24 -o eth0 -j MASQUERADE` |
| Transfer client .ovpn | `scp ... ubuntu@<IP>:/home/ubuntu/`                                   |
| Connect               | OpenVPN client import `.ovpn`                                         |








