# Users & Permissions in Linux

## 🔹 What
Linux is a **multi-user operating system**, meaning multiple users can work on the same system simultaneously.  
Users, groups, and permissions control **who can access or modify files and processes**.

---

## 🔹 Why
- Security: Prevents unauthorized access.  
- Organization: Different teams/users can work safely.  
- Administration: DevOps engineers must manage users & file access on servers.

---

## 🔹 How

### 📌 Check Current User & Groups
```bash
whoami      # show current user
id          # show UID, GID, groups
groups      # show groups of current user

📌 User Management
sudo adduser devuser          # create user
sudo passwd devuser           # set password
sudo userdel devuser          # delete user

Switch user:
su - devuser

📌 Permissions in Linux

r (read), w (write), x (execute)

Permissions apply to User (owner), Group, Others
Check file permissions
ls -l

📌 Change Permissions
chmod 755 script.sh   # rwxr-xr-x
chmod 644 file.txt    # rw-r--r--

👉 Numeric permission values:

7 = rwx

6 = rw-

5 = r-x

4 = r--

📌 Change Ownership

chown user:group file.txt

✅ Example:
sudo chown devuser:devuser app.log

🔹 Key Points

Every file has an owner, group, and others.

chmod → change permissions

chown → change ownership

Managing users & permissions is critical for system security.
