# Networking Glossary

A complete reference list of the most common and important networking acronyms, explained in simple and clear language.

---
## 🛰️ General Networking & Internet Acronyms

| Acronym  | Full Meaning                        | Explanation                                                                                     |
| -------- | ----------------------------------- | ----------------------------------------------------------------------------------------------- |
| **IP**   | Internet Protocol                   | The main addressing system of the internet. Every device gets an IP address to communicate.     |
| **TCP**  | Transmission Control Protocol       | Reliable, connection-oriented communication. Ensures every packet reaches the destination.      |
| **UDP**  | User Datagram Protocol              | Fast, connectionless communication. No guarantee of delivery. Used for streaming, VoIP, gaming. |
| **ISP**  | Internet Service Provider           | The company that provides you internet access (e.g., Vodafone, MTN).                            |
| **LAN**  | Local Area Network                  | A small network in one location (home, office).                                                 |
| **WAN**  | Wide Area Network                   | Large-scale network over long distances (e.g., the internet).                                   |
| **MAN**  | Metropolitan Area Network           | Large network covering a city.                                                                  |
| **PAN**  | Personal Area Network               | Small range network around a single person (Bluetooth devices).                                 |
| **NAT**  | Network Address Translation         | A method to allow multiple private devices to share one public IP.                              |
| **DHCP** | Dynamic Host Configuration Protocol | Automatically assigns IP addresses to devices.                                                  |
| **DNS**  | Domain Name System                  | Converts domain names (google.com) into IP addresses.                                           |
| **MAC**  | Media Access Control                | A hardware address burned into network interface cards.                                         |
| **MTU**  | Maximum Transmission Unit           | The largest packet size a network can transmit.                                                 |
| **QoS**  | Quality of Service                  | Prioritizes certain traffic (e.g., video calls > downloads).                                    |
| **ICMP** | Internet Control Message Protocol   | Used for error messages and tools like `ping`, `traceroute`.                                    |
| **TTL**  | Time To Live                        | Limits how long a packet stays on the network. Seen in `ping` output.                           |
| **ARP**  | Address Resolution Protocol         | Maps IP addresses to MAC addresses in a LAN.                                                    |
| **RARP** | Reverse ARP                         | Maps MAC addresses to IP addresses (rare today).                                                |
| **VLAN** | Virtual Local Area Network          | Segments one physical network into multiple virtual networks.                                   |
| **VPN**  | Virtual Private Network             | Creates an encrypted tunnel over the internet.                                                  |
| **MPLS** | Multi-Protocol Label Switching      | High-performance routing in enterprise networks.                                                |
| **CIDR** | Classless Inter-Domain Routing      | Modern IP addressing that supports variable subnet masks.                                       |
| **FQDN** | Fully Qualified Domain Name         | The complete domain name (e.g., `api.example.com`).                                             |
| **CDN**  | Content Delivery Network            | Caches content closer to users (e.g., Cloudflare, Akamai).                                      |

---

## 🌐 HTTP, Web & Application Layer Acronyms

| Acronym   | Full Meaning                          | Explanation                                           |
| --------- | ------------------------------------- | ----------------------------------------------------- |
| **HTTP**  | HyperText Transfer Protocol           | The web’s main communication protocol.                |
| **HTTPS** | HTTP Secure                           | HTTP + SSL/TLS for encrypted web browsing.            |
| **URL**   | Uniform Resource Locator              | The address used to access a web resource.            |
| **URI**   | Uniform Resource Identifier           | A broader identifier (includes URLs).                 |
| **HTML**  | HyperText Markup Language             | Structure of web pages.                               |
| **CSS**   | Cascading Style Sheets                | For designing and styling web pages.                  |
| **API**   | Application Programming Interface     | A defined way for applications to communicate.        |
| **REST**  | Representational State Transfer       | A common API architectural style.                     |
| **SOAP**  | Simple Object Access Protocol         | A strict and XML-based API protocol.                  |
| **SSL**   | Secure Sockets Layer                  | Older encryption protocol for web traffic.            |
| **TLS**   | Transport Layer Security              | Newer, secure version of SSL.                         |
| **JSON**  | JavaScript Object Notation            | Lightweight data format used in APIs.                 |
| **XML**   | eXtensible Markup Language            | Structured data format, older than JSON.              |
| **MIME**  | Multipurpose Internet Mail Extensions | Identifies content type (e.g., `"application/json"`). |

