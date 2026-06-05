# AWS CLI Basics

## 🎯 Purpose
Use AWS CLI to inspect AWS resources from an EC2 instance and understand how IAM permissions affect CLI behavior.

---

## 🧭 Core Concepts

AWS CLI is a command-line tool for interacting with AWS services.

Common command styles:
- list
- describe
- get

CLI commands do not use Linux local permissions.  
They use AWS identity and IAM permissions.

---

## 🔍 Important Identity Concept

Linux user permissions and AWS permissions are different.

Example:
- `root` in Linux means local OS administrator
- `assumed-role/...` in AWS means the AWS identity currently used by the EC2 instance

### Key Takeaway
**Linux root ≠ AWS admin**

---

## 🛠️ Basic Commands

### 1. Check CLI version

```bash
aws --version
```
2. Check current AWS identity
```
aws sts get-caller-identity
```
This command is useful for verifying which IAM identity the EC2 instance is currently using.

🛠️ S3 Commands
List objects in an allowed bucket
`aws s3 ls s3://YOUR-BUCKET-NAME`
Copy an object from an allowed bucket
`aws s3 cp s3://YOUR-BUCKET-NAME/YOUR-FILE .`
List all buckets in the account
`aws s3api list-buckets`
Important Note

aws s3api list-buckets requires:
s3:ListAllMyBuckets

If the EC2 role only has least-privilege access to a specific bucket, this command should fail with AccessDenied.

That is expected behavior.

🛠️ EC2 Commands
Describe EC2 instances
aws ec2 describe-instances
Simplified output
`aws ec2 describe-instances --query "Reservations[].Instances[].{ID:InstanceId,State:State.Name,PrivateIP:PrivateIpAddress,PublicIP:PublicIpAddress}" --output table`
Important Note

These commands require:
ec2:DescribeInstances

If the current IAM role only has S3 read-only access, describe-instances should fail with UnauthorizedOperation.

That is expected behavior.

🔍 Least Privilege Interpretation

If an EC2 instance has a role that only allows access to one specific S3 bucket, then:

Expected Success
```
aws sts get-caller-identity
aws s3 ls s3://allowed-bucket
aws s3 cp s3://allowed-bucket/file.txt .
```
Expected Failure
```
aws s3api list-buckets
aws ec2 describe-instances
access to unauthorized S3 buckets
```
These failures are not errors in the lab design.
They are evidence that least privilege is working correctly.

💡 Key Takeaways

- AWS CLI uses IAM permissions, not Linux local privileges
- sts get-caller-identity helps verify which AWS identity is active
- list-buckets is broader than listing a single bucket
- describe-instances requires EC2 read permissions
- Least privilege means some CLI commands should succeed and some should fail
- Failure can be a correct security outcome
