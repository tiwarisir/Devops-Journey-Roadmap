# Linux Filesystem Introduction

Linux follows a **hierarchical filesystem structure** — everything starts from `/` (root).  
Understanding this layout is very important for working with servers.  

---

## 🌳 Filesystem Tree Overview
- `/` → Root directory, base of everything.
- `/bin` → Essential user binaries (commands like `ls`, `cp`, `mv`).
- `/sbin` → System binaries (for admins, e.g., `iptables`, `reboot`).
- `/etc` → Configuration files (e.g., `/etc/ssh/sshd_config`).
- `/home` → User home directories (`/home/ubuntu`).
- `/root` → Root user’s home directory.
- `/var` → Variable data (logs, mail, spool).
- `/tmp` → Temporary files, cleared on reboot.
- `/usr` → User programs and libraries.
- `/lib` → Shared libraries required by system.
- `/boot` → Boot loader files (Linux kernel, GRUB).
- `/dev` → Device files (disks, USB, etc.).
- `/proc` → Virtual filesystem showing processes info.
- `/sys` → Kernel and device information.

---

## 🔍 What | Why | How

### 1. What is the Linux Filesystem?
It’s the way Linux organizes files into directories, starting from root `/`.

### 2. Why is it Important?
- To know **where configs, logs, and binaries live**.  
- Helps in troubleshooting (e.g., checking `/var/log` for errors).  
- Useful for installing, editing, or debugging services.

### 3. How to Explore It?
cd /
ls

**Check logs**
cd /var/log
ls -lh

**See system processes info**
cd /proc
ls
cat /proc/cpuinfo

**Identify your home directory**
cd ~
pwd


