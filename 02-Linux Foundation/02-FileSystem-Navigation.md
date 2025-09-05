# Linux Filesystem & Navigation

## 🔹 What is Linux Filesystem?
The Linux filesystem is a **hierarchical tree structure** that starts from `/` (root directory).  
Everything in Linux is represented as a **file** (text files, devices, processes, sockets).

---

## 🔹 Why is it Important?
- Helps you **locate files and configs** quickly.  
- Essential for **system administration & troubleshooting**.  
- Needed for **installing apps, editing configs, and reading logs**.

---

## 🔹 How to Navigate Linux Filesystem?

### 📂 Common Directories
| Directory | Purpose |
|-----------|----------|
| `/`       | Root directory (top of FS tree) |
| `/home`   | User home directories |
| `/etc`    | System & application configuration files |
| `/var`    | Logs, spool, cache |
| `/usr`    | Installed software & libraries |
| `/bin`    | Essential system binaries |
| `/tmp`    | Temporary files |

---

### 📌 Navigation Commands
pwd          # show current directory
ls           # list files
ls -l        # detailed list
ls -a        # show hidden files
cd /etc      # go to /etc directory
cd ~         # go to home directory
cd ..        # go one level back


📌 File Viewing Commands

cat file.txt         # display entire file
less file.txt        # scroll inside file
head -n 5 file.txt   # show first 5 lines
tail -n 5 file.txt   # show last 5 lines
tail -f /var/log/syslog   # live logs

✅ Example:

$ head -n 3 /etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin

📌 File Operations

touch test.txt      # create empty file
mkdir testdir       # create directory
cp file1 file2      # copy file
mv file1 file2      # rename/move file
rm file.txt         # delete file
rm -r dir/          # delete directory

🔹 Key Points

/ (root) is the starting point of everything.

Learn to use ls, cd, pwd, cat, less, head, tail.

File operations (cp, mv, rm) are core skills for Linux admins.

