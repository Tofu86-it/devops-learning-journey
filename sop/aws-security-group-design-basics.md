# AWS Security Group Design Basics

## 🎯 Purpose
Understand how to design Security Group rules using the principle of least privilege.

---

## 🧭 Core Principle

Only allow the minimum required source, port, and direction.

---

## 🛠️ Common Rule Design

### SSH
```text
TCP 22 -> Source: Admin IP/32
```
Public Web
```
TCP 80  -> Source: 0.0.0.0/0
TCP 443 -> Source: 0.0.0.0/0
```
Application Port
```
TCP 8000 -> Source: web-sg
```
Database Port
```
TCP 3306 -> Source: app-sg
```
🔍 Key Concepts

SSH should not be open to the world
Web ports may be public if the service is intended for internet users
App ports should usually only allow traffic from the web layer
Database ports should usually only allow traffic from the application layer
Security Group source can be another Security Group, not only an IP or CIDR
💡 Example Three-Layer Design
```
web-sg
80 <- 0.0.0.0/0
443 <- 0.0.0.0/0
22 <- Admin IP/32
app-sg
8000 <- web-sg
db-sg
3306 <- app-sg
```
✅ Key Takeaway

Security Group design should follow least privilege and layer-based access control, not simple broad allow rules.
