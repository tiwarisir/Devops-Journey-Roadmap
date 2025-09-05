# Package Management in Linux

## 🔹 What
A **package** is a software application or library bundled for installation.  
Package managers are tools that help install, update, and remove software.

- Debian/Ubuntu → `apt`  
- RHEL/CentOS → `yum` or `dnf`

---

## 🔹 Why
- To install and manage required software on servers.  
- To keep systems updated with latest security patches.  
- To remove unwanted or vulnerable software.

---

## 🔹 How

### 📌 Update Package Index

# Ubuntu / Debian
sudo apt update

# CentOS / RHEL
sudo yum check-update

📌 Install Software
# Ubuntu / Debian
sudo apt install nginx -y

# CentOS / RHEL
sudo yum install httpd -y

📌 Remove Software

# Ubuntu / Debian
sudo apt remove nginx -y

# CentOS / RHEL
sudo yum remove httpd -y

📌 Upgrade System
# Ubuntu / Debian
sudo apt upgrade -y

# CentOS / RHEL
sudo yum update -y

📌 Search Packages

apt search python3
yum search git

📌 Check Installed Packages
dpkg -l | grep nginx     # Debian/Ubuntu
rpm -qa | grep httpd     # RHEL/CentOS

🔹 Key Points

Use apt for Ubuntu/Debian, yum/dnf for CentOS/RHEL.

Always run apt update or yum check-update before installation.

Regular updates are critical for security & stability.

