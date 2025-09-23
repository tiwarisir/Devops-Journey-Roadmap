# 01 - Network Basics

Networking is the foundation of all IT systems. Without networking, servers, cloud, and applications cannot communicate.  
As a DevOps engineer, you must understand how networks work to deploy and manage infrastructure.

---

## 🌐 OSI Model (7 Layers)

The **OSI model** helps us understand how data flows in a network.

1. **Physical** – Cables, WiFi, hardware  
2. **Data Link** – Ethernet, MAC addresses, ARP  
3. **Network** – IP addressing, routing  
4. **Transport** – TCP, UDP  
5. **Session** – Connections between applications  
6. **Presentation** – Data formatting, encryption (SSL/TLS)  
7. **Application** – User-level apps (HTTP, DNS, SSH)  

👉 As DevOps, focus mainly on **Layers 3–7**.

---

## 📍 IP Addressing

- **IPv4**: `192.168.1.10` (32-bit, 4 billion addresses)  
- **IPv6**: `2001:0db8:85a3::8a2e:0370:7334` (128-bit, future of internet)  
- **Private IP ranges**:  
  - `10.0.0.0 – 10.255.255.255`  
  - `172.16.0.0 – 172.31.255.255`  
  - `192.168.0.0 – 192.168.255.255`  
- **Public IP**: Unique address assigned by ISP, reachable from the internet.  

---

## 🔄 Important Terms

- **Gateway** – Device that connects local network to other networks (usually router).  
- **Subnet** – Divides a network into smaller sections.  
- **NAT (Network Address Translation)** – Converts private IP to public IP for internet access.  
- **CIDR Notation** – Example: `192.168.1.0/24` (255.255.255.0 mask).  

---

## 🛠️ Common Tools

- `ping` → Check connectivity  
- `traceroute` / `tracert` → Path of packets  
- `nslookup` / `dig` → DNS lookup  
- `ifconfig` / `ip addr` → Show network interfaces  
- `netstat -tulnp` / `ss` → Active ports & services  
- `curl` → Test HTTP requests  

---

## ✅ DevOps Relevance

- Understanding **IP addressing** is key for cloud (AWS VPC, subnets).  
- OSI model helps in debugging (is it app issue? network? firewall?).  
- Tools like `ping`, `curl`, `netstat` are essential in troubleshooting deployments.  

---
