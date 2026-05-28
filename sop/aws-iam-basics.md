# AWS IAM Basics

## 🎯 Purpose
Understand the core IAM components in AWS: User, Group, Role, and Policy.

---

## 🧭 Core Concepts

### IAM User
A long-term identity typically used by a human user.

### IAM Group
A collection of IAM users that share the same permissions.

### IAM Role
A temporary identity commonly used by AWS services or assumed identities.

### IAM Policy
A JSON document that defines permissions.

---

## 🔍 Basic Relationship

User / Group / Role
-> attach
-> Policy

---

## 🛠️ Common Usage

### User
Used for human access to AWS Console, CLI, or API.

### Group
Used to manage permissions for multiple users more efficiently.

### Role
Used for EC2, Lambda, and temporary access scenarios.

### Policy
Defines what actions are allowed or denied on which resources.

---

## 💡 Least Privilege

IAM permissions should follow least privilege:
- allow only the required actions
- on only the required resources
- for only the required identities

---

## ⚠️ Important Best Practice

Do not store long-term access keys directly inside EC2 instances.  
Use IAM Role for EC2 to access AWS services such as S3.

---

## ✅ Key Takeaway

- User = human identity
- Group = permission grouping for users
- Role = temporary/service identity
- Policy = permission rules
