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

## 🆚 OSI vs TCP/IP — Comparison Table

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

