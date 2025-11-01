# 🔥 Firewalls & Ports
## **The Gatekeepers of the Network Kingdom**

When data travels across the internet, it’s like cars moving on a highway. Some cars are allowed in, others are turned away. In tech, **your firewall is the police checkpoint**, and **ports are the entry gates** into your system.

As a DevOps engineer, we’ll deal with firewalls and port rules daily, especially when deploying apps, securing services, and debugging “why isn’t this working?!” moments.

---

## 🧱 What is a Firewall?

A **firewall** is a security device or software that monitors incoming and outgoing traffic and decides whether to allow or block it based on security rules.

Think of it as:

> “You shall not pass!” -Gandalf to untrusted traffic

### 📌 What Firewalls Do

| Role                    | Explanation                              |
| ----------------------- | ---------------------------------------- |
| **Traffic Filtering**   | Blocks or allows traffic based on rules  |
| **Protects Systems**    | Prevents attacks and unauthorized access |
| **Monitors & Logs**     | Keeps records of network activity        |
| **Defines Trust Zones** | Internet vs internal network             |

---

## 🔥 Types of Firewalls

1️⃣ **Packet-Filtering Firewall**

- Checks packets’ source/destination IP & port

- Fast but basic

2️⃣ **Stateful Firewall**

- Tracks connections and traffic states

- More secure & intelligent than packet-filtering

3️⃣ **Application-Layer Firewall (Proxy)**

- Looks inside packets at application data

- Great for HTTP/HTTPS inspection

4️⃣ **Next-Gen Firewall (NGFW)**

- Deep packet inspection

- Blocks malware, intrusion detection, app-level filtering

- AI/ML analysis (fancy stuff)

5️⃣ **Cloud Firewalls**

- Provided by cloud vendors (AWS, Azure, GCP)

- Secures virtual machines, load balancers, Kubernetes, etc.


---

## Firewall in DevOps / Cloud

| Platform       | Firewall Concept                  |
| -------------- | --------------------------------- |
| **AWS**        | Security Groups, NACLs, WAF       |
| **Azure**      | NSG, App Gateway Firewall         |
| **GCP**        | VPC Firewall Rules                |
| **Kubernetes** | Network Policies (Calico, Cilium) |


---

## 🚪 Ports & Protocols Explained

### **What is a Port?**

A **port** is a number that identifies a service on a device.

Think of it like:

- House = IP address

- Apartment number = Port

> IP takes you to the building.
> Ports take you to the right room (service).

Ports range: **0 – 65535**

| Group                 | Range       | Usage                         |
| --------------------- | ----------- | ----------------------------- |
| **Well-known ports**  | 0-1023      | Common services (HTTP, SSH)   |
| **Registered ports**  | 1024-49151  | Apps & services register here |
| **Dynamic/Ephemeral** | 49152-65535 | Temporary connections         |


---

## 📎 Common Ports Every DevOps Engineer MUST Know

| Service              | Protocol | Port   |
| -------------------- | -------- | ------ |
| HTTP                 | TCP      | 80     |
| HTTPS                | TCP      | 443    |
| SSH                  | TCP      | 22     |
| FTP                  | TCP      | 20, 21 |
| SFTP                 | TCP      | 22     |
| DNS                  | UDP/TCP  | 53     |
| SMTP (Email send)    | TCP      | 25     |
| POP3 (Email receive) | TCP      | 110    |
| IMAP                 | TCP      | 143    |
| MySQL                | TCP      | 3306   |
| PostgreSQL           | TCP      | 5432   |
| Redis                | TCP      | 6379   |
| MongoDB              | TCP      | 27017  |
| Kubernetes API       | TCP      | 6443   |

Save this list, tattoo it mentally, or frame it above your desk 😄

---

## 🛠 Linux Firewall Commands (UFW)

| Action                | Command                                    |
| --------------------- | ------------------------------------------ |
| Check firewall status | `sudo ufw status`                          |
| Allow SSH             | `sudo ufw allow 22`                        |
| Allow HTTP/HTTPS      | `sudo ufw allow 80` — `sudo ufw allow 443` |
| Deny port             | `sudo ufw deny 23`                         |
| Enable firewall       | `sudo ufw enable`                          |


---

## 🌐 Firewall Rules in Cloud CLI

aws ec2 authorize-security-group-ingress \
  --group-id sg-xxxx \
  --protocol tcp \
  --port 22 \
  --cidr 0.0.0.0/0

  ---

  ## 🧠 Key Takeaways

  - Firewalls = Security guards of your network

- Ports = Entry gates to services

- Cloud firewalls are essential in DevOps

- Know your common ports (22, 80, 443, DB ports, etc.)

- Always restrict access — least privilege wins


---

## 🎯 Real-World Troubleshooting Scenarios

| Situation               | What you do                         |
| ----------------------- | ----------------------------------- |
| Website not loading     | Check ports 80/443 open             |
| SSH into EC2 fails      | Check port 22 security group rule   |
| DB connection fails     | Open DB port only to app server VPC |
| Kubernetes pods blocked | Apply correct network policies      |






