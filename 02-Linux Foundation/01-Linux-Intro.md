# Linux Introduction

## 🔹 What is Linux?
Linux is an **open-source operating system** based on the Unix architecture.  
It acts as a bridge between computer hardware and software applications.

- Kernel → Core of the OS (manages CPU, memory, devices)  
- Shell → Interface to interact with the Kernel (bash, sh, zsh)  
- Distributions → Variants of Linux (Ubuntu, CentOS, Amazon Linux, Debian, etc.)

---

## 🔹 Why Linux is Important in DevOps?
- Most **servers in cloud (AWS, GCP, Azure)** run on Linux.  
- Core DevOps tools like **Docker, Kubernetes, Ansible, Jenkins** are Linux-based.  
- Provides better **performance, security, and automation** capabilities.  
- Essential for **troubleshooting production issues**.

---

## 🔹 How to Check Linux System Information?
Run these commands inside your Linux VM / EC2 instance:

# Show system name, kernel version
uname -a

# Show Linux distribution details
cat /etc/os-release

# Show logged-in user
whoami

# Show current directory
pwd
