# Manage Users and File Access in Linux

In Linux, **users, groups, and permissions** control who can access what.  
This is critical for multi-user systems and server security.  

---

## 👤 User Management

### Create a new user

sudo adduser raj

Switch user
su - raj

Delete a user
sudo deluser raj

👥 Group Management
Create a group
sudo groupadd developers

Add user to group
sudo usermod -aG developers raj

See group memberships
groups raj

🔑 File Permissions

Linux uses r (read), w (write), x (execute) for access control.

Check permissions
ls -l
-rw-r--r--  1 ubuntu ubuntu  1234 Sep  4  file.txt

Change permissions
chmod 755 script.sh

Change ownership
sudo chown raj:developers project.txt

📂 Permission Breakdown

r = read

w = write

x = execute

Example: -rwxr-xr--

Owner: read, write, execute

Group: read, execute

Others: read

🔍 What | Why | How
1. What is User & File Access Management?

The way Linux controls who can log in and what files they can access.

2. Why is it Important?

Prevents accidental or malicious changes.

Enforces security in multi-user systems.

Gives flexibility (developers, admins, services).

3. How to Use?

Create/manage users and groups.

Apply correct file permissions.

Regularly audit with ls -l and groups.

✅ Example Scenario

Create a user for developer:

sudo adduser dev1


Create a group for project:

sudo groupadd projectA
sudo usermod -aG projectA dev1


Assign file to group:

sudo chown dev1:projectA code.py
chmod 770 code.py


🔒 Now only dev1 + projectA members can read/write/execute.

👉 Mastering users & permissions = secure and well-organized server.
