# How to Access EC2 Ubuntu via SSH

## What
Connect to your Ubuntu EC2 instance from your local computer using SSH.

## Why
To manage and configure the server remotely.

## How
### On Linux/Mac
```bash
chmod 400 mykey.pem
ssh -i mykey.pem ubuntu@<Public-IP>
