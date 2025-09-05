# Networking Basics in Linux

## 🔹 What
Networking in Linux allows servers to **communicate** with each other and with the internet.  
It includes **IP addresses, DNS, ports, and firewall rules**.

---

## 🔹 Why
- DevOps engineers must **debug connectivity issues**.  
- Helps in managing **web servers, APIs, and databases**.  
- Needed for **secure SSH access** and service availability.

---

## 🔹 How

### 📌 Check Network Interfaces

ip a             # modern command to show interfaces
ifconfig         # older command (may need net-tools)

📌 Test Connectivity
ping google.com             # test network reachability
curl http://example.com     # fetch webpage
wget http://example.com     # download webpage

📌 Check Open Ports & Services
netstat -tulnp    # show listening ports (if installed)
ss -tulnp         # modern alternative

📌 DNS & Hosts
cat /etc/resolv.conf   # check DNS servers
cat /etc/hosts         # local hostname mappings

📌 SSH Basics
# Connect to remote server
ssh -i mykey.pem ubuntu@<server-ip>

# Copy files between local & remote
scp -i mykey.pem file.txt ubuntu@<server-ip>:/home/ubuntu/

🔹 Key Points

ip a → check IP address

ping → test connectivity

curl/wget → test HTTP/HTTPS requests

ss/netstat → check open ports & services

ssh & scp → secure access and file transfer

📌 Firewall Basics (Ubuntu with UFW)

sudo ufw status                # check firewall status
sudo ufw allow 22              # allow SSH
sudo ufw allow 80              # allow HTTP
sudo ufw allow 443             # allow HTTPS
sudo ufw deny 23               # block Telnet
sudo ufw enable                # enable firewall
sudo ufw disable               # disable firewall

📌 Firewall on CentOS/RHEL (firewalld)
sudo systemctl start firewalld
sudo systemctl enable firewalld
sudo firewall-cmd --permanent --add-port=22/tcp
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --reload
sudo firewall-cmd --list-all

