# 🌐 IP Addressing Deep Dive  
_A fun, friendly, and DevOps ready guide_

Welcome to the world of **IP Addressing** where computers get their names on the internet. Without IPs, devices would just be yelling into the void.

## 🧠 What is an IP Address?

An **IP Address** (Internet Protocol Address) is a unique numerical label assigned to a device in a network so it can communicate with others. Think of it as your house address. Without it, Amazon would never deliver your goodies.

Two main versions exist:

| Version | Format | Total Addresses | Example |
|--------|--------|----------------|--------|
| IPv4 | 32 bit (4 octets) | About 4.3 billion | `192.168.1.10` |
| IPv6 | 128 bit | About 340 undecillion (massive!) | `2001:db8:85a3::8a2e:370:7334` |

## 📦 IPv4 Breakdown

IPv4 addresses are split into **4 octets** separated by dots:  
`A.B.C.D` = 8 bits each = 32 bits total

Example: 

`11000000.10101000.00000001.00001010`
`192.168.1.10`


### ✅ Private vs Public IPs

| Type | Description | Examples |
|------|------------|---------|
| Public | Used on the internet | `102.89.5.1` |
| Private | Used inside local networks | `192.168.0.0/16`, `10.0.0.0/8`, `172.16.0.0/12` |

---

### 🎭 NAT - The Secret Agent

**NAT** (Network Address Translation) lets private IPs talk to the internet by translating them to public ones. Like a receptionist who speaks to visitors on your behalf.

- Saves public IPs
- Adds security
- Essential in home and cloud networks

---

### 🔢 IP Classes (Old School but useful)

| Class | Range | Use Case |
|-------|-------|---------|
| A | 1.0.0.0 to 126.0.0.0 | Very large networks |
| B | 128.0.0.0 to 191.255.0.0 | Medium networks |
| C | 192.0.0.0 to 223.255.255.0 | Small networks |
| D | 224.0.0.0 to 239.0.0.0 | Multicast |
| E | 240.0.0.0 to 255.255.255.255 | Experimental |

---

### 🧮 Subnetting Starter Pack

Subnetting splits networks to improve efficiency and security.

Example:  
`192.168.1.0/24` means  
- Network bits: 24  
- Host bits: 8  
- Hosts available: `2^8 - 2 = 254`

Helpful CIDR table:

| CIDR | Hosts Available |
|-----|----------------|
| /24 | 254 |
| /25 | 126 |
| /26 | 62 |
| /27 | 30 |
| /30 | 2 (point to point) |

### 👉 Common Subnet Masks

| Mask | CIDR |
|------|-----|
| 255.255.255.0 | /24 |
| 255.255.0.0 | /16 |
| 255.0.0.0 | /8 |

---

### ✨ Practical Examples

#### In linux terminal: Display IP

`ip addr show`

##### `ip addr show` Output

| Section | Meaning |
|--------|--------|
`lo` | Local loopback network used inside your computer only |
`inet 127.0.0.1` | Localhost IPv4 address |
Interface name (`ens33`) | The actual network card your machine uses |
`inet 192.168.x.x/24` | Private IP used inside your LAN (not internet accessible) |
`inet6 fe80::` | Local IPv6 address |
`link/ether` | The device MAC address (unique hardware identifier) |

> 🚨 Pro Tip: When sharing screenshots, hide MAC address and private IP for security hygiene.

---

#### Assign IP

`sudo ip addr add 192.168.10.5/24 dev eth0`

---

#### Ping a host

`ping google.com`

![alt text](image-1.png)


| Output Part                          | Meaning                                                       |
| ------------------------------------ | ------------------------------------------------------------- |
| `PING google.com (142.xxx.xxx.xxx)`  | DNS resolved `google.com` to an IP address                    |
| `64 bytes from ...`                  | Response received — network is working                        |
| `icmp_seq=1`                         | Packet sequence number (which reply it is)                    |
| `ttl=XX`                             | Time-to-live; how many network hops remain before packet dies |
| `time=XX ms`                         | Round-trip time (latency) — lower is better                   |
| `ping: ctrl+c to stop`               | Stops the continuous ping                                     |
| `--- google.com ping statistics ---` | Summary of test results                                       |
| `packets transmitted/received`       | Shows if any packets were lost                                |
| `packet loss 0%`                     | No loss = stable network                                      |
| `rtt min/avg/max/stddev`             | Speed & consistency of network responses                      |

###### 💡 Important Concepts

- Ping uses ICMP protocol

- Checks connectivity + DNS + latency

- 0% packet loss + low ms = good network

**If ping fails, issue might be DNS, network cable/Wi-Fi, firewall, or gateway.**

---

#### Check public IP

`curl ifconfig.me`

---


### 📦 Bits vs Bytes — What's the Difference?

These two can really confuse a junior engineer, here is a short note on their differences.

| Term | Symbol | Size | Used For |
|------|--------|------|---------|
**Bit** | `b` | 1 binary digit (0 or 1) | Network speed, data transmission |
**Byte** | `B` | 8 bits | File size, memory, storage |

Think of it like this:

- **Bit = a single grain of rice**
- **Byte = a spoonful (8 grains)**

---

### ✅ Why It Matters

| Example | Means |
|--------|-------|
`100 Mbps` = 100 **Megabits per second** | Internet/network speed |
`100 MB` = 100 **Megabytes** | File size |

> ⚠️ **1 Byte = 8 Bits**  
So, if your internet is **100 Mbps**, your **max download speed ≈ 12.5 MBps**

📌 Calculation:  
`100 Mbps ÷ 8 = 12.5 MBps`

---

### 🧠 Quick Memory Trick

| Phrase | Helps you remember |
|-------|--------------------|
**b = bit = tiny** | lowercase letter, smaller unit  
**B = Byte = bigger** | uppercase letter, bigger unit  

---

### 💡 DevOps Note

In networking configs and speed tests:

- Bandwidth is measured in **bits**
- Storage/Memory is measured in **bytes**

You'll see terms like:

- `Kb`, `Mb`, `Gb` (kilobits, megabits, gigabits)
- `KB`, `MB`, `GB` (kilobytes, megabytes, gigabytes)

Different capitalization = **BIG difference**

---

You now understand why your ISP says **100 Mbps**, but your browser shows **12 MB/s** 



