# AWS EC2 Role Access S3 Lab

## 🎯 Purpose
Verify that an EC2 instance can access a specific S3 bucket using an IAM Role instead of long-term access keys.

---

## 🧭 Lab Goal

- Create a least-privilege IAM policy
- Attach the policy to an EC2 IAM Role
- Attach the role to an EC2 instance
- Verify S3 access from EC2
- Confirm that unauthorized S3 access is denied

---

## 🛠️ Example Policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:ListBucket",
      "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME"
    },
    {
      "Effect": "Allow",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
    }
  ]
}
```
🛠️ Steps
1. Prepare a test bucket and object
Bucket: YOUR-BUCKET-NAME
Object: day21-test.txt
2. Create a customer managed policy
Allow only s3:ListBucket
Allow only s3:GetObject on the test bucket
3. Create an EC2 IAM Role
Trusted entity: EC2
Attach the custom policy
4. Attach the role to an EC2 instance
5. SSH into the EC2 instance
6. Verify identity
aws sts get-caller-identity
7. Verify allowed S3 access
```
aws s3 ls s3://YOUR-BUCKET-NAME
aws s3 cp s3://YOUR-BUCKET-NAME/day21-test.txt .
cat day21-test.txt
```
9. Verify denied access to unauthorized bucket
```aws s3 ls s3://UNAUTHORIZED-BUCKET```
💡 Key Takeaways
- EC2 should use IAM Role instead of long-term access keys
- Policy defines allowed S3 actions and resources
- Least privilege should be validated by both allowed and denied tests
