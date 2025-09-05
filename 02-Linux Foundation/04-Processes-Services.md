# Processes & Services in Linux

## 🔹 What
- **Process** → A running program (active in memory).  
- **Service (Daemon)** → A special process that runs in the background (e.g., web server, database).  

---

## 🔹 Why
- To **monitor CPU, memory usage**.  
- To **start/stop/restart services** like `nginx`, `mysql`.  
- For **troubleshooting server performance issues**.

---

## 🔹 How

### 📌 Process Management
```bash
ps aux          # show all running processes
top             # real-time process monitoring
htop            # improved top (if installed)
kill -9 1234    # kill process with PID

📌 Jobs (Foreground & Background)

sleep 500 &     # run process in background
jobs            # list background jobs
fg %1           # bring job to foreground
bg %1           # resume job in background

📌 Services (Systemd)

Most modern Linux distros (Ubuntu 16+, CentOS 7+) use systemd.

sudo systemctl status nginx    # check service status
sudo systemctl start nginx     # start service
sudo systemctl stop nginx      # stop service
sudo systemctl restart nginx   # restart service
sudo systemctl enable nginx    # auto-start on boot
sudo systemctl disable nginx   # disable auto-start

📌 Check Ports & Services
netstat -tulnp   # show open ports and services
ss -tulnp        # modern alternative to netstat

🔹 Key Points

ps, top, htop → monitor processes

kill → stop a process by PID

systemctl → manage services (start, stop, restart, enable)

ss/netstat → check ports & services
