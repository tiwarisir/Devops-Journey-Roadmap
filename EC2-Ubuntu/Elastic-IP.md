# How to Assign Elastic IP to EC2

## What
Attach a static public IP to your EC2 instance.

## Why
Without an Elastic IP, the public IP changes every time you stop/start the instance.

## How
1. In AWS Console → **EC2 → Elastic IPs → Allocate Elastic IP**.
2. Select the running instance.
3. Click **Associate Elastic IP**.
4. Use this fixed IP to access the instance anytime.
