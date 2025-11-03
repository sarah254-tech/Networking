# 🧾 Acronym Glossary (DNS & DevOps Networking)

Let us quickly dig into the most common acronyms that will keep on emerging on this notes,

## 🌐 DNS-Related Acronyms

| Acronym            | Full Meaning             | What It Does                                             |
| ------------------ | ------------------------ | -------------------------------------------------------- |
| **DNS**            | Domain Name System       | Translates domain names to IP addresses                  |
| **TTL**            | Time To Live             | How long DNS info is cached before refreshing            |
| **TLD**            | Top-Level Domain         | Extension like `.com`, `.org`, `.net`                    |
| **IP**             | Internet Protocol        | Numerical address used to identify a device on a network |
| **URL**            | Uniform Resource Locator | Web address (like `https://google.com`)                  |
| **URL → DNS → IP** | Request chain            | Browser → DNS lookup → server IP returned                |


---

## 📬 Email Authentication Acronyms (VERY important for DevOps)

| Acronym   | Full Form                                                    | Purpose                                                                                |
| --------- | ------------------------------------------------------------ | -------------------------------------------------------------------------------------- |
| **SPF**   | Sender Policy Framework                                      | Prevents spoofed email senders; tells internet "who can send mail for this domain"     |
| **DKIM**  | DomainKeys Identified Mail                                   | Uses cryptographic signatures to verify email wasn't tampered with                     |
| **DMARC** | Domain-based Message Authentication, Reporting & Conformance | Policy that tells mail servers what to do if SPF/DKIM fail (reject, quarantine, allow) |

**✅ In DevOps/cloud deployments, you will configure SPF, DKIM, and DMARC when setting up domain email & preventing spam.**

---

## 🔐 Security & Certificate Acronyms

| Acronym   | Full Meaning                       | Purpose                                                               |
| --------- | ---------------------------------- | --------------------------------------------------------------------- |
| **SSL**   | Secure Sockets Layer               | Encrypts data between browser & server *(legacy term but still used)* |
| **TLS**   | Transport Layer Security           | Modern replacement for SSL (actual current encryption standard)       |
| **HTTPS** | Hypertext Transfer Protocol Secure | Secure version of HTTP (uses SSL/TLS certificates)                    |

**SSL is what people say, TLS is what modern systems use.**

---

## 🧰 DNS/Networking Command Acronyms

| Command    | Means                     | Use                                              |
| ---------- | ------------------------- | ------------------------------------------------ |
| `dig`      | Domain Information Groper | Advanced DNS query tool                          |
| `nslookup` | Name Server Lookup        | Basic DNS lookup tool                            |
| `host`     | Hostname Lookup           | Simple DNS name-to-IP lookup                     |
| `ping`     | Packet Internet Groper    | Tests connection to a host / DNS + network check |


---

## 📡 Protocol Acronyms

| Acronym  | Full Name                         | Purpose                                     |
| -------- | --------------------------------- | ------------------------------------------- |
| **TCP**  | Transmission Control Protocol     | Reliable, connection-oriented communication |
| **UDP**  | User Datagram Protocol            | Fast, connectionless, less reliable         |
| **ICMP** | Internet Control Message Protocol | Used by ping/traceroute for diagnostics     |
| **HTTP** | Hypertext Transfer Protocol       | Web communication                           |
| **SMTP** | Simple Mail Transfer Protocol     | Sends emails                                |
| **POP**  | Post Office Protocol              | Downloads email to client                   |
| **IMAP** | Internet Message Access Protocol  | Reads email on server without deleting      |


---

## 🖥 OS / System Acronyms

| Acronym   | Full Meaning     | Purpose                               |
| --------- | ---------------- | ------------------------------------- |
| **OS**    | Operating System | Manages hardware & software resources |
| `sudo`    | Super-User DO    | Runs command as admin/root            |
| `systemd` | System Daemon    | Linux system & service manager        |

`sudo systemd-resolve --flush-caches`
Clears DNS cache on Linux systems using systemd

---

# 🌐 DNS Basics: The Internet's Phonebook 

When you type `google.com` into your browser, your computer doesn’t magically know where Google lives.
It needs directions, just like you need Google Maps when traveling to a new place.

DNS (Domain Name System) = The Internet Phonebook / GPS
It translates human-friendly names into IP addresses computers understand.

`google.com ➝ 142.250.190.78 (example IP)`

---

## 🎯 Why DNS Matters in DevOps

As a DevOps engineer, you will use DNS daily when:

- Deploying apps on cloud (AWS Route53 / GCP Cloud DNS / Azure DNS)

- Configuring load balancers and ingress in Kubernetes

