# AWS Aurora and RDS Basics

## 🎯 Purpose
Understand the current AWS relational database service model, including Amazon RDS and Amazon Aurora, and learn how to distinguish high availability and read scaling designs.

---

## 🧭 Core Concepts

### Aurora and RDS
AWS now presents relational database services in the console as **Aurora and RDS**.

- **Amazon RDS** is the managed relational database service family
- **Amazon Aurora** is a cloud-native relational database engine within the RDS family
- Aurora is compatible with **MySQL** and **PostgreSQL**
- Traditional RDS engines include **MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Db2**

---

## 🔍 Service Positioning

### Traditional RDS
Used when you want a managed relational database with familiar database engines and reduced operational burden.

### Aurora
Used when you want an AWS cloud-native relational database option with cluster-based architecture and stronger built-in availability / scaling features.

---

## 🧭 Availability and Scaling Concepts

### Multi-AZ
Multi-AZ is mainly used for:
- high availability
- automatic failover
- reducing single-AZ failure impact

### Read Replica
Read Replica is mainly used for:
- read scaling
- reducing read pressure on the primary database
- supporting reporting / read-heavy workloads

---

## 🔍 Key Difference

- **Multi-AZ = high availability / failover**
- **Read Replica = read scaling**

---

## 🧭 Aurora-Specific Thinking

Aurora is commonly understood through:
- **DB cluster**
- **writer instance / writer endpoint**
- **reader endpoint**
- high availability and read scaling together

---

## 🛠️ Typical Selection Logic

### Choose Multi-AZ when:
- database uptime is critical
- automatic failover is required
- minimizing outage is the main priority

### Choose Read Replica when:
- read traffic is high
- reporting queries are heavy
- scaling read throughput is the main priority

### Choose Aurora when:
- you want an AWS cloud-native managed relational database
- you need stronger managed HA / scaling patterns
- the workload fits MySQL- or PostgreSQL-compatible architecture

---

## 💡 Key Takeaways

- Aurora is not separate from RDS; it is part of the RDS service family
- The console now uses **Aurora and RDS** as the service entry point
- Traditional RDS questions often focus on **Multi-AZ** and **Read Replica**
- Aurora questions often involve **cluster architecture**, **writer / reader endpoints**, and managed HA design
- Databases are usually placed in **private subnets** and accessed only by the application layer
