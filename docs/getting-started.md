# 🟢 Getting Started with AWS Cloud Security

Welcome! This guide walks you through the foundational steps for starting your journey with AWS Cloud Security. Whether you're new to cloud computing or just new to AWS, this will get you up and running smoothly.

---

## 🧰 Prerequisites

Before diving in, make sure you have:
- A stable internet connection
- A laptop or desktop with a modern browser
- A GitHub account (for version control and documentation)
- A valid email to sign up for AWS

---

## 🛠️ Step-by-Step Setup

### 1. Create an AWS Account
- Visit [https://aws.amazon.com](https://aws.amazon.com)
- Click **Create an AWS Account**
- Follow the prompts to verify your email, payment method, and identity
- Select the **Free Tier** to avoid charges during early learning

### 2. Set Up IAM User
- Go to **IAM Console** from your AWS dashboard
- Create a new IAM user with Administrator Access (for learning purposes)
- Enable MFA (Multi-Factor Authentication) for enhanced security

### 3. Launch Your First EC2 Instance
- Navigate to the **EC2 Console**
- Click **Launch Instance**
- Choose a Free Tier eligible AMI (e.g., Amazon Linux 2023)
- Select instance type: `t2.micro`
- Configure security group: open SSH (port 22) for access

### 4. Create an S3 Bucket
- Go to the **S3 Console**
- Click **Create Bucket**
- Name your bucket and choose a region
- Uncheck "Block all public access" if you plan to test public object access

---

## 📸 Screenshots

You’ll find example screenshots in the `/docs/images/` folder showing:
- AWS account creation
- IAM user setup
- EC2 launch configuration
- S3 bucket dashboard

To view inline examples in this guide, see:
```markdown
![IAM User Setup](images/iam-user-setup.png)

