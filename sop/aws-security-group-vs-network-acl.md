# AWS Security Group vs Network ACL

## 🎯 Purpose
Understand the difference between Security Groups and Network ACLs in AWS networking.

---

## 🧭 Security Group

Security Group is an instance-level virtual firewall attached to an EC2 instance or ENI.

### Characteristics
- Instance / ENI level
- Allow rules only
- Stateful

### Meaning of Stateful
If inbound traffic is allowed, response traffic is automatically allowed.

---

## 🧭 Network ACL

Network ACL is a subnet-level access control list.

### Characteristics
- Subnet level
- Allow and deny rules
- Rule order matters
- Stateless

### Meaning of Stateless
Inbound and outbound traffic must be evaluated separately.

---

## 🔍 Key Differences

| Item | Security Group | Network ACL |
|------|----------------|-------------|
| Scope | Instance / ENI | Subnet |
| Rule Type | Allow only | Allow and Deny |
| State | Stateful | Stateless |
| Rule Order | Not important | Important |

---

## 💡 Key Takeaway

- Security Group = instance-level, stateful, allow-only
- Network ACL = subnet-level, stateless, allow/deny
- Traffic usually needs to pass both layers before reaching the EC2 instance
