# 03 - DNS & DHCP

Networking is incomplete without **DNS** and **DHCP**.  
- **DNS (Domain Name System)** resolves domain names into IP addresses.  
- **DHCP (Dynamic Host Configuration Protocol)** automatically assigns IPs to devices.  

As a DevOps engineer, you’ll configure DNS in cloud (AWS Route53, Cloudflare) and use DHCP in office/VM environments.

---

## 🌐 DNS (Domain Name System)

### Why DNS?
Hum `google.com` type karte hain, par system ko chahiye `142.250.182.110`.  
DNS = Internet’s phonebook.

### DNS Record Types
- **A** → Maps domain to IPv4 (e.g., `example.com → 192.168.1.10`)  
- **AAAA** → Maps domain to IPv6  
- **CNAME** → Alias for another domain (e.g., `www → example.com`)  
- **MX** → Mail server records (e.g., Gmail, Outlook)  
- **TXT** → Verification/metadata (SPF, DKIM)  
- **NS** → Nameserver information  

### Tools to Test DNS
- `nslookup google.com`  
- `dig google.com A`  
- `host google.com`  

---

## 🔄 DHCP (Dynamic Host Configuration Protocol)

### Why DHCP?
Without DHCP → manual IP configuration needed.  
With DHCP → automatic IP allocation + gateway + DNS.

### DHCP Workflow
1. Device sends **DHCPDISCOVER**  
2. Server replies **DHCPOFFER**  
3. Device requests with **DHCPREQUEST**  
4. Server confirms with **DHCPACK**  

### Benefits
- Avoids IP conflicts  
- Easy to manage large networks  
- Centralized control of IP leases  

---

## 🛠️ DevOps Use Cases

- **DNS**
  - AWS Route53 → Host public domains, internal private DNS  
  - Kubernetes → CoreDNS manages pod/service names  
  - Load Balancer + DNS → Route traffic efficiently  

- **DHCP**
  - Office networks → Users get IPs automatically  
  - VMware / VirtualBox → VM network auto assignment  
  - Cloud instances usually use DHCP behind the scenes  

---

## ✅ Quick Commands Recap

- `dig example.com ANY` → Get all DNS records  
- `cat /etc/resolv.conf` → See DNS servers Linux is using  
- `ipconfig /all` (Windows) → Shows DHCP/DNS info  
- `systemctl status isc-dhcp-server` (Linux) → Check DHCP service  

---