---

## ✉️ Email Protocol Acronyms

| Acronym  | Full Meaning                     | Explanation                                                 |
| -------- | -------------------------------- | ----------------------------------------------------------- |
| **SMTP** | Simple Mail Transfer Protocol    | Used to **send** emails.                                    |
| **POP3** | Post Office Protocol version 3   | Downloads emails from server to client.                     |
| **IMAP** | Internet Message Access Protocol | Accesses emails directly on the server (modern, preferred). |
| **MTA**  | Mail Transfer Agent              | Software that routes emails (e.g., Postfix, Sendmail).      |
| **MUA**  | Mail User Agent                  | Email client (Gmail, Outlook).                              |

---

## 🚦 Routing, Switching & Infrastructure Acronyms
| Acronym  | Full Meaning                      | Explanation                                             |
| -------- | --------------------------------- | ------------------------------------------------------- |
| **OSPF** | Open Shortest Path First          | Popular internal network routing protocol.              |
| **BGP**  | Border Gateway Protocol           | The main routing protocol of the internet.              |
| **RIP**  | Routing Information Protocol      | Older distance-vector routing protocol.                 |
| **ACL**  | Access Control List               | Rules to allow or deny traffic.                         |
| **STP**  | Spanning Tree Protocol            | Prevents network loops in switching.                    |
| **LACP** | Link Aggregation Control Protocol | Combines multiple physical links into one logical link. |
| **DMZ**  | Demilitarized Zone                | Isolated network area for public-facing servers.        |

---

## 🔐 Security Acronyms

| Acronym  | Full Meaning                           | Explanation                                        |
| -------- | -------------------------------------- | -------------------------------------------------- |
| **IDS**  | Intrusion Detection System             | Detects suspicious activity.                       |
| **IPS**  | Intrusion Prevention System            | Detects and actively blocks attacks.               |
| **WAF**  | Web Application Firewall               | Protects web apps from attacks like SQL injection. |
| **SSH**  | Secure Shell                           | Secure login to remote servers.                    |
| **IAM**  | Identity and Access Management         | Controls user permissions (AWS IAM).               |
| **HMAC** | Hash-Based Message Authentication Code | Ensures integrity + authenticity of messages.      |

---

## 📦 Cloud & DevOps Acronyms

| Acronym   | Full Meaning                   | Explanation                                          |
| --------- | ------------------------------ | ---------------------------------------------------- |
| **IaaS**  | Infrastructure as a Service    | Cloud compute, storage, network (AWS EC2, Azure VM). |
| **PaaS**  | Platform as a Service          | App platform (Heroku, Elastic Beanstalk).            |
| **SaaS**  | Software as a Service          | Cloud software (Gmail, Slack).                       |
| **VPC**   | Virtual Private Cloud          | A private network inside AWS/Azure/GCP.              |
| **ENI**   | Elastic Network Interface      | Virtual network card in AWS.                         |
| **ALB**   | Application Load Balancer      | L7 load balancer on AWS.                             |
| **NLB**   | Network Load Balancer          | L4 load balancer for high-performance traffic.       |
| **IGW**   | Internet Gateway               | Allows VPC to reach the internet.                    |
| **NATGW** | NAT Gateway                    | Allows private instances to access the internet.     |
| **CIDR**  | Classless Inter-Domain Routing | Defines IP ranges used in subnets/VPCs.              |

---

## 🛠️ Protocols & Tools

| Acronym   | Full Meaning                       | Explanation                                        |
| --------- | ---------------------------------- | -------------------------------------------------- |
| **FTP**   | File Transfer Protocol             | Transfers files between computers.                 |
| **SFTP**  | SSH File Transfer Protocol         | Secure version of FTP.                             |
| **TFTP**  | Trivial FTP                        | Lightweight file transfer (used for configs/boot). |
| **SNMP**  | Simple Network Management Protocol | Manages network devices.                           |
| **NTP**   | Network Time Protocol              | Syncs clocks on devices.                           |
| **WHOIS** | (Not an acronym)                   | Database lookup of domain ownership.               |
| **DIG**   | Domain Information Groper          | DNS lookup tool.                                   |

