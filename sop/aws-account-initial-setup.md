# AWS Account Initial Setup

## 🎯 Purpose
Prepare an AWS account for safe daily use and future lab practice.

---

## 🛠️ Steps

### 1. Secure root account
- Enable MFA
- Keep root account for account-level management only

### 2. Create IAM admin user
- Go to IAM
- Create user: `devops-admin`
- Attach policy: `AdministratorAccess`

### 3. Login with IAM user
- Sign out from root
- Login using IAM user for daily operations

### 4. Enable billing alert
- Open Billing console
- Configure billing alarm / budget notification

### 5. Choose a working region
- Select one main region for lab practice
- Keep using the same region consistently

### 6. Familiarize with core services
- EC2
- VPC
- IAM
- Billing

---

## 💡 Notes
- Root should not be used for normal daily lab work
- Billing alert should be enabled before creating more resources
- Consistent region usage helps reduce confusion in lab practice
