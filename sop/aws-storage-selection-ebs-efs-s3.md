# AWS Storage Selection: EBS vs EFS vs S3

## 🎯 Purpose
Understand how to choose between EBS, EFS, and S3 in AWS solution design.

---

## 🧭 Core Concepts

### Amazon EBS
EBS is block storage for EC2 instances.

Typical use cases:
- system disk
- attached data volume
- storage that behaves like a virtual hard disk

### Amazon EFS
EFS is shared file storage.

Typical use cases:
- multiple EC2 instances need shared access
- NFS-style file system
- shared application files

### Amazon S3
S3 is object storage.

Typical use cases:
- files
- backups
- logs
- static website content

---

## 🔍 Selection Logic

### Choose EBS when:
- storage must be attached to EC2
- the workload expects a block device
- you need an OS disk or attached application disk

### Choose EFS when:
- multiple EC2 instances must share the same files
- the workload expects a file system
- NFS-style shared storage is needed

### Choose S3 when:
- the workload stores files as objects
- static assets, backups, and logs are involved
- a mounted block/file disk is not required

---

## 💡 Key Takeaways

- EBS = block storage for EC2
- EFS = shared file storage
- S3 = object storage
- SAA questions often test whether the requirement is block, file, or object storage