---

## 🖼️ Data Formats & Encoding Acronyms

| Acronym   | Full Meaning                                       | Explanation                               |
| --------- | -------------------------------------------------- | ----------------------------------------- |
| **ASCII** | American Standard Code for Information Interchange | Early text encoding standard.             |
| **UTF**   | Unicode Transformation Format                      | Modern encoding supporting all languages. |
| **JPEG**  | Joint Photographic Experts Group                   | Popular compressed image format.          |
| **PNG**   | Portable Network Graphics                          | Lossless image format.                    |
| **GIF**   | Graphics Interchange Format                        | Supports animations.                      |
| **MP4**   | MPEG-4 Part 14                                     | Common video format.                      |
| **AVI**   | Audio Video Interleave                             | Older Microsoft video format.             |

---

# 📡 Networking Models Summary

Understanding networking models helps us see **how data travels** across networks. The two main models used in networking are:

- **OSI Model** (Open Systems Interconnection)
- **TCP/IP Model** (Transmission Control Protocol / Internet Protocol)

---

## ✅ OSI Model (Open Systems Interconnection)

The OSI model is a **7-layer framework** that standardizes how systems communicate.  
It breaks networking into clear layers, each responsible for specific tasks.

### **7 Layers of the OSI Model**

| Layer | Name | Purpose / Function | Examples |
|------|------|--------------------|---------|
| 7 | **Application Layer** | Provides user-level network services | Web browser, HTTP, FTP, SMTP, DNS |
| 6 | **Presentation Layer** | Data translation, encryption, compression | SSL/TLS, JPEG, MP3, ASCII |
| 5 | **Session Layer** | Manages sessions and connections | NetBIOS, RPC, SSH sessions |
| 4 | **Transport Layer** | Reliable data delivery, segmentation | TCP, UDP, ports, flow control |
| 3 | **Network Layer** | Routing and IP addressing | IP, ICMP, routers |
| 2 | **Data Link Layer** | Physical addressing (MAC), error detection | MAC address, Ethernet, switches |
| 1 | **Physical Layer** | Transmission of raw bits over media | Cables, Wi-Fi, voltages, hubs |

### 🧠 Quick OSI Memory Trick

> **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing  
Application, Presentation, Session, Transport, Network, Data Link, Physical

---

## ✅ TCP/IP Model (Transmission Control Protocol / Internet Protocol)

The TCP/IP model is the **practical model used on the Internet**, created before OSI.  
It explains data flow in **5 layers**.

### **5 Layers of TCP/IP Model**

| Layer | Name | Purpose / Function | Examples |
|------|------|--------------------|---------|
| 5 | **Application Layer** | User services and protocols | HTTP, DNS, SSH, SMTP, FTP |
| 4 | **Transport Layer** | End-to-end communication, reliability | TCP, UDP, ports |
| 3 | **Network Layer** | Logical addressing and routing | IP, ICMP, routers |
| 2 | **Data Link Layer** | MAC addressing, framing | Ethernet, switches, ARP |
| 1 | **Physical Layer** | Physical media and signals | Cables, NIC, Wi-Fi, fiber |

---

##  OSI vs TCP/IP — Comparison Table

| Feature | OSI Model | TCP/IP Model |
|--------|----------|--------------|
| Full Name | Open Systems Interconnection | Transmission Control Protocol / Internet Protocol |
| Layers | 7 layers | 5 layers |
| Usage | Reference/teaching model | Real-world networking model |
| Layer Focus | Detailed — strict separation | More flexible and simplified |
| Developed By | ISO | DoD (U.S. Department of Defense) |
| Transport Protocols | TCP, UDP | TCP, UDP |
| Network Layer Protocol | IP | IP |
| Best For | Learning & troubleshooting | Internet communication and DevOps use |

#  TCP vs UDP — Comparison Table

| TCP                 | UDP                    |
| ------------------- | ---------------------- |
| Reliable            | Fast                   |
| Connection-oriented | Connectionless         |
| Handshake required  | No handshake           |
| Used for web, email | Used for video, gaming |


