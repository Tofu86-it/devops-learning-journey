# AWS DynamoDB Basics and Database Selection

## 🎯 Purpose
Understand the basics of DynamoDB and learn how to choose between Aurora/RDS and DynamoDB in AWS solution design.

---

## 🧭 Core Concepts

### Aurora / RDS
Aurora and RDS are used for relational database workloads.

Typical characteristics:
- SQL
- structured schema
- transactions
- relational queries

### DynamoDB
DynamoDB is a fully managed NoSQL database.

Typical characteristics:
- key-value / document model
- low latency
- very high scalability
- managed service with minimal operational overhead

---

## 🔍 Selection Logic

### Choose Aurora / RDS when:
- SQL is required
- relational data is important
- joins are needed
- traditional transactional database design is required

### Choose DynamoDB when:
- extremely high scale is required
- low latency is critical
- data access is key-based
- the workload fits a NoSQL pattern

---

## 💡 Key Takeaways

- Aurora / RDS and DynamoDB solve different problems
- DynamoDB is not a replacement for relational databases
- SAA questions often test requirement-based database selection
- SQL / join / relational thinking usually points to Aurora or RDS
- key-value / massive scale / low latency usually points to DynamoDB
