# Install nginx on AWS EC2

## 🎯 Purpose
Install and run nginx web server on an EC2 instance, and make it accessible from the internet.

---

## 🧭 Environment
- Platform: AWS EC2
- OS: Amazon Linux 2023 / Ubuntu 22.04
- Access Method: SSH
- Required Port: 80 (HTTP)

---

## 🛠️ Steps

### 1. Connect to EC2 via SSH

```bash
ssh -i your-key.pem ec2-user@your-public-ip
```
For Ubuntu:
```
ssh -i your-key.pem ubuntu@your-public-ip
```
2. Update system packages

Amazon Linux:
```
sudo dnf update -y
```
Ubuntu:
```
sudo apt update && sudo apt upgrade -y
```
3. Install nginx

Amazon Linux:
```
sudo dnf install nginx -y
```
Ubuntu:
```
sudo apt install nginx -y
```
4. Enable nginx service (auto start on boot)
```
sudo systemctl enable nginx
```
6. Start nginx service
```
sudo systemctl start nginx
```
7. Verify nginx service status
```
systemctl status nginx
```
Expected: active (running)

7. Open HTTP port (Security Group)

Go to AWS Console:

EC2 → Security Groups → Inbound rules

Add rule:

Type: HTTP
Port: 80
Source: 0.0.0.0/0
8. Verify from browser

Open:

http://<EC2 Public IP>

Expected: nginx default welcome page

⚠️ Troubleshooting
❌ Cannot access webpage

Check:

Security Group
Is port 80 open?
nginx service
systemctl status nginx
Local firewall (if enabled)
Ubuntu:
sudo ufw status
Amazon Linux:
sudo firewall-cmd --list-all
❌ SSH works but HTTP not working

Possible causes:

Port 80 not allowed in Security Group
nginx not started
Wrong Public IP
💡 Notes
Security Group acts as a cloud-level firewall
Public IP is required for external access
nginx default page confirms successful deployment

---