---

## 🎯 Key Takeaways

- OSI = **7 layers** (theoretical model)
- TCP/IP = **5 layers** (real-world model)
- Both explain **how data moves** across a network
- DevOps engineers frequently work with:
  - **IP, DNS, HTTP, SSH** (Application)
  - **TCP/UDP & Ports** (Transport)
  - **Routing & subnets** (Network)
  - **Ethernet, MAC, Wi-Fi** (Data Link / Physical)

---

# 🧠 Application Layer (Layer 7)

The **Application Layer** is the top layer of the OSI model.  
It provides the **interface between user applications and the network**.

This layer does **not** refer to the application itself  
but the **protocols and services applications use to communicate over a network**.

Examples:
- Web browsing
- Email
- File transfer
- Remote login
- DNS resolution

---

## 🌐 Key Protocols in the Application Layer

| Protocol | Purpose | Port | Transport |
|---------|---------|------|-----------|
| **HTTP** (HyperText Transfer Protocol) | Web browsing | 80 | TCP |
| **HTTPS** (Secure HTTP) | Secure web browsing (TLS/SSL) | 443 | TCP |
| **FTP** (File Transfer Protocol) | File transfer | 21 | TCP |
| **SFTP** (Secure File Transfer) | Secure file transfer | 22 | TCP (SSH) |
| **SMTP** (Simple Mail Transfer Protocol) | Sending emails | 25 | TCP |
| **POP3** (Post Office Protocol v3) | Downloading emails | 110 | TCP |
| **IMAP** (Internet Message Access Protocol) | Reading emails on server | 143 | TCP |
| **DNS** (Domain Name System) | Converts domain names to IP | 53 | UDP/TCP |
| **SSH** (Secure Shell) | Secure remote login | 22 | TCP |
| **DHCP** (Dynamic Host Configuration Protocol) | Assigns IPs | 67/68 | UDP |
| **TELNET** | Remote login (insecure) | 23 | TCP |

---

## 🏛️ Client-Server Architecture

Most network systems follow a **client-server model**.

| Client | Server |
|--------|--------|
| Sends request | Processes requests |
| Consumes data | Stores & serves data |
| Browser, app, CLI | Web server, DB server, mail server |

Example:
- Browser = client
- Web server (Nginx/Apache) = server

---

## 🔁 Peer-to-Peer (P2P) Architecture

P2P networks **do not require a central server**.  
Devices communicate **directly**.

Examples:
- Torrents
- Blockchain networks (Bitcoin)
- Some chat services

| Client-Server | P2P |
|--------------|-----|
| Central server | No central server |
| Scalable but costly | Highly scalable |
| Single point of failure | No single point failure |

---

## 🖥️ Networking Devices & Their Roles

| Device | Role |
|-------|-----|
| **Router** | Routes packets between networks & assigns IPs |
| **Switch** | Connects devices in a LAN & forwards using MAC |
| **Hub** | Broadcasts to all ports (old tech) |
| **Firewall** | Filters traffic by rules & ports |
| **Modem** | Converts analog ↔ digital internet signal |
| **Access Point** | Provides wireless network access |
| **Load Balancer** | Distributes traffic across servers |
| **Gateway** | Connects different network types |

---

## 🔌 How Applications Communicate: Sockets & Ports

### **Sockets**
A socket = `IP address + Port number`

Example:

`192.168.1.10:22 (SSH)`
`10.0.0.5:80 (HTTP)`

### **Ports**
Ports help identify **applications/services** on a device.

| Range | Type |
|------|------|
| 0–1023 | Well-known ports (HTTP 80, SSH 22) |
| 1024–49151 | Registered/ app ports |
| 49152–65535 | Private/ dynamic ports |

---

## 🌍 HTTP — Web Communication Protocol

### **HTTP Methods**

| Method | Purpose |
|--------|--------|
| **GET** | Retrieve data |
| **POST** | Send/submit data |
| **PUT** | Update/replace data |
| **PATCH** | Partial update |
| **DELETE** | Remove data |
| **HEAD** | Get header info only |
| **OPTIONS** | Check supported methods |