- Setting up CI/CD for domains and SSL (Let's Encrypt)

- Connecting microservices and APIs

- Diagnosing "site not reachable" issues

If networking is the internet's skeleton, **DNS is the brain that remembers everything** 🧠✨

---

## 🧩 How DNS Works (Step-by-Step Lookup Journey)

When you type `www.example.com`:

**1️⃣ Browser Cache**

- Computer checks if it already knows the IP

- Fastest lookup

**2️⃣ OS / Local DNS Cache**

- Stored recently resolved addresses

**3️⃣ Router / Local DNS Resolver**

- Your home/office router often caches DNS

**4️⃣ ISP DNS Resolver**

- Your internet company checks if they know it

**5️⃣ Root DNS Servers**

- First stop if everything else fails

- Point to TLD servers (.com, .net, .org)

**6️⃣ TLD Servers**

- `.com` servers point to the domain’s DNS host

**7️⃣ Authoritative DNS Server**

- Final authority for the domain

- Holds the actual DNS records

**8️⃣ IP Returned → Website Loads**

Browser connects to the server using IP

🎬 Done in milliseconds!

> It's interesting to note that you can never buy a domain name, but only rent it.

> `man dig` - is the quick DNS name servers look-up command.

---

## 🧠 DNS Records (Cheat Sheet Table)

| Record Type | Purpose                        | Example                                    |
| ----------- | ------------------------------ | ------------------------------------------ |
| A           | Hostname ➝ IPv4                | `google.com = 142.250.190.78`              |
| AAAA        | Hostname ➝ IPv6                | `google.com = 2607:f8b0::1234`             |
| CNAME       | Alias domain name              | `www ➝ example.com`                        |
| MX          | Mail server                    | `mx.example.com`                           |
| TXT         | Metadata / domain verification | `Google Workspace, SPF, DKIM`              |
| NS          | Nameserver for domain          | `ns1.hosting.com`                          |
| PTR         | IP ➝ hostname (reverse lookup) | `78.190.250.142 ➝ google.com`              |
| SOA         | Admin info for domain          | Primary DNS server, contact, refresh rules |


## 🚨 DevOps Tip

You will configure TXT records when setting up SSL & email (SPF, DKIM, DMARC).

---

## 🌎 DNS Hierarchy (Think of it like government levels)

Root (.)
> TLD (.com, .org, .net)

>  Domain (example.com)

>  Subdomain (www.example.com)

🧩 Root = President
🧩 .com = Ministry
🧩 example.com = City
🧩 www. = Street

---

## 🕵️‍♂️ DNS Tools Every DevOps Should Master
### ✅ Linux Commands

| Command                 | Use                       |
| ----------------------- | ------------------------- |
| `nslookup google.com`   | Simple DNS lookup         |
| `dig google.com`        | Detailed DNS query        |
| `dig +trace google.com` | Full DNS resolution path  |
| `host google.com`       | Quick DNS lookup          |
| `ping google.com`       | Checks DNS + connectivity |


**Example** `dig` **Output Highlights**

| Field     | Meaning                      |
| --------- | ---------------------------- |
| ANSWER    | DNS result (IP returned)     |
| AUTHORITY | Which server has DNS control |
| TTL       | How long to cache result     |

### Cloud DNS Services

- AWS Route 53

- GCP Cloud DNS

- Azure DNS Zones

- Cloudflare DNS (fast + secure)

---

### 🚫 Common DNS Issues & Fixes

| Problem                      | Cause                  | Fix                                   |
| ---------------------------- | ---------------------- | ------------------------------------- |
| Site not loading             | DNS not resolved       | Try `dig`, `host`, `nslookup`         |
| Wrong server serving content | Stale DNS cache        | `sudo systemd-resolve --flush-caches` |
| Email going to spam          | Incorrect DNS records  | Add SPF, DKIM, DMARC                  |
| SSL errors                   | DNS not propagated yet | Wait or lower TTL                     |

---

## 🧠 TTL- Time To Live

DNS records are cached to speed up lookups.
| TTL Value             | Meaning                        |
| --------------------- | ------------------------------ |
| 60 seconds            | Fast testing, dynamic services |
| 3600 seconds (1 hr)   | Common default                 |
| 86400 seconds (1 day) | Static/rarely changed records  |

> Lower TTL before moving servers,speeds up propagation!


---

## 🎉 Summary

DNS converts **names** → **IPs**
It is:

- Your online phonebook

- A critical DevOps skill

- Required in Cloud, Kubernetes, CI/CD, Email, and Load balancing

Mastering DNS,  makes debugging becomes 100x easier.

> When a website is "down", it’s often DNS, not the server.