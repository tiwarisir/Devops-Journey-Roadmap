# 09 - HTTP and HTTPS

The **HTTP (Hypertext Transfer Protocol)** and **HTTPS (HTTP Secure)** are the foundation of web communication.  
Every API request, website load, and browser-server interaction happens over these protocols.

Understanding how they work is crucial for DevOps engineers managing web servers, APIs, and load balancers.

---

## 🌍 What is HTTP?

**HTTP** is an **application-layer protocol** used for transferring data between clients and servers — such as browsers, APIs, and web servers.

- It works on **Port 80**
- It’s **stateless** (each request is independent)
- It uses **TCP** as the underlying transport protocol

---

### 🔹 Basic HTTP Request Flow

1. Client (browser) sends a request → `GET /index.html`
2. Server responds → `200 OK` + page content
3. Client displays the page

Example:
GET / HTTP/1.1
Host: example.com
User-Agent: Mozilla/5.0
Accept: text/html

makefile
Copy code

Response:
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 150

pgsql
Copy code

---

### 🔹 HTTP Methods

| Method | Description | Example Use |
|---------|--------------|--------------|
| **GET** | Retrieve data | View webpage or API data |
| **POST** | Send data to server | Submit form / upload file |
| **PUT** | Update existing data | Update user info |
| **DELETE** | Remove resource | Delete a record |
| **PATCH** | Partial update | Modify one field in data |
| **HEAD** | Fetch headers only | Check if file exists |

---

### 🔹 HTTP Status Codes

| Code | Meaning | Example |
|------|----------|----------|
| **200** | OK | Successful request |
| **301** | Moved Permanently | URL redirect |
| **400** | Bad Request | Invalid input |
| **401** | Unauthorized | Login required |
| **403** | Forbidden | Access denied |
| **404** | Not Found | Wrong URL |
| **500** | Internal Server Error | Server issue |

---

## 🔒 What is HTTPS?

**HTTPS** = HTTP + SSL/TLS encryption.  
It ensures **secure data transfer** between client and server by encrypting all communication.

- Works on **Port 443**
- Uses **SSL/TLS certificates**
- Prevents **man-in-the-middle (MITM)** attacks
- Ensures **data confidentiality & integrity**

---

### 🔹 How HTTPS Works (Step-by-Step)

1. **Client Hello:** Browser connects and asks for secure session  
2. **Server Hello:** Server sends SSL certificate  
3. **Key Exchange:** Both sides agree on encryption keys  
4. **Data Transfer:** Encrypted communication begins  
5. **Session Close:** Securely terminated

🧠 All this happens within milliseconds when you open a website!

---

### 🔹 SSL/TLS Certificates

SSL (Secure Sockets Layer) and its modern version TLS (Transport Layer Security) use certificates to authenticate servers.

**Types of Certificates:**

| Type | Description | Use Case |
|-------|--------------|----------|
| **DV (Domain Validated)** | Validates only domain | Personal sites |
| **OV (Organization Validated)** | Validates organization | Business websites |
| **EV (Extended Validation)** | Strict validation, green bar in browsers | Banks, e-commerce |

---

### 🔹 Free HTTPS with Let's Encrypt

Let’s Encrypt provides **free SSL/TLS certificates**.

Example (Linux + NGINX):
```bash
sudo apt install certbot python3-certbot-nginx
sudo certbot --nginx -d example.com -d www.example.com
sudo systemctl reload nginx
✅ Certificate auto-renewal:

bash
Copy code
sudo systemctl enable certbot.timer
🔹 Common HTTPS Problems
Issue	Cause	Fix
“Not Secure” warning	Expired or missing certificate	Renew SSL (e.g., certbot renew)
Mixed content	HTTP elements on HTTPS site	Use https:// for all assets
Invalid CN	Wrong domain in certificate	Reissue with correct domain

🧠 HTTP vs HTTPS
Feature	            HTTP	        HTTPS
Port	               80	           443
Encryption	       ❌ No	     ✅ Yes (SSL/TLS)
Data Security      	None	        Encrypted
Speed	          Slightly faster  	Slightly slower (TLS overhead)
SEO             Ranking	Normal	  Preferred by Google
Example     	http://example.com	 https://example.com

☁️ DevOps Use Cases
Use Case	               Protocol	         Example
Web application hosting	  HTTPS	         NGINX with SSL
API Gateway              	HTTPS	         AWS API Gateway or ALB
Internal microservices	  HTTP or HTTPS	 Kubernetes ingress
Monitoring endpoints	    HTTP	        /health probes

🧾 Quick Commands & Tools
bash
# Check website SSL details
openssl s_client -connect example.com:443

# Verify HTTPS certificate expiry
echo | openssl s_client -servername example.com -connect example.com:443 2>/dev/null | openssl x509 -noout -dates

# Test HTTP response
curl -I https://example.com
💡 Remember:

HTTP = Communication protocol

HTTPS = Secure version of HTTP using encryption

Always use HTTPS for production, API, or user data transfer
