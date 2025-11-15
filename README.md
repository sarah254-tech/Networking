# Networking Study Repository

Welcome to my Networking learning repository.

## Purpose
To document foundational networking knowledge for DevOps, cloud, and automation roles.

## What you will find here:
- Basic networking concepts explained simply
- Commands practice (ping, traceroute, netstat, telnet, ssh, curl)
- Network layers and protocols
- Network troubleshooting exercises
- Labs and notes for Linux networking

## Learning Path
1. OSI Model vs TCP/IP Model
2. IP Addressing (IPv4, IPv6, Subnets)
3. Routing vs Switching
4. DNS, DHCP, NAT, VPN
5. Firewalls & Ports
6. Load Balancing
7. Network Tools & Diagnostics
8. Cloud Networking Basics (AWS VPC, Subnets, Route Tables)


# What is  Computer Networking?
Computer networking is the practice of connecting computers, servers, and devices so they can communicate, share data, and access resources like the internet, files, printers, and applications.

In simple terms, networking allows devices to talk to each other.
Without networking, there would be no internet, no emails, no cloud, and no communication between systems.

A computer network can be as small as two laptops sharing files in your home, or as large as millions of servers powering global platforms like Google, Netflix, and AWS.

## Why is networking important in DevOps
Networking is the foundation of cloud and DevOps because every application runs on a network.
In DevOps engineering, we will deal with:

- Servers communicating over networks

- Cloud networking (VPCs, subnets, route tables, gateways)

- Load balancers and firewalls

- DNS settings (domain names, records)

- Secure access (SSH, VPN, ports)

- Monitoring network traffic and connectivity

Understanding networking helps in deployment, troubleshooting, security, and scalability of applications in real environments.


# 📘 Networking Acronyms Explained (Full DevOps Edition)
Below, I have written down the most important acronyms you will meet in DevOps, Cloud, Linux administration, and networking engineering.

## 🔡 A–Z Networking Acronyms (With Full Explanations)

### 🅰️ A
**ARP** – Address Resolution Protocol

> Maps an IPv4 address → MAC address inside a local network.
Used when two devices want to communicate but only know IPs.

**ACL** – Access Control List

> Rules that allow/deny traffic on routers, firewalls, and cloud resources.
Example: AWS Security Groups, NACLs, Linux file permissions.

**AP** – Access Point

> Device that allows Wi-Fi devices to connect to a wired network.

**AS** – Autonomous System

> A group of IP networks under a single organization (e.g., ISP).
Used in internet routing (BGP).

### 🅱️ B
**BGP** – Border Gateway Protocol

> The routing protocol of the entire internet.
Decides the best path between different autonomous systems.

**BR** – Bridge

> Connects two network segments as if they were one LAN.

**BYOD** – Bring Your Own Device

> Security model allowing employees to use personal devices.

### 🅲️ C
**CIDR** – Classless Inter-Domain Routing

> Modern IP addressing system using / notation (e.g., /24, /16).
Reduces IP waste, enables subnetting & VLSM.

**CPU** – Central Processing Unit

> Not networking, but used in performance discussions (routers, switches).

**CSMA/CD** – Carrier Sense Multiple Access / Collision Detection

> Used in Ethernet before full-duplex.
Detects collisions and retransmits frames.

**CORS** – Cross-Origin Resource Sharing

> Browser security feature that controls which domains can access APIs.

### 🅳️ D
**DHCP** – Dynamic Host Configuration Protocol

> Automatically assigns IP address, gateway, subnet mask, DNS to clients.

**DNS** – Domain Name System

> Phonebook of the internet.
Maps domain name → IP address.

**DoH** – DNS over HTTPS

> Encrypts DNS queries to prevent spying or tampering.

**DoT** – DNS over TLS

> Another encrypted DNS protocol used by security-focused networks.

**DDoS** – Distributed Denial of Service

> Attack where multiple systems flood a target to take it offline.

### 🅴️ E
**EIGRP** – Enhanced Interior Gateway Routing Protocol

> Cisco proprietary routing protocol.

**ENCAP** – Encapsulation

> Wrapping data with headers as it moves down OSI layers.

**ESP** – Encapsulating Security Payload

> Part of IPsec that provides encryption and authentication.

### 🅵️ F
**FTP** – File Transfer Protocol

> Used for transferring files over a network.
Not encrypted → replaced by SFTP/FTPS.

**FQDN** – Fully Qualified Domain Name

> Complete domain name: www.example.com.
Includes hostname + domain.

### 🅶️ G
**GRE** – Generic Routing Encapsulation

> Tunneling protocol for VPNs.
Encapsulates packets into new headers to transport across networks.

**GCP** – Google Cloud Platform

> Cloud provider used in networking and DevOps pipelines.

### 🅷️ H
**HTTP** – HyperText Transfer Protocol

> Transfers web pages (GET, POST, PUT, DELETE).
Not encrypted.

**HTTPS** – HTTP Secure

