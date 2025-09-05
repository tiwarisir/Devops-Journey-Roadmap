# Control Processes and Services in Linux

Linux is a multitasking OS → multiple processes & services run at the same time.  
You must know how to monitor, start/stop, and manage them.  

---

## ⚙️ Processes

### See running processes
ps aux

Find a process by name
ps aux | grep nginx

Real-time process monitoring
top
htop   # if installed

Kill a process
kill 1234        # by PID
kill -9 1234     # force kill

🛠️ Services (systemd)

Most modern Linux distros use systemd to manage services.

Check status
systemctl status ssh

Start / Stop service
sudo systemctl start ssh
sudo systemctl stop ssh

Restart service
sudo systemctl restart ssh

Enable service (start on boot)
sudo systemctl enable ssh

Disable service
sudo systemctl disable ssh

🔍 What | Why | How
1. What are Processes & Services?

Processes: Running programs on the system.

Services: Background processes managed by systemd (e.g., SSH, Apache).

2. Why are They Important?

To keep applications running smoothly.

For troubleshooting crashes or high CPU usage.

To control which services auto-start on boot.

3. How to Manage Them?

Use ps, top for process monitoring.

Use systemctl for service management.

Kill or restart misbehaving processes.

✅ Example Scenario

Check which process is using high CPU:

top


Find process ID (PID) of nginx:

ps aux | grep nginx


Restart nginx service:

sudo systemctl restart nginx


👉 Once you know process & service management, you can keep Linux servers stable and healthy.
