# Firewall and NAT (Network Security Basics)

Network security is one of the most essential topics for DevOps and IT engineers.  
Two key concepts that protect and control network traffic are **Firewall** and **NAT (Network Address Translation).**

---

## 🧱 Firewall

### 🔸 What is a Firewall?
A **Firewall** is a security system that **monitors and controls incoming and outgoing traffic** based on predefined rules.  
It acts as a barrier between your **internal trusted network** and **untrusted networks** like the internet.

---

### 🔹 Types of Firewalls

| Type | Description | Example |
|-------|-------------|----------|
| **Packet Filtering Firewall** | Filters packets based on IP, port, and protocol | Basic routers |
| **Stateful Firewall** | Tracks connection states for smarter filtering | Linux `iptables`, UFW |
| **Proxy Firewall** | Intermediary that inspects traffic at application level | Squid proxy |
| **Next-Gen Firewall (NGFW)** | Deep packet inspection, IDS/IPS, application control | FortiGate, Palo Alto, Sophos |

---

### 🔹 Firewall Rules

A firewall rule defines **what kind of traffic is allowed or blocked**.

Example (Linux `iptables`):
# Allow SSH
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT

# Allow HTTP and HTTPS
sudo iptables -A INPUT -p tcp -m multiport --dports 80,443 -j ACCEPT

# Block everything else
sudo iptables -A INPUT -j DROP


🔹 Firewall in Cloud (AWS / Azure / GCP)

In cloud environments, firewall functionality is provided by Security Groups and Network ACLs.

Component	Level	Description
Security Group	Instance-level	Stateful rules (e.g., allow port 22 inbound)
Network ACL	Subnet-level	Stateless rules for inbound/outbound
Firewall Manager	Organization-level	Centralized policy control

Example (AWS SG Rule):

Direction	Protocol	Port	Source
Inbound	TCP	22	203.0.113.10/32
Inbound	TCP	80	0.0.0.0/0
Outbound	All	All	0.0.0.0/0

🌍 #** NAT (Network Address Translation)**
🔸** What is NAT?**

NAT allows multiple devices on a private network to share a single public IP address when accessing the internet.
It hides internal IPs from external users — adding a security layer and conserving public IPs.

🔹 **Types of NAT**
Type	Description	Example
**Static NAT	One private IP** → One public IP	Web server with fixed IP
**Dynamic NAT	Private IPs →** Public IP pool	Large office networks
PAT (Port Address Translation)	Many private IPs → One public IP with port mapping	Home router / Office gateway
🔹 Example: How NAT Works

Office LAN:

Internal IPs: 192.168.1.10, 192.168.1.20

Public IP: 203.0.113.25

When user 192.168.1.10 browses Google:

Router replaces 192.168.1.10 → 203.0.113.25:12345

Response returns to router → router maps back to original user

✅ This is Source NAT (SNAT).

🔹 Common NAT Configurations (Linux)
# Enable IP forwarding
sudo sysctl -w net.ipv4.ip_forward=1

# Set up NAT (masquerade)
sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE

🔐 Real-World Examples
Scenario	Technology Used
Allow only SSH & HTTPS traffic on server	UFW or iptables rules
Secure AWS EC2 instance	Security Groups
Isolate web and DB tiers	Private Subnets + NACLs
Connect multiple branch offices	NAT with VPN
Enable Internet for local LAN	NAT (Masquerade) on router

🧠 **Key Differences**
Feature                	Firewall	                    NAT
Purpose   	Controls traffic flow (allow/deny)	 Translates IPs (hide internal IPs)
Layer	               Network                     Transport	Network
Security	            Yes	                       Indirectly

Example	      iptables, UFW, Security Groups	   MASQUERADE, SNAT, DNAT

⚙️ Quick Checks
# View firewall rules
sudo iptables -L -n -v

# Check UFW status
sudo ufw status verbose

# Display NAT table
sudo iptables -t nat -L -n -v


💡 Remember:

Firewall = Gatekeeper (controls what goes in/out)

NAT = Translator (hides internal network details)
