# AWS VPC / Subnet / Route Table / Internet Gateway Basics

## 🎯 Purpose
Understand the basic AWS network components that allow an EC2 instance to be reachable from the internet.

---

## 🧭 Core Concepts

### VPC
A VPC is a private virtual network in AWS.

### Subnet
A subnet is a smaller network segment inside a VPC.

### Route Table
A route table defines where traffic should go.

### Internet Gateway
An Internet Gateway is the connection point between a VPC and the internet.

---

## 🛠️ Basic Relationship

VPC -> Subnet -> Route Table -> Internet Gateway -> EC2

---

## 🌐 Public Reachability Conditions

For an EC2 instance to be reachable from the internet, the following are typically required:

- The EC2 is in a subnet
- The subnet is associated with a route table
- The route table has:
  - `0.0.0.0/0 -> Internet Gateway`
- The VPC has an attached Internet Gateway
- The EC2 has a Public IP
- The Security Group allows the required port (for example TCP 22 for SSH)

---

## 🔍 Public IP vs Private IP

- Public IP = used by external clients to reach the EC2
- Private IP = used by the EC2 inside the VPC

The Linux OS usually shows the private IP on its network interface.

---

## 💡 Key Takeaway

An EC2 instance is not directly placed on the internet.  
It is placed inside a VPC and subnet, and internet access depends on routing, Internet Gateway, Public IP, and Security Group configuration.
