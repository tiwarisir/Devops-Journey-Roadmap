# TCP vs UDP

**TCP (Transmission Control Protocol)** and **UDP (User Datagram Protocol)** are the two most common transport layer protocols (Layer 4 in the OSI model).

They define **how data travels** between devices over a network — reliability, order, and speed.

---

## ⚙️ TCP (Transmission Control Protocol)

### 🔸 Characteristics
- **Connection-oriented** → Establishes a connection before sending data  
- **Reliable** → Ensures delivery of packets  
- **Error-checking & acknowledgment**  
- **Order maintained** – Packets arrive in the same sequence  

### 🔹 Common Use Cases
| Application | Port | Description |
|--------------|------|-------------|
| HTTP / HTTPS | 80 / 443 | Web traffic |
| SSH | 22 | Secure shell access |
| FTP | 21 | File transfer |
| SMTP | 25 | Email delivery |

### 🔹 TCP Handshake (3-way)
1. **SYN** → Client requests connection  
2. **SYN-ACK** → Server acknowledges  
3. **ACK** → Connection established  

📈 Reliable but slightly slower due to overhead.

---

## ⚡ UDP (User Datagram Protocol)

### 🔸 Characteristics
- **Connectionless** → Sends data without handshake  
- **Unreliable** → No acknowledgment or retransmission  
- **Faster** → Lower latency, minimal overhead  
- **Order not guaranteed**  

### 🔹 Common Use Cases
| Application | Port | Description |
|--------------|------|-------------|
| DNS | 53 | Domain name resolution |
| DHCP | 67–68 | IP assignment |
| VoIP / Video Streaming | 16384–32767 | Real-time media |
| Gaming | varies | Low latency communication |

🎯 Great for speed-sensitive apps where small packet loss is acceptable.

---

## 🔍 DevOps Relevance

| Scenario | Protocol | Why |
|-----------|-----------|-----|
| Web Servers / APIs | **TCP** | Reliability & data integrity |
| DNS resolution | **UDP** | Speed; no need for connection |
| Monitoring (SNMP) | **UDP** | Lightweight data |
| Streaming / VoIP | **UDP** | Real-time performance |
| SSH / SFTP access | **TCP** | Secure, ordered data transfer |

---

## 🧠 Quick Commands

```bash
# Check listening TCP/UDP ports
sudo netstat -tulnp
# or
sudo ss -tulnp

# Check connectivity on specific port
nc -zv example.com 80   # TCP
nc -u -zv example.com 53  # UDP
