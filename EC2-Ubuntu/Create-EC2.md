# How to Create an EC2 Ubuntu Instance

## What
Launch an Ubuntu server on AWS using the EC2 service.

## Why
To host scalable, secure, and on-demand Linux servers in the cloud.

## How
1. Log in to **AWS Management Console**.
2. Go to **EC2 → Launch Instance**.
3. Select **Ubuntu AMI** (prefer LTS version).
4. Choose instance type (e.g., `t2.micro` for free tier).
5. Configure storage, tags, and security groups (allow SSH on port 22).
6. Create & download a `.pem` key pair.
7. Launch the instance.
