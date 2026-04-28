# AWS EC2 SSH Basics

## 🎯 Purpose
Understand the core components required to launch and access a Linux EC2 instance.

---

## 🧭 Core Concepts

### AMI
AMI is the operating system image template used to launch an EC2 instance.

### Key Pair
Key Pair is used for SSH authentication.
AWS stores the public key in the instance, and the user downloads the private key (`.pem`) for login.

### Security Group
Security Group is the virtual firewall attached to the EC2 instance.

### Public IP
Public IP is used to access the EC2 instance from the internet.

### SSH
SSH is the main method to access a Linux EC2 instance remotely.

---

## 🛠️ Launch Flow

AMI -> EC2 -> Key Pair -> Security Group -> Public IP -> SSH login

---

## 🛠️ Common Example

### Amazon Linux
```bash
ssh -i "C:\path\key.pem" ec2-user@<PublicIP>
```
###Ubuntu
```bash
ssh -i "C:\path\key.pem" ubuntu@<PublicIP>
```
Verification Commands
```
whoami
hostname
ip a
cat /etc/os-release
```
⚠️ Common SSH Failure Causes

Security Group does not allow TCP 22

Source IP is incorrect

Wrong login user

Wrong key pair

Using private IP instead of public IP
