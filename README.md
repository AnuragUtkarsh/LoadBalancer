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


<img width="1157" height="636" alt="Screenshot 2026-03-06 173442" src="https://github.com/user-attachments/assets/4fd36d54-62da-4631-b929-2f6ee21e07f9" />
<img width="1166" height="666" alt="Screenshot 2026-03-06 173459" src="https://github.com/user-attachments/assets/3a1589c8-a91a-4144-8737-7005a8f48512" />
<img width="404" height="190" alt="Screenshot 2026-03-06 173620" src="https://github.com/user-attachments/assets/8e937752-9335-45d4-bbb9-370d6b398fa9" />
<img width="1108" height="603" alt="Screenshot 2026-03-06 180707" src="https://github.com/user-attachments/assets/e4476e38-4299-4c59-a494-8fff18b785d2" />
<img width="1167" height="655" alt="Screenshot 2026-03-06 181125" src="https://github.com/user-attachments/assets/8813291c-9bb1-4014-8509-8dd7a91cd8de" />



