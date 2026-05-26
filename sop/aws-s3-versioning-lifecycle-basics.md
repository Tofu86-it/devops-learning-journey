# AWS S3 Versioning and Lifecycle Basics

## 🎯 Purpose
Understand S3 versioning and lifecycle management for object retention and storage governance.

---

## 🧭 Core Concepts

### Versioning
S3 Versioning keeps multiple versions of an object when the same key is overwritten or deleted.

### Lifecycle
Lifecycle rules automatically manage objects over time, such as expiring old versions or deleting unnecessary data.

---

## 🔍 Why Versioning Matters

- Protects against accidental overwrite
- Protects against accidental deletion
- Keeps historical object versions

### Important Note
Older versions still consume storage and may increase cost.

---

## 🔍 Why Lifecycle Matters

- Controls retention period
- Deletes old versions automatically
- Helps reduce storage cost
- Supports storage governance

---

## 🛠️ Basic Lab Steps

### 1. Create or use a test bucket

### 2. Enable Versioning

### 3. Upload `day18-test.txt` with content:
```text
Version 1
```
4. Upload the same file again with content:
```Version 2```
5. Observe object versions in the S3 console
6. Delete the object and observe delete marker behavior
7. Review Lifecycle rule options in the bucket settings
💡 Key Takeaways
- Versioning keeps historical versions of the same object key
- Deleting a versioned object may create a delete marker
- Lifecycle helps control object retention and storage cost
- Versioning and Lifecycle are often used together
```
