# AWS IAM Policy and EC2 Role Basics

## 🎯 Purpose
Understand IAM policy structure and how EC2 should use IAM roles to access AWS resources securely.

---

## 🧭 Core Concepts

### IAM Policy
A JSON document that defines permissions.

Key elements:
- Version
- Statement
- Effect
- Action
- Resource

### IAM Role
A temporary identity commonly used by AWS services such as EC2.

### Instance Profile
A container used to pass an IAM role to an EC2 instance.

---

## 🔍 Example Policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
    }
  ]
}
```
🛠️ Basic Lab Flow
- Create a test S3 bucket
- Create a customer managed policy for read-only object access
- Create an IAM role for EC2
- Attach the policy to the role
- Attach the role to an EC2 instance via instance profile
💡 Key Takeaways
- Policy defines permissions
- Role is the identity used by EC2
- EC2 should use IAM role instead of long-term access keys
- Instance profile is how the role is passed to EC2
