# How to Access EC2 Ubuntu via SSH

## What
Connect to your Ubuntu EC2 instance from your **Windows computer** using SSH.

## Why
To remotely log in and manage the EC2 Ubuntu instance.

## How

### Step 1: Download PEM Key
- When creating the EC2 instance, AWS provides a `.pem` key file.
- Save it in a safe location, e.g., `C:\Users\<YourName>\Desktop\new.pem`.

---

### Step 2: Open PowerShell
- Press `Win + S`, type **PowerShell**, and open it.

---

### Step 3: Run SSH Command
Use the following format:
```powershell
ssh -i "C:\Users\<YourName>\Desktop\new.pem" ubuntu@<Public-IP>