### Cookies
Cookies are **small data files** saved on client side to store:
- Session IDs
- Login tokens
- User preferences
- Tracking info

---

## ✉️ How Email Works

### **Protocols**

| Purpose | Protocol | Port |
|--------|--------|------|
Send email | SMTP | 25 |
Receive email | POP3 | 110 |
Read email from server | IMAP | 143 |

### **Flow Example**

1. User sends email → SMTP server
2. SMTP forwards to recipient’s mail server
3. Recipient retrieves via POP3/IMAP

---

## 🌐 DNS — Domain Name System

DNS converts **domain names → IP addresses**

Example:

`google.com → 142.250.64.78`


### DNS Record Types

| Record | Stands For         | What It Does                          |
| ------ | ------------------ | ------------------------------------- |
| A      | Address            | Maps a domain to an IPv4 address                          |
| AAAA   | Quad-A             | Maps a domaain to an IPv6 address                          |
| CNAME  | Canonical Name     | Creates an alias to another domain               |
| MX     | Mail eXchange      | Specifies Mail servers  responsible for receiving emails for your domain.                |
| NS     | Name Server        | Defines the authoritative DNS servers for the domain            |
| TXT    | Text               | Info used for verification + security ( SPF, DKIM, DMARC, Verification, Security policies)|
| SOA    | Start of Authority | DNS zone admin details("Birth certificate" of a DNS zone)                |


### DNS Tools
- `nslookup` - Name Server Look Up
- `dig` - Domain Information Groper
- `host`

---

## 💡 Summary

- Application Layer enables **user services**
- Uses protocols like **HTTP, SMTP, DNS, FTP, SSH**
- Supports **client-server & P2P architectures**
- Uses **sockets & ports** for communication
- Handles **web, email, DNS, authentication**

---

# Presentation Layer & Session Layer

## Layer 6: Presentation Layer

The **Presentation Layer** is responsible for making data from the application layer readable across different systems. It ensures **formatting, encryption, and compression** of data.

> Think of it as the translator and formatter for network communications.

#### Key Responsibilities
- Data translation (converts formats so systems understand each other)
- Encryption and decryption (secure data transmission)
- Compression and decompression (reduce file size to save bandwidth)
- Character encoding conversion (ASCII, UTF-8, Unicode)

#### Common Standards & Formats

| Category | Examples |
|--------|--------|
Text Encoding | ASCII, UTF-8, UTF-16 |
Image Formats | JPEG, PNG, GIF |
Video Formats | MP4, AVI |
Encryption Protocols | SSL, TLS |
Serialization Formats | JSON, XML |

#### Real-World Example
When visiting a secure website (HTTPS), this layer encrypts data using **TLS**, protecting passwords, cards, and personal info.

---

## Layer 5: Session Layer

The **Session Layer** manages and controls **sessions** — ongoing communication between two devices. It opens, maintains, and closes dialogs.

> Think of this layer as the "meeting coordinator" for data exchange.

#### Key Responsibilities
| Function | Description |
|--------|-------------|
Session creation | Starts communication between devices |
Session maintenance | Keeps communication active |
Session termination | Cleanly closes session |
Authentication | Confirms identity before communication |
Dialog control | Manages who speaks and when |
Checkpointing | Saves progress to resume transmission if interrupted |

#### Real-World Examples
| Scenario | Session Layer Role |
|---------|-------------------|
Logging into a website | Maintains your login session |
Zoom/Teams call | Keeps call active and synchronized |
File transfer via FTP | Sets checkpoints, resumes if connection drops |

---

### Protocols Seen at These Layers

| Layer | Sample Protocols |
|------|------------------|
Presentation | TLS, SSL, HTTPS, ASCII, UTF-8, JPEG, MPEG |
Session | NetBIOS, RPC, PPTP, SIP, SMB |

---

### Simple Analogy

| Layer | Function | Analogy |
|------|---------|--------|
Presentation | Format, encrypt, compress data | Translator + envelope sealing a letter |
Session | Create, maintain, close connection | Starting, continuing, and ending a phone call |

---

### Summary Table

| Layer | Name | Purpose |
|------|------|--------|
6 | Presentation | Data formatting, encryption, compression |
5 | Session | Establishes and controls communication sessions |

