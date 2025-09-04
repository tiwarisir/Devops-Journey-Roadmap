# How to Recover Access if PEM File is Lost

## What
Recover access to your EC2 instance when the private key (`.pem`) file is lost.

## Why
Without the PEM key file, SSH login will not work.

## How
1. Stop the instance.
2. Detach its root volume.
3. Attach that volume to another EC2 instance where you have access.
4. Mount the volume and edit the `~/.ssh/authorized_keys` file.
   - Add a new public key (from a new key pair).
5. Detach the volume and reattach it to the original instance.
6. Start the instance and connect using the new key.
