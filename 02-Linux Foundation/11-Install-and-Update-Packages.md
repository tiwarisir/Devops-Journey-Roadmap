# Install and Update Packages in Linux

Linux software is installed and managed through **package managers**.  
Different distros use different package managers (e.g., APT, YUM, DNF).  

---

## 📦 Package Managers by Distro
- **Debian/Ubuntu** → `apt`  
- **Red Hat/CentOS/Fedora** → `yum` or `dnf`  
- **SUSE** → `zypper`  

---

## 🛠️ APT (Debian/Ubuntu)

### Update package list
sudo apt update

Upgrade installed packages
sudo apt upgrade

Install a package
sudo apt install nginx

Remove a package
sudo apt remove nginx

Remove with config files
sudo apt purge nginx

Search package
apt search apache2

🛠️ YUM/DNF (CentOS/RedHat/Fedora)
Update system
sudo yum update
# or
sudo dnf upgrade

Install package
sudo yum install httpd

Remove package
sudo yum remove httpd

Search package
yum search mysql

🔍 What | Why | How
1. What is Package Management?

A way to install, update, and remove software on Linux.

2. Why is it Important?

Keeps system secure with updates.

Easy installation (no manual downloads).

Resolves dependencies automatically.

3. How to Use?

Choose the package manager based on distro.

Regularly run update/upgrade.

Search and install required software.

✅ Example Scenario

Update your Ubuntu server:

sudo apt update && sudo apt upgrade -y


Install Apache:

sudo apt install apache2 -y


Remove Apache:

sudo apt remove apache2 -y


👉 With package managers, Linux software handling becomes fast, safe, and reliable.
