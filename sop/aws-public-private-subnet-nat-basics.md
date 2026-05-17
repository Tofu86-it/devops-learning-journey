# AWS Public Subnet / Private Subnet / NAT Gateway Basics

## 🎯 Purpose
Understand the difference between public and private subnets, and the role of NAT Gateway in AWS networking.

---

## 🧭 Core Concepts

### Public Subnet
A public subnet is typically a subnet whose route table includes:
```
0.0.0.0/0 -> Internet Gateway
```
Instances in a public subnet can be reachable from the internet if they also have:

a Public IP
proper Security Group rules
Private Subnet

A private subnet does not have a direct default route to the Internet Gateway.

Instances in a private subnet are usually:

not assigned a Public IP
not directly reachable from the internet
NAT Gateway

A NAT Gateway allows instances in a private subnet to initiate outbound internet connections without being directly reachable from the internet.

🛠️ Traffic Flow
Public EC2

External Client -> Public IP -> Internet Gateway -> Public Subnet -> EC2

Private EC2 outbound access

Private EC2 -> Route Table -> NAT Gateway -> Internet Gateway -> Internet

💡 Key Takeaways
Public subnet = direct internet route via Internet Gateway

Private subnet = no direct internet route

NAT Gateway = outbound internet access for private instances

Private subnet instances can go out, but external hosts cannot directly connect in
