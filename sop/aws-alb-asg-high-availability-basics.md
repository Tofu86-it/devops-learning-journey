# AWS ALB / Auto Scaling / High Availability Basics

## 🎯 Purpose
Understand how Application Load Balancer and Auto Scaling Group work together to improve availability and scalability.

---

## 🧭 Core Concepts

### Application Load Balancer (ALB)
ALB distributes incoming HTTP/HTTPS traffic across healthy targets in one or more Availability Zones.

### Target Group
A target group is the set of backend targets that receive traffic from the load balancer.

### Auto Scaling Group (ASG)
ASG maintains and adjusts the number of EC2 instances based on configured capacity settings.

### High Availability
High availability means avoiding single points of failure by distributing resources across multiple Availability Zones.

---

## 🔍 Basic Relationship

Internet
-> ALB
-> Target Group
-> Auto Scaling Group
-> EC2 instances across multiple AZs

---

## 🛠️ Key Ideas

- ALB sends traffic only to healthy targets
- Target groups connect ALB to backend instances
- ASG maintains minimum capacity and can scale out/in
- Multi-AZ design improves availability

---

## 💡 Key Takeaways

- Single EC2 instance is not highly available
- ALB + ASG + Multi-AZ is a common SAA core pattern
- ELB health checks and Auto Scaling health checks can work together
