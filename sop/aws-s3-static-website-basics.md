# AWS S3 Static Website Basics

## 🎯 Purpose
Host a simple static website using Amazon S3.

---

## 🧭 Core Concepts

### S3 Static Website Hosting
S3 can host static files such as:
- HTML
- CSS
- JavaScript
- Images

### Public Access
By default, S3 content is private.
To host a public static website, public read access must be configured carefully.

### Block Public Access
This is an important safety control that helps prevent accidental public exposure.

---

## 🛠️ Basic Steps

### 1. Create a new bucket
- Use a globally unique bucket name
- Choose the correct region

### 2. Upload `index.html`

### 3. Enable Static Website Hosting
- Set index document to `index.html`

### 4. Configure public read access
- Review Block Public Access settings
- Add Bucket Policy allowing `s3:GetObject`

### 5. Open the website endpoint in browser

---

## 🛠️ Example Bucket Policy

```json id="edui50"
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
    }
  ]
}
```
💡 Key Takeaways
- S3 is private by default
- Static website hosting is suitable for static frontend content
- Public access should only be enabled intentionally and minimally
- S3 static websites are different from EC2-hosted dynamic applications
