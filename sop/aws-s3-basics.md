# AWS S3 Basics

## 🎯 Purpose
Understand the basic concepts of Amazon S3 and perform basic bucket and object operations.

---

## 🧭 Core Concepts

### S3
Amazon S3 is an object storage service.

### Bucket
A bucket is a container for storing objects.

### Object
An object is a file stored in a bucket.

---

## 🔍 Storage Comparison

| Service | Type | Common Use |
|--------|------|------------|
| S3 | Object Storage | Files, backup, static website, logs |
| EBS | Block Storage | EC2 system/data disk |
| EFS | File Storage | Shared file system for multiple EC2 instances |

---

## 🛠️ Basic Steps

### 1. Create a bucket
- Choose a globally unique bucket name
- Choose the correct region
- Keep Block Public Access enabled

### 2. Upload a test file
Example:
- `day16-test.txt`

### 3. Verify object exists in the bucket

### 4. Download the object

### 5. Delete the object

---

## 💡 Key Takeaways

- S3 is not a traditional VM disk
- S3 uses buckets and objects
- Bucket names must be globally unique
- Block Public Access should usually remain enabled unless there is a clear reason to make content public
