# VPN & VLAN

In networking, **VPN (Virtual Private Network)** and **VLAN (Virtual Local Area Network)** are two key concepts that serve similar goals — *security and network segmentation* — but work at different layers and scales.

---

## 🌐 VPN (Virtual Private Network)

### 🔸 What it is
A **VPN** creates a **secure, encrypted tunnel** between devices over the internet.  
It allows users or offices to send private data securely across public networks.

---

### 🔹 Types of VPN

| Type | Description | Example |
|-------|--------------|----------|
| **Site-to-Site VPN** | Connects two office networks securely | Head Office ↔ Branch Office |
| **Remote Access VPN** | Individual users connect securely from anywhere | Work-from-home users |
| **Client-to-Site VPN** | Users connect via VPN client software | IT staff accessing company servers |
| **Cloud VPN** | Connects on-premises to cloud | AWS Site-to-Site VPN |

---

### 🔹 Common VPN Protocols

| Protocol | Port | Description |
|-----------|------|-------------|
| **IPSec** | 500 / 4500 | Used by Cisco, Azure, AWS — secure and reliable |
| **OpenVPN** | 1194 | Open source, flexible, and widely supported |
| **WireGuard** | 51820 | Modern, lightweight, high performance |
| **SSL VPN** | 443 | Uses HTTPS tunnel (works behind most firewalls) |

---

### 🔹 Real-World Example

**Scenario:**  
Your office in Gurgaon needs secure connectivity to your AWS VPC.

**Solution:**
- Create an **AWS Site-to-Site VPN**
- Configure your **office firewall/router** (FortiGate, Mikrotik, or Sophos)
- Exchange **Tunnel IPs** and **Pre-shared keys**
- Route only internal subnets (e.g., 192.168.1.0/24 → 10.0.0.0/16)

✅ **Result:** Both networks behave as a single private network securely connected.

---

### 🔹 DevOps Use Cases

| Use Case | Purpose |
|-----------|----------|
| Secure access to AWS private subnets | Avoid public exposure |
| Developers connecting to staging servers | Controlled access |
| Remote admins managing Kubernetes clusters | Secure via VPN only |
| Hybrid cloud between AWS & Azure | Site-to-site connection |

---

## 🖧 VLAN (Virtual Local Area Network)

### 🔸 What it is
A **VLAN** is a **logical segmentation** of a network within a single switch.  
It separates departments or users into isolated **broadcast domains** without extra hardware.

**Example:**
| Department | VLAN ID |
|-------------|----------|
| HR | 10 |
| IT | 20 |
| Guest Wi-Fi | 30 |

Each group acts as if it has its own private switch, even though physically all are on the same device.

---

### 🔹 VLAN Configuration Example

```bash
# Cisco Switch Example
Switch(config)# vlan 10
Switch(config-vlan)# name HR
Switch(config)# vlan 20
Switch(config-vlan)# name IT
Switch(config)# interface fa0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10
