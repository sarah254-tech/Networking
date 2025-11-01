# 🛠️ Network Tools & Troubleshooting Cheatsheet

A DevOps-friendly guide to debugging networks like a boss 👑

Networking breaks.
**We don’t panic — we troubleshoot**.

This guide walks you through essential tools, commands, and interpretation tips to diagnose and fix network issues fast.

---

## First Step: Basic Troubleshooting Mindset

| Step                | What to Check          | Commands                          |
| ------------------- | ---------------------- | --------------------------------- |
| ✅ Connectivity      | Is the network up?     | `ping`, `ip addr`, `ifconfig`     |
| 🌍 DNS Resolution   | Can we resolve names?  | `nslookup`, `dig`, `host`         |
| 🛣️ Routing         | Do we have a path?     | `traceroute`, `ip route`, `route` |
| 🔏 Firewall / Ports | Are ports blocked?     | `netstat`, `ss`, `nc`, `telnet`   |
| 🧠 Layered thinking | OSI from bottom to top | Physical → Application            |

**Golden rule**: Test layer by layer. Networking rarely lies, humans do. 😆

---

### 📡 Connectivity Tools

**`ping` — Check if a host is reachable**

`ping` google.com
`ping `-c 4 8.8.8.8

✅ Tests ICMP reachability
❎ If DNS name fails but IP works → DNS issue

---

**`ip addr` / `ifconfig` — View network interfaces**

`ip addr show`
`ifconfig`

Use when checking:
- IP address assigned
- Correct subnet
- Interface is UP

---

**`ip link` — Interface state**

`ip link show`

Look for `state UP` or `DOWN`.

---

### 🚏 Routing Tools

**`ip route `— See routing table**

`ip route`

**`traceroute` — Trace the path to a host**

`traceroute google.com`


If packets stop mid-way → Routing / ISP problem.

---


### 🌍 DNS Troubleshooting

**`nslookup`**

`nslookup google.com`

**`dig`**

`dig google.com`
`dig google.com +trace`


**Tip:**
If `dig google.com` fails but `ping 8.8.8.8` works → DNS broken
Fix: change nameservers`/etc/resolv.conf`

---


### 🔌 Port & Service Debugging

**`netstat` / `ss` — View open ports**

`ss -tulpn`
`netstat -tulpn`

**Flags:**

| Flag | Meaning            |
| ---- | ------------------ |
| `-t` | TCP                |
| `-u` | UDP                |
| `-l` | Listening sockets  |
| `-p` | Process using port |
| `-n` | Numeric output     |

---

**`telnet` / `nc` — Test open ports**

**Test if server is listening on port 80:**

`telnet <server-ip> 80`
OR
`nc -zv <server-ip> 80`


✅ Connection opens = port reachable
❌ Times out = firewall / routing issue

---


### 📦 Packet Inspection

**`tcpdump` — Packet sniffer**

`sudo tcpdump -i eth0`
`sudo tcpdump -i eth0 port 443`

Useful for:
-  SSL / API debugging
-  Dropped packets
-  Network latency analysis

🧠 **Pro tip**: `tcpdump` + Wireshark combo =  YES

---


### 🧵 Curl / HTTP Debugging

**Test an HTTP endpoint:**

`curl http://example.com`
`curl -I https://example.com `  # Headers only
`curl -v https://example.com `  # Verbose

✅ Useful for API health, TLS checks, redirects.


---


### 🧭 Quick Troubleshooting Table

| Problem              | Likely Cause    | Command to Confirm       |
| -------------------- | --------------- | ------------------------ |
| Cannot ping gateway  | Wrong IP/Subnet | `ip addr`, `ip route`    |
| DNS name fails       | DNS misconfig   | `nslookup`, `dig`        |
| Port blocked         | Firewall/ACL    | `ss -tulpn`, `nc -zv`    |
| Site loads slowly    | Latency issues  | `traceroute`, `ping`     |
| SSL Errors           | Cert issues     | `curl -v https://...`    |
| Container can't talk | Docker network  | `docker network inspect` |

---


### 🧠 Real-World DevOps Tips
| Tip                              | Why it matters               |
| -------------------------------- | ---------------------------- |
| Use `8.8.8.8` for DNS check      | Bypass local DNS issues      |
| Check `/etc/hosts`               | Local override may break DNS |
| Monitor logs (`/var/log/syslog`) | Hidden networking messages   |
| Check SGs + NACLs (AWS)          | Cloud firewalls trick you 😅 |
| Document commands you try        | Saves your brain next time   |


---


## 💡 Summary

Networking is like detective work.
You don’t guess, you interrogate the network.

Ping it.
Trace it.
Sniff it.
Look at ports.
Fix the layer that’s broken.

---