> Encrypted version of HTTP using TLS.

**HMAC** – Hash-based Message Authentication Code

> Ensures integrity and authenticity of data packets.

### 🅸️ I
**ICMP** – Internet Control Message Protocol

> Used for diagnostics (e.g., ping, traceroute).
Reports errors, unreachable hosts, timeouts.

**IGMP** – Internet Group Management Protocol

> Manages multicast group memberships.

**IMAP** – Internet Message Access Protocol

Retrieves email while keeping mail on the server.

**IP** – Internet Protocol

> Provides logical addressing and routing.

**IPSec** – Internet Protocol Security

> Encrypts and authenticates IP traffic.
Used in VPNs.

**ISP** – Internet Service Provider

> Organization that provides access to the internet.

### 🅺️ K
**KVM** – Kernel-based Virtual Machine

> Used in virtualization (Linux servers, cloud hypervisors).

### 🅻️ L
**LAN** – Local Area Network

> Small network in offices, homes, data centers.

**LLC** – Logical Link Control

> Part of data-link layer responsible for error checking.

**LACP** – Link Aggregation Control Protocol

> Combines multiple physical links into one logical link for increased bandwidth.

### 🅼️ M
**MAC** – Media Access Control

> Unique hardware address assigned to network interfaces.

**MPLS** – Multi-Protocol Label Switching

> High-performance routing technique used by ISPs and large companies.

**MTU** – Maximum Transmission Unit

> Largest size of a packet that can be transmitted.

### 🅽️ N
**NAT** – Network Address Translation

> Converts private IPs to public IPs.
Used in routers & cloud networks.

**NACL** – Network Access Control List

> AWS firewall rules for subnets (stateless).

**NIC** – Network Interface Card

> Hardware that connects a device to a network.

**NTP** – Network Time Protocol

> Synchronizes clocks across devices.

### 🅾️ O
**OSPF** – Open Shortest Path First

> Fast and modern internal routing protocol.

**OSI** – Open Systems Interconnection

> 7-layer networking model used for teaching/troubleshooting.

**🅿️ P**
**PAT** – Port Address Translation

> Type of NAT that maps multiple private IPs → one public IP using ports.

**POP** – Post Office Protocol

> Downloads email to client. Deletes from server by default.

**PoE** – Power over Ethernet

> Provides power + data through a single Ethernet cable.

**P2P** – Peer-to-Peer

> Direct communication between devices (no server).

**PKI** – Public Key Infrastructure

> Manages certificates and encryption keys.

### 🆀️ Q
**QoS** – Quality of Service

> Prioritizes certain network traffic (VoIP, video streaming).

### 🆁️ R
***RSTP** – Rapid Spanning Tree Protocol

> Prevents switching loops, improves convergence time.

**RADIUS** – Remote Authentication Dial-In User Service

> Central authentication for network access.

### 🆂️ S
**SMTP** – Simple Mail Transfer Protocol

> Transfers email between mail servers.

**SNMP** – Simple Network Management Protocol

> Monitors routers, switches, firewalls.

**SSH** – Secure Shell

> Encrypted remote login into servers.

**SSL** – Secure Sockets Layer

> Old encryption protocol replaced by TLS.

**SSO** – Single Sign-On

> One login for multiple systems.

**SFTP** – SSH File Transfer Protocol

> Secure file transfer using SSH.

### 🆃️ T
**TCP** – Transmission Control Protocol

> Reliable, ordered, connection-oriented communication.

**TLS** – Transport Layer Security

> Modern encryption used in HTTPS.

**TTL** – Time To Live

> Limits how long a DNS record or IP packet stays valid.

**TLD** – Top-Level Domain

> .com, .org, .net, country codes.

### 🆄️ U
**UDP** – User Datagram Protocol

> Fast but unreliable.
Used for streaming, gaming, VoIP.

### 🆅️ V
VLAN – Virtual Local Area Network

> Logically segments a LAN for security and efficiency.

**VLSM** – Variable Length Subnet Masking

> Subnetting where subnets have different sizes.

**VPN** – Virtual Private Network

> Encrypted tunnel over the internet.

**VPC** – Virtual Private Cloud

> AWS private network inside the cloud.

### 🆆️ W
**WAN** – Wide Area Network

> Network spanning large geographical areas (ISPs, banks).

**WAF** – Web Application Firewall

> Filters HTTP traffic, protects against web attacks.

**WPA** – Wi-Fi Protected Access

> Wireless security standards (WPA2, WPA3).

### 🆇️ X
**XML** – eXtensible Markup Language

> Used in APIs, config files, enterprise systems.

### 🆈️ Y
**YAML** – YAML Ain’t Markup Language

> Human-friendly data serialization used in DevOps
(Kubernetes, Ansible, GitHub Actions).

### 🆉️ Z
**ZTP** – Zero Touch Provisioning

> Devices auto-configure themselves on first boot.
Used in modern network automation.