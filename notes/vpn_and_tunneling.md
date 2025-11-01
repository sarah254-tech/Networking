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

