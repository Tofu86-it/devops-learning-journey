# AWS EC2 Setup SOP

## Purpose
Launch an EC2 instance and access it via SSH.

## Steps

### 1. Create Key Pair
- Go to EC2 Console
- Open Key Pairs
- Click Create Key Pair
- Download the `.pem` file

### 2. Launch EC2 Instance
- Choose AMI
- Select instance type
- Configure Security Group
- Allow SSH (22)
- Allow HTTP (80) if needed

### 3. Connect via SSH
Example:
```bash
ssh -i your-key.pem ec2-user@your-public-ip
