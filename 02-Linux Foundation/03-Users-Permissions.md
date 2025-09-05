# 👥 Linux Users & Permissions

Managing users and controlling access to files is one of the core responsibilities in Linux.  

---

## 📌 What
Linux is a **multi-user operating system** where permissions decide **who can do what** with files and directories.  

---

## 📌 Why
- To ensure security and prevent unauthorized access.  
- To share resources between users without exposing everything.  
- To enforce **principle of least privilege** in DevOps environments.  

---

## 📌 How

### 1. Users and Groups
- **User**: An account for login (`ubuntu`, `root`).  
- **Group**: Collection of users with similar permissions (`developers`, `admins`).  

Commands:
# Create new user
sudo adduser raj
# Create group
sudo groupadd devs
# Add user to group
sudo usermod -aG devs raj


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

2. File Permissions (rwx)

Each file/directory has three permission sets:

Owner

Group

Others

ls -l


Output example:

-rw-r--r-- 1 ubuntu devs 123 Sep 4 myfile.txt


rw- → Owner can read/write

r-- → Group can read

r-- → Others can read

3. chmod (Change Permissions)

Modify who can read/write/execute files.

chmod 755 script.sh   # rwxr-xr-x
chmod u+x script.sh   # add execute for user
chmod g-w file.txt    # remove write for group

4. chown (Change Ownership)

What: The chown command changes the owner or group of a file/directory.
Why: Sometimes files are created by root or another user, and you need to give ownership to the correct user.

Syntax:
chown [new_owner] file
chown [new_owner]:[new_group] file

Examples:
# Change file owner to user 'ubuntu'
sudo chown ubuntu myfile.txt

# Change both owner and group
sudo chown ubuntu:devs myfile.txt

# Change ownership recursively for a folder
sudo chown -R ubuntu:ubuntu /var/www/html


✅ Expected Output: Ownership of the file/folder updates to the specified user/group.

🧪 Practice Task

Create a file as root:

sudo touch /tmp/rootfile
ls -l /tmp/rootfile


(You will see owner as root)

Change the owner to your user (ubuntu):

sudo chown ubuntu /tmp/rootfile
ls -l /tmp/rootfile


Verify that now the file is owned by ubuntu.

Try changing a folder’s ownership recursively with -R.

✅ With users, groups, permissions, chmod, and chown, you now have the basics to manage Linux security effectively.
