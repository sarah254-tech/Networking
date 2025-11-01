#  📡🚦 Routing & Switching Fundamentals

Picture this:

Networking = roads.
Devices = cars.
Switches = traffic officers inside one town.
Routers = highway junctions connecting towns, cities, and countries.

As DevOps engineer, we must understand how data travels across networks, from our laptop to AWS, from pods inside Kubernetes, across VPCs, and through load balancers.

---

## 🧩 What is Switching?

Switching happens **inside a network** (LAN).
A **switch** connects devices within the same network and forwards traffic intelligently based on **MAC addresses**.

> **MAC Address** = device’s physical ID (like a fingerprint)
> Example: 3C:5A:B4:9F:82:11

## 📌 Switch Key Functions

| Concept              | Explanation                                   |
| -------------------- | --------------------------------------------- |
| **MAC learning**     | Switch learns which MAC lives on which port   |
| **Forwarding**       | Sends packets only where they need to go      |
| **Filtering**        | Drops or blocks unwanted traffic              |
| **Broadcast domain** | All devices connected on same network segment |

## 📌 Types of Switching

| Type          | Meaning                 |
| ------------- | ----------------------- |
| **Unicast**   | One-to-one traffic      |
| **Broadcast** | One-to-all on network   |
| **Multicast** | One-to-many subscribers |


---

## 🧠 Switch vs Hub (Why Switches Rule)
| Feature          | Hub                | Switch                       |
| ---------------- | ------------------ | ---------------------------- |
| Traffic Handling | Sends to all ports | Sends to correct device only |
| Performance      | Slow & inefficient | Fast & intelligent           |
| Security         | Poor               | Better — isolates data flows |

So if hubs are **megaphones**, switches are **whisperers** 


---

## 🚀 VLANs (Virtual LANs)

Switches can divide a network into logical groups called **VLANs**.

> Think of it as: separate offices inside the same building

| VLAN Benefit      | Why it matters                    |
| ----------------- | --------------------------------- |
| Security          | Isolate sensitive traffic         |
| Reduce Broadcasts | Better performance                |
| Segmentation      | Dev/Prod separation in cloud      |
| Flexibility       | Group users by need, not location |


Example VLAN IDs:

- 10 = Finance

- 20 = Development

- 30 = Guest Wi-Fi

> Cloud equivalent: AWS VPC Subnets


---

## 🛣 What is Routing?

Routing connects **different networks** together.

If switching is local streets, routing is **highways connecting cities**.

A **router** makes decisions based on **IP addresses**.

> **IP Address** = Home Address
> **Router** = GPS Navigation System

---

## 🚚 How Routing Works (High-Level)

When your PC sends data to another network:

1. Packet hits your default gateway (router)

2. Router checks routing table

3. Chooses best path

4. Sends packet forward

5. Packet hops through multiple routers

6. Arrives at destination & returns response

---

## 🗺 Routing Table Example

In linux terminal: `ip route show`

Example of output:

`nginx`

    default via 192.168.1.1 dev wlan0
    192.168.1.0/24 dev wlan0 proto kernel scope link src 192.168.1.
    
    | Field                     | Meaning         |
| ------------------------- | --------------- |
| default via `192.168.1.1` | Default gateway |
| `192.168.1.0/24`          | Local network   |
| `wlan0`                   | Wi-Fi interface |
| `192.168.1.100`           | Device IP       |


---

## 🧭 Types of Routing

| Type                | Meaning                       |
| ------------------- | ----------------------------- |
| **Static Routing**  | Manually configured routes    |
| **Dynamic Routing** | Routers auto-learn best paths |

### 🔥 Dynamic Routing Protocols

| Protocol                                               | Purpose                                          |
| ------------------------------------------------------ | ------------------------------------------------ |
| **OSPF** (Open Shortest Path First)                    | Finds shortest path inside enterprise network    |
| **BGP** (Border Gateway Protocol)                      | Internet routing, connects ISPs & cloud networks |
| **EIGRP** (Enhanced Interior Gateway Routing Protocol) | Cisco smart routing inside networks              |
| **RIP** (Routing Information Protocol)                 | Simple, old, hop-count-based routing             |


> As DevOps, we pay special attention to BGP, cloud uses it for global traffic routing

---

## 🏎 Routing Metrics (How routers pick best path)

Routers decide path based on:

- Distance (hops)

- Speed (bandwidth)

- Delay (latency)

- Reliability

- Cost/priority

It's like choosing the fastest route on Google Maps🗺

---

## 🔐 NAT (Network Address Translation)

Private devices share one public IP translating addresses.

| NAT Type           | Purpose                                        |
| ------------------ | ---------------------------------------------- |
| **PAT / Port NAT** | Many devices share 1 public IP (home internet) |
| **Static NAT**     | One-to-one mapping for servers                 |
| **Dynamic NAT**    | Pool of public IPs rotated                     |

> Cloud version: AWS NAT Gateway, GCP Cloud NAT

---

## 🌩 Routing in the Cloud (DevOps Must-Know)

| Cloud Component  | Real-world Equivalent                           |
| ---------------- | ----------------------------------------------- |
| VPC              | Campus network                                  |
| Subnets          | Network floors/rooms                            |
| Route Table      | Router GPS table                                |
| Internet Gateway | Public internet connection                      |
| NAT Gateway      | Access to internet without exposing private IPs |
| Load Balancer    | Traffic control, distributes requests           |
| Transit Gateway  | Cloud Router for multi-VPC                      |

---

## 🧪 Useful Linux Commands

| Command                 | Use                      |
| ----------------------- | ------------------------ |
| `ip addr`               | Show network interfaces  |
| `ip route`              | View routing table       |
| `traceroute google.com` | Show path to destination |
| `ping`                  | Test connectivity        |
| `arp -a`                | Show MAC ↔ IP table      |


---

## 🎯 Summary

| Topic            | Key Point                            |
| ---------------- | ------------------------------------ |
| Switching        | Moves traffic inside a network (MAC) |
| VLANs            | Network segmentation                 |
| Routing          | Connects networks (IP)               |
| Static Routing   | Manual path                          |
| Dynamic Routing  | Auto-learning path                   |
| BGP              | Protocol that runs the internet      |
| NAT              | Private → Public IP translation      |
| Cloud Networking | Route tables, VPC, subnets           |


> Switch = Works inside neighborhood
> Router = Connects neighborhoods
> BGP = Connects the world 🌍







