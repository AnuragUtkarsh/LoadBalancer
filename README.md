Devops HAProxy Load Balancer
Architecture

Client → HAProxy Load Balancer → Apache Web Servers

This project demonstrates how to configure a basic load balancing setup using HAProxy and Apache2 on Ubuntu 22.04.

Lab Setup
Component	Technology
Load Balancer	HAProxy
Web Server	Apache2
OS	Ubuntu 22.04
Algorithm	Round Robin
Network Layout

Load Balancer → 192.168.22.133
Web Server 1 → 192.168.22.134
Web Server 2 → 192.168.22.135

Steps Performed
1. Installed HAProxy on Load Balancer
sudo apt update
sudo apt install haproxy -y
2. HAProxy Configuration
frontend http_front
    bind *:80
    default_backend web_servers

backend web_servers
    balance roundrobin
    server web1 192.168.22.134:80 check
    server web2 192.168.22.132:80 check
3. Installed Apache on Web Servers
sudo apt install apache2 -y
4. Created custom pages

Web Server 1:

<h1>Hello from Web Server 1</h1>

Web Server 2:

<h1>Hello from Web Server 2</h1>
Verification

Test from load balancer:

curl http://LOADBALANCER-IP

Browser output rotates between servers:

Hello from Web Server 1
Hello from Web Server 2
Concepts Demonstrated

Layer 7 Load Balancing

HAProxy configuration

Apache web server deployment

Backend health checks

Round Robin traffic distribution

Author

Anurag Utkarsh
Cloud Engineer(Linux & Security) | DevOps Enthusiast
<img width="404" height="190" alt="Screenshot 2026-03-06 173620" src="https://github.com/user-attachments/assets/bb40dc8e-6080-401f-8ec4-62fee884e802" />
<img width="1166" height="666" alt="Screenshot 2026-03-06 173459" src="https://github.com/user-attachments/assets/fa8c58fe-39f9-43ce-aed5-0fe33203badc" />
<img width="1157" height="636" alt="Screenshot 2026-03-06 173442" src="https://github.com/user-attachments/assets/14ced3e5-7e01-41ff-b9f5-a39a376409a7" />

