# Load Balancing

Load Balancing is the process of distributing incoming network or application traffic across multiple servers to ensure **high availability, reliability, and performance**.

In modern DevOps systems, load balancers prevent a single point of failure and improve scalability across web servers, databases, or containerized applications.

---

## ⚙️ What is Load Balancing?

When multiple users access a service, instead of directing all traffic to one server, a **load balancer** distributes the requests among available servers.

✅ **Goal:**  
- Optimize resource utilization  
- Prevent overload  
- Ensure continuous availability  

---

## 🌐 Types of Load Balancers

### 1️⃣ **Layer 4 (Transport Layer) Load Balancer**
- Works at the **TCP/UDP** layer.
- Routes traffic based on **IP address and port**.
- Doesn’t inspect actual application data.

**Examples:**  
- AWS NLB (Network Load Balancer)  
- HAProxy (TCP mode)  
- Linux IPVS  

**Pros:**  
- Fast and efficient  
- Ideal for simple traffic distribution  

**Cons:**  
- No visibility into HTTP headers or URLs  

---

### 2️⃣ **Layer 7 (Application Layer) Load Balancer**
- Works at the **HTTP/HTTPS** layer.
- Routes based on **URL, cookies, or headers**.
- Can perform SSL termination and intelligent routing.

**Examples:**  
- AWS ALB (Application Load Balancer)  
- NGINX, HAProxy (HTTP mode)  
- Traefik, Envoy  

**Pros:**  
- Smart routing  
- Can handle different application paths  
- Enables A/B testing and API versioning  

**Cons:**  
- Slightly more processing overhead  

---

## ⚖️ Load Balancing Algorithms

| Algorithm | Description | Example Use |
|------------|--------------|--------------|
| **Round Robin** | Each server gets equal requests sequentially | Simple web servers |
| **Least Connections** | New request → server with least active connections | Dynamic traffic loads |
| **IP Hash** | Client IP decides which server handles it | Sticky sessions |
| **Weighted Round Robin** | Distributes load based on server capacity | Mixed hardware setup |
| **Random** | Random selection | Testing / small setups |

---

## 🧩 NGINX Load Balancing Example

### 🔹 NGINX Configuration
```bash
# /etc/nginx/conf.d/loadbalance.conf
upstream backend_servers {
    server 192.168.1.101;
    server 192.168.1.102;
    server 192.168.1.103;
}

server {
    listen 80;

    location / {
        proxy_pass http://backend_servers;
    }
}
✅ Result:
Requests will automatically rotate between 3 backend servers.

☁️ AWS Load Balancers
AWS Service	Layer	Description
ALB (Application Load Balancer)	Layer 7	Smart HTTP/HTTPS routing, path-based rules
NLB (Network Load Balancer)	Layer 4	Ultra-fast TCP traffic handling
CLB (Classic Load Balancer)	L4 + L7	Legacy, basic features
Gateway Load Balancer	Layer 3	Integrates firewalls and inspection appliances

Example Use Cases:

ALB → Web apps (EC2, ECS, EKS)

NLB → Gaming servers, TCP-based services

GWLB → Security tools, traffic inspection

🧠 Health Checks

Load balancers perform health checks to ensure only healthy instances receive traffic.

Example (AWS):

Target group health check: /health

Interval: 30 seconds

Unhealthy threshold: 3 failures

NGINX Example:
Use third-party module ngx_http_healthcheck_module or integrate with a monitoring script.

🧰 HAProxy Example (TCP Load Balancing)
# /etc/haproxy/haproxy.cfg
frontend http_front
    bind *:80
    default_backend web_back

backend web_back
    balance roundrobin
    server web1 192.168.1.101:80 check
    server web2 192.168.1.102:80 check


✅ Result:
HAProxy distributes HTTP requests evenly to both web servers.

🧾 Real-World DevOps Scenarios
Scenario	                     Load Balancer        	Purpose
Web servers behind NGINX	        L7	             HTTP load distribution
API Gateway on AWS	             ALB	            Smart routing by path
Microservices in Kubernetes	 Ingress Controller	 Internal L7 balancing
Database cluster	          ProxySQL / HAProxy	 Read/Write separation
VPN gateway failover	            NLB	           TCP-based redundancy

🔒 Security & Best Practices

Always enable HTTPS (SSL termination) at the load balancer level

Use health checks to auto-remove bad instances

Enable sticky sessions when state is important

Monitor with Prometheus / Grafana or AWS CloudWatch

For multi-region systems → use Global Load Balancing (Route53, Cloudflare)

💡 Remember:

Layer 4 → Fast & simple, TCP-based

Layer 7 → Smart & application-aware

Load balancing = High Availability + Performance + Reliability