---

# 🧩 Layer 4: Transport Layer

Welcome to the **Transport Layer** — the **traffic controller** and **delivery service** of networking.

Think of it like a global courier (DHL/UPS):
- Ensures your package (data) goes to the right home (port)
- Decides whether to deliver carefully with receipts + signatures (TCP)
- Or just drop it fast without fuss (UDP)
- Tracks lost packages and resends them (reliability)
- Avoids traffic jams (flow control)

Without this layer, the internet would be chaos — like throwing letters into the air and hoping they land in the right mailbox!

> Note that transport layer is easily confused with Network layer. Below is table that differentiate their jobs.

## 🚚 Transport Layer vs 🌐 Network Layer

| Feature                | **Transport Layer (Layer 4)**                               | **Network Layer (Layer 3)**                    |
| ---------------------- | ----------------------------------------------------------- | ---------------------------------------------- |
| **Primary Purpose**    | Reliable delivery **between processes (apps)**              | Delivery **between devices/networks**          |
| **Main Role**          | Ensures complete, correct data delivery end-to-end          | Finds the best path across networks            |
| **Communication Type** | **End-to-end** (host to host apps)                          | **Hop-to-hop** (router to router)              |
| **Key Functions**      | Connection mgmt, error handling, flow control, segmentation | Routing, logical addressing, packet forwarding |
| **Data Unit Name**     | Segment (TCP) / Datagram (UDP)                              | Packet                                         |
| **Protocols**          | **TCP**, **UDP**, SCTP                                      | **IP**, ICMP, ARP, IGMP                        |
| **Addressing**         | **Port Numbers** (e.g., 443, 22, 80)                        | **IP Addresses** (e.g., 192.168.1.10)          |
| **Reliability**        | Can be reliable (TCP) or unreliable (UDP)                   | No reliability — only forwarding               |
| **Error Handling**     | Yes (retransmission, checksum)                              | Limited (ICMP error reporting)                 |
| **Flow Control**       | Yes (TCP sliding window)                                    | No                                             |
| **Routing Involved?**  | ❌ No                                                        | ✅ Yes (routing tables, BGP, OSPF, RIP)         |
| **Device Involved**    | Host machines                                               | **Routers**                                    |
| **OSI Layer #**        | Layer 4                                                     | Layer 3                                        |
| **Examples**           | HTTP relies on TCP, DNS can use UDP                         | Your IP packet crossing the internet           |


### 🤓 Quick memory hack

| Mnemonic                                           | Meaning                       |
| -------------------------------------------------- | ----------------------------- |
| **Transport = T for Talking between applications** | It manages the *conversation* |
| **Network = N for Navigating networks**            | It manages the *path/route*   |


---

### 🎯 What the Transport Layer Does - Deep dive with fun analogies

| Function | Description | Real-Life Analogy |
|---|---|---|
Segmentation | Breaks big data into smaller chunks | Breaking a pizza into slices |
Reassembly | Rebuilds chunks into original data | Putting the pizza back together |
Flow Control | Prevents overwhelming the receiver | Talking slowly so someone taking notes can keep up |
Error Control & Retransmission | Detects lost data, resends | "Did you get that? Let me repeat." |
Connection Control | Establishes & ends communication | Handshake before conversation |
Port Addressing | Directs data to correct app | Apartment numbers in a building |

---

### 🚦 TCP vs UDP — Delivery Styles

| Feature | **TCP** (Transmission Control Protocol) | **UDP** (User Datagram Protocol) |
|---|---|---|
Type | Connection-oriented | Connectionless |
Reliability | ✅ Reliable, guaranteed delivery | ❌ No guarantee |
Acknowledgment | Yes | No |
Ordering | Ensures correct order | No ordering |
Speed | Slower (safe & reliable) | Faster (no checks) |
Use Case | Browsing, email, file transfer | Streaming, gaming, VoIP |

#### 📦 Memory Trick

> **TCP = Talk Carefully**  
> **UDP = Ultra-Fast Data Push**

---

## Connection flow in TCP

Connection is controlled by **Timers**, and the packets of data sent are traced using the sequence number. With this kind of back and forth communication, the data is traced and timed and errors and omitted! Cool!

