# ☁️ Cloud Networking Fundamentals

Cloud networking brings traditional networking concepts into cloud environments — like AWS, Azure, and GCP — but with virtualized components instead of physical routers and switches.

> The cloud is just someone else's computer, but with **virtual networking superpowers**.

Cloud networking is a **must-know** for DevOps, SRE, and Cloud Engineers.

---

## 🏗️ Key Building Blocks

| Concept | Meaning | Example |
|---|---|---|
VPC | Virtual network in the cloud | Virtual private data center |
Subnets | Network segments inside VPC | Public & private subnets |
Routing Table | Defines traffic paths | Internet traffic vs internal |
Internet Gateway (IGW) | Allows VPC ↔ Internet communication | Public web servers |
NAT Gateway | Private devices go to internet | Updates servers without exposing them |
Security Groups | Virtual firewalls for EC2 | Allow/deny traffic by port/protocol |
Network ACL (NACL) | Subnet-level traffic control | Extra layer of firewalling |
Load Balancer | Distributes traffic | ALB, NLB |
VPN | Secure private network connection to cloud | Office ↔ VPC |
VPC Peering | Connect two VPCs | Multi-VPC architecture |
Transit Gateway | Hub for many VPCs | Enterprise cloud networks |
DNS Service | Domain name resolution | Route 53 / Cloud DNS |

---

## 🧠 Cloud vs Traditional Networking

| Traditional | Cloud Equivalent |
|---|---|
Physical data center | VPC |
Router | VPC Routing Table |
Firewall | Security Group / NACL |
Switch | Subnet / virtual switching |
Public Internet modem | Internet Gateway |
NAT Box | NAT Gateway |
Corporate leased line | VPN / Direct Connect |

The rules of networking still apply — **just virtualized and scalable**.

---

## 🔥 Public vs Private Subnets

| Type | Purpose | Example |
|---|---|---|
Public Subnet | Accessible from the Internet | Web server EC2 |
Private Subnet | Internal access only | Databases, backend apps |

> **Best practice:** Never put databases in public subnets.

---

## 🧭 Route Tables

Contain routing rules for subnets.

Simple example:

| Destination | Target |
|---|---|
0.0.0.0/0 | Internet Gateway |
10.0.0.0/16 | Local VPC Traffic |

---

## 🛡️ Security: SG vs NACL

### 🔐 Security Groups (Stateful)

- Instance-level firewall
- Returns traffic is automatically allowed
- Used 99 percent of the time

Example:

| Type | Port | Source |
|---|---|---|
Allow | 22 | My IP |
Allow | 80 | Anywhere |

---

### 🧱 NACLs (Stateless)

- Subnet-level firewall
- Explicit allow and deny rules
- Rarely modified

Example:

| Rule | Action | Port | Source |
|---|---|---|---|
100 | Allow | 80 | 0.0.0.0/0 |
200 | Deny | All | 0.0.0.0/0 |

> If AWS were a house, **Security Group = door lock**, **NACL = fence**.

---

## 🌍 DNS in Cloud

Managed DNS replaces self-hosted DNS servers.

| Cloud Provider | DNS Service |
|---|---|
AWS | Route 53 |
Azure | Azure DNS |
GCP | Cloud DNS |

Features:

- Domain resolution
- Routing policies (geo, latency, failover)
- Health checks

---

## 🌐 Internet Gateway vs NAT Gateway

| Feature | Internet Gateway | NAT Gateway |
|---|---|---|
Traffic Direction | VPC ↔ Internet | Private subnet → Internet |
Use Case | Web servers | Private servers updating packages |
Public Exposure | Yes | No |

> Shortcut memory: **IGW = Public**, **NAT = Private**

---

## 🏷️ Load Balancers

| Type | Use Case |
|---|---|
Application LB | HTTP/HTTPS (Layer 7) |
Network LB | TCP/UDP (Layer 4) |
Gateway LB | Third-party network appliance |

> Real-world: Accepts traffic and distributes across multiple servers.

---

## 🧵 VPC Connectivity Explained

| Technology | Use Case |
|---|---|
VPC Peering | Connect two VPCs one-to-one |
Transit Gateway | Connect many VPCs (hub & spoke) |
VPN | Office ↔ Cloud secure | 
Direct Connect | Dedicated fiber to cloud for enterprises |

---

## 🧪 Useful Cloud Networking Tools

| Tool | Purpose |
|---|---|
VPC Reachability Analyzer | Trace network traffic |
Flow Logs | Monitor traffic to/from ENIs |
Traceroute / MTR | Path debugging |
Telnet / nc | Port testing |
dig / nslookup | DNS debugging |

---

## 💡 Best Practices

- Use private subnets for sensitive systems
- Separate subnets for app tiers (web / app / DB)
- Enable VPC flow logs
- Restrict SSH; use VPN / SSM instead
- Never allow `0.0.0.0/0` inbound SSH in prod
- Rotate NAT/IGW usage for cost awareness

---

## 🎯 Real DevOps Scenarios

| Task | Example |
|---|---|
Deploy app to private subnet | EC2 + NAT for updates |
Troubleshoot 502 errors | ALB target health + SG rules |
VPN outage | Route table + tunnels |
DNS failing | Route 53 + dig testing |
No internet access | Missing IGW route |

---

> Cloud networking is **real networking, just invisible, scalable, and programmable.**

---

