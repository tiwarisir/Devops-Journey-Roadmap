# 02 - IP & Subnetting

Subnetting helps in dividing a large network into smaller, manageable networks.  
As a DevOps engineer, you will use subnetting daily while working with **AWS VPC, Kubernetes clusters, or office LANs**.

---

## 🧩 IP Address Structure

An IPv4 address has **two parts**:
- **Network ID** – Identifies the network
- **Host ID** – Identifies the device in that network

Example: `192.168.1.10/24`  
- Network ID = `192.168.1.0`  
- Host range = `192.168.1.1 – 192.168.1.254`  
- Broadcast = `192.168.1.255`  

---

## 📝 Subnet Mask

Subnet mask tells which portion of IP is **network** and which is **host**.

- `255.255.255.0` → `/24` (256 addresses, 254 usable hosts)  
- `255.255.0.0` → `/16` (65,536 addresses)  
- `255.0.0.0` → `/8` (16 million addresses)  

---

## 📊 CIDR (Classless Inter-Domain Routing)

CIDR notation (`/n`) defines how many bits are reserved for network.

| CIDR | Subnet Mask        | Hosts Usable |
|------|--------------------|--------------|
| /30  | 255.255.255.252    | 2            |
| /29  | 255.255.255.248    | 6            |
| /28  | 255.255.255.240    | 14           |
| /24  | 255.255.255.0      | 254          |
| /16  | 255.255.0.0        | 65,534       |

---

## 🛠️ Subnetting Example

You are given network: `192.168.1.0/24`  
- Requirement: 4 subnets  
- Solution: Borrow 2 bits → `/26`  
- Each subnet has 64 addresses (62 usable hosts)  

Subnets:  
1. 192.168.1.0/26 → Hosts 1–62  
2. 192.168.1.64/26 → Hosts 65–126  
3. 192.168.1.128/26 → Hosts 129–190  
4. 192.168.1.192/26 → Hosts 193–254  

---

## 🔧 Useful Tools

- `ipcalc <IP/CIDR>` → Quick subnet calculation (Linux)  
- Online calculators: `subnet-calculator.com`  
- Practice by hand → great for interviews & real scenarios  

---

## ✅ DevOps Relevance

- AWS VPC requires you to plan **CIDR blocks** (`10.0.0.0/16`, subnets like `/24`).  
- Kubernetes clusters use subnets for **pods & services**.  
- Office LAN requires subnetting to segment teams (HR, IT, Dev).  
- Avoids **IP conflicts** and improves network security.  

---