`sudo tcpdump -c 5` - this command shows you the number of packets coming in, in this case, `5` being the number packets I have set to recieve. 

### 🤝 TCP Handshake (3-Way Handshake)

TCP sets up a connection first — like a polite conversation:

`Client: SYN → Hey, can we talk?` - Synchronisation flag + Sequence number
`Server: SYN-ACK → Sure, I'm ready!` Synchronisation flag + Server Acknowlegemnt Number.
`Client: ACK → Great, let’s start!` Acknowlegement (number +1)

Connection is established ✅  
Now real data flows.

---

### 📉 TCP Connection Termination (4-Way Disconnect)

`FIN → Closing now?`
`ACK → Received`
`FIN → Me too.`
`ACK → Bye!`


Like saying goodbye politely instead of hanging up suddenly.

---

### 🎚️ Flow Control & Congestion Control

| Mechanism | Purpose |
|---|---|
Windowing | Controls how much data is sent before needing ACK |
Buffering | Temporarily stores incoming data |
Congestion Avoidance | Avoids flooding the network |

---

## 🎮 UDP in Action — Low Latency Wins

Components of a UDP packet:

- Source and Destination Port numbers.
- Length of datagram.
- Checksum.

UDP sends without waiting, speed over reliability.

Used in:

- 🎮 Online gaming
- 🎥 Video streaming (Netflix, YouTube)
- 📞 Voice calls (Zoom, WhatsApp)
- 📡 DNS queries

> In games, you’d rather skip one frame than freeze!

---

### 🔢 Well-Known Ports (Must-Know!)

| Protocol | Port | Notes |
|---|---|---|
HTTP | 80 | Web (unsecured) |
HTTPS | 443 | Secure web |
SSH | 22 | Secure login to servers |
FTP | 20/21 | File transfers |
DNS | 53 | Translates domain to IP |
SMTP | 25 | Send email |
IMAP | 143 | Receive email |
POP3 | 110 | Download email |
DHCP | 67/68 | Gives IP addresses |
DNS | 53 | Name resolution |
RDP | 3389 | Remote Desktop (Windows) |

> Tip: Ports = **doors** to applications on your OS.

---

### 🛠️ Tools to Test Transport Layer

| Tool | Use |
|---|---|
`netstat` | Shows active connections |
`ss` | View socket statistics |
`telnet <ip> <port>` | Test ports |
`nc` / `netcat` | Send data manually to ports |
`ping` | ICMP — network reachability (not TCP/UDP) |

---

### 🧠  A quick Summary of what we already discussed

| Feature | TCP | UDP |
|---|---|---|
Connection | Required | None |
Reliability | High | Low |
Speed | Slower | Very fast |
Order | Guaranteed | Not guaranteed |
Use | Email, Web, File Transfer | Video, Games, VoIP |

---

### 🏁 Quick Memory Cheat-Codes

- **TCP** = Reliable, ordered, handshake
- **UDP** = Fast, lightweight, no guarantee
- **Ports** = App entry doors
- **Transport Layer = Data delivery boss**

---

### ✅ Why  as DevOps Engineers  we should Care

- Load balancers route TCP/UDP traffic
- Kubernetes services use ports & protocols
- Firewalls, security groups, NACLs operate on ports
- Debugging connectivity issues requires TCP/UDP knowledge
- DNS, SSH, HTTPS — all transport layer use cases

> If we can troubleshoot ports & protocols, we can troubleshoot the cloud.

---

# 🌐 Network, Data-Link, and Physical layers

These are the **foundation levels** of the OSI model — where IP addresses, MAC addresses, routers, switches, cables, and electricity all come alive.

These layers decide **where data goes**, **how it travels**, and **what format it takes on the wire**.

---

## 3️⃣ Network Layer (Layer 3)

The **Network Layer** handles **routing**, **logical addressing**, and **path selection**.

> Think of this layer as **Google Maps for your data** — deciding the best route across the internet.

**Control Plane**:  This is where the Routers tables lie. Routers are nodes and the links between are the Egdes. Routers create a sort of maps or graphs that are connected.

### 🧠 Core Responsibilities

