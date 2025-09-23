# 04 - Firewall & Ports

A **firewall** controls what traffic is allowed **in** (ingress) and **out** (egress) of a system or network.  
Ports represent **communication endpoints** for applications.  

As a DevOps engineer, you will configure firewalls on Linux servers, cloud security groups, and Kubernetes network policies.

---

## 🔑 Common Ports

| Service        | Port | Protocol |
|----------------|------|----------|
| SSH            | 22   | TCP |
| HTTP           | 80   | TCP |
| HTTPS (SSL/TLS)| 443  | TCP |
| FTP            | 21   | TCP |
| DNS            | 53   | UDP/TCP |
| DHCP           | 67, 68 | UDP |
| MySQL          | 3306 | TCP |
| PostgreSQL     | 5432 | TCP |
| MongoDB        | 27017 | TCP |
| RDP (Windows)  | 3389 | TCP |

👉 Remember: TCP = reliable (web, SSH), UDP = fast but not guaranteed (DNS, streaming).

---

## 🔥 Linux Firewall Basics

### UFW (Uncomplicated Firewall) – Ubuntu/Debian

# Enable firewall
sudo ufw enable

# Allow SSH
sudo ufw allow 22/tcp

# Allow HTTP & HTTPS
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp

# Deny a port
sudo ufw deny 3306/tcp

# Check rules
sudo ufw status verbose