| Function | Meaning |
|---|---|
Logical addressing | Assigns IP addresses to devices |
Routing (Routing Table) | Chooses best path across networks |
Packet forwarding | Moves data from router to router |
Fragmentation | Breaks large packets if needed |

---

### 🧾 Key Concepts

| Concept | Description |
|---|---|
IP Address | Logical device address (like a street address) |
Router | Device that forwards packets between networks |
Subnetting | Dividing a network into smaller networks |
NAT | Allows many devices to share one public IP |
ICMP | Used for troubleshooting (ping) |

---

### 🚀 Protocols @ Network Layer

| Protocol | Purpose |
|---|---|
IPv4 / IPv6 | Addressing & routing |
ICMP | Ping, traceroute, diagnostics |
ARP* | Finds MAC from IP (*belongs between L2 & L3) |
OSPF, BGP, RIP | Routing protocols |
IPSec | Secure IP traffic |

---

### 🌍 Real-World Examples
- Visiting a website (uses IP + routing)
- Sending messages across countries
- Cloud VPC routing in AWS, Azure, GCP

> If TCP is the postman, **IP is the address written on the envelope**.

---

## 2️⃣ Data-Link Layer (Layer 2)

The **Data-Link Layer** provides **node-to-node delivery** inside the same local network (LAN). DHCP (Dynamic Host Configuration Protocol) servers are the point of contact for new devices to get allocated a new IP address. Data link layer Address of sender and IP address of destination are part the shoe kinking process.

> Think of it as **the rulebook for neighbors talking over the fence**.

---

### 🧠 Core Responsibilities

| Task | Explanation |
|---|---|
MAC addressing | Physical address burned into NIC |
Frames | Data formatting for LAN transmission |
Error checking | Detects transmission errors |
Flow control | Prevents overwhelming devices |
Switching | Forwards frames inside the LAN |

---

### 🧾 Sub-Layers

| Sub-Layer | Role |
|---|---|
LLC (Logical Link Control) | Identifies protocols, error control |
MAC (Media Access Control) | Uses MAC addresses, controls access |

---

### 🔌 Devices & Protocols

| Device / Protocol | Role |
|---|---|
Switch | Forwards frames in LAN using MAC |
Bridge | Connects LAN segments |
ARP | Maps IP to MAC |
Ethernet | LAN communication standard |
Wi-Fi (802.11) | Wireless LAN |

---

### 🍪 MAC Address Example

`D4-3B-04-9A-2C-F1`

Like a device fingerprint — **unique, permanent, cannot be shared**.

---

### ⚡ Fun Memory Tip

> **Layer 2 = Switching + MAC + LAN**

When troubleshooting local network issues — think Layer 2 first.

---

## 1️⃣ Physical Layer (Layer 1)

The **Physical Layer** is the **hardware and electrical world** — it moves **bits** (0s and 1s) across cables and signals.

> Imagine being inside the cable hearing electrons and light fibers shouting “ONE! ZERO! ZERO! ONE!” 😆

---

### 🧠 Core Responsibilities

| Task | Meaning |
|---|---|
Bit transmission | Sends raw bits across media |
Electrical / Optical standards | Voltage, light wave standards |
Physical topology | Star, mesh, hybrid layouts |
Media type | Fiber, copper, radio waves |
Device connectors | RJ45, fiber LC, antennas |

---

### 🔌 Devices, Media & Standards

| Type | Example |
|---|---|
Cables | Ethernet, Fiber, Coaxial |
Wireless | Bluetooth, Wi-Fi |
Repeaters | Boost signal |
Hubs | Broadcast traffic to all ports |
Connectors | RJ45, BNC, Fiber plugs |
Standards | IEEE 802.3 (Ethernet), 802.11 (Wi-Fi) |

---

### 🧾 Fun Memory Trick

> **Layer 1 = Electricity, Light, Radio Waves**

Or simpler:

> **If you can physically touch it — it’s Layer 1**

---

## 🎉 Final Summary

| Layer | Focus | Device | Address Type | Data Unit |
|---|---|---|---|---|
3 | Routing between networks | Router | IP | Packet |
2 | Local network delivery | Switch | MAC | Frame |
1 | Signals & media | Cables, NICs | N/A | Bits |

---








