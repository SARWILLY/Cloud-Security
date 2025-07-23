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
    - [IAM User Setup](docs/screenshots/Screenshot_22-7-2025_19100_us-east-1.console.aws.amazon.com.jpeg)
    - [IAM User Setup](docs/screenshots/Screenshot_22-7-2025_191557_us-east-1.console.aws.amazon.com.jpeg)
---

## 🧪 IAM Policy Simulation: AmazonS3FullAccess vs AWS Config Actions

As part of understanding how IAM policies behave in specific contexts, I ran a simulation using the **IAM Policy Simulator** for a group named `Analyst`, which had the `AmazonS3FullAccess` policy attached.

### 🔍 What I Tested
I simulated the following AWS Config actions:
1. `DeletePendingAggregation`
2. `DeleteRemediationConfiguration` (Resource: RemediationConfiguration)
3. `DeleteConfigurationAggregator` (Resource: ConfigurationAggregator)
4. `DeleteConformancePack` (Resource: ConformancePack)

### ❌ Results
- All actions were **Denied**, due to **implicit denial** (no matching policies for these actions).
- This confirms that the `AmazonS3FullAccess` policy does *not* grant permissions for AWS Config operations—showing how precise policy scopes are.

### ✅ What I Learned
- IAM policies are **action-specific** and must explicitly define permissions for each AWS service.
- Using the **IAM Policy Simulator** is a reliable way to verify access *before* deployment or testing in live environments.
- Policy simulation avoids accidental misconfigurations and reinforces the importance of least privilege.

### 📸 Screenshot Example
- [Policy Simulator showing denied AWS Config actions](docs/screenshots/Screenshot_22-7-2025_192953_us-east-1.console.aws.amazon.com.jpeg)

---

## 🧪 IAM Policy Simulation: Validating AmazonS3FullAccess Scope

Continuing my IAM policy evaluation, I simulated S3-related actions for a user named `Sar Williams` who was attached to the managed policy `AmazonS3FullAccess`.

### 🔍 Actions Simulated
I focused on key S3 operations across buckets and objects:
- `s3:ListBucket`
- `s3:GetObject`
- `s3:PutObject`
- `s3:DeleteObject`
- `s3:ListAllMyBuckets`
- AWS Config action: `DeletePendingAggregationRequest`

### ✅ Simulation Results
- All **Amazon S3 actions** returned **Allowed** with a matching policy statement.
- The AWS Config action was **Denied** due to no matching permissions.

### 🧠 What I Learned
- `AmazonS3FullAccess` fully supports bucket-level and object-level interactions.
- No cross-service permissions are granted—AWS Config actions require their own explicit policies.
- The IAM Policy Simulator is essential for verifying granular access and refining policy design.

### 📸 Screenshot Reference
- [IAM Simulation: AmazonS3FullAccess results](docs/screenshots/Screenshot_22-7-2025_192452_policysim.aws.amazon.com.jpeg)

---

### 3. Launch Your First EC2 Instance
- Navigate to the **EC2 Console**
- Click **Launch Instance**
- Choose a Free Tier eligible AMI (e.g., Amazon Linux 2023)
- Select instance type: `t2.micro`
- Configure security group: open SSH (port 22) for access
  - [EC2 Instance Setup](https://github.com/SARWILLY/Cloud-Security/blob/dd77120c75caeefdadc83c3248a9dc684eb674d5/docs/docs/screenshots/Screenshot%202025-07-21%20172612.png)
  - [EC2 Instance Setup](https://github.com/SARWILLY/Cloud-Security/blob/162ca306566f562e7d6c203396d05d88323da665/docs/docs/screenshots/Screenshot%202025-07-21%20200821.png)
  - [EC2 Instance Setup](https://github.com/SARWILLY/Cloud-Security/blob/162ca306566f562e7d6c203396d05d88323da665/docs/docs/screenshots/Screenshot%202025-07-21%20201052.png)

### 4. Create an S3 Bucket
- Go to the **S3 Console**
- Click **Create Bucket**
- Name your bucket and choose a region
- Uncheck "Block all public access" if you plan to test public object access
  - [s3 Bucket Setup](docs/screenshots/screenshot-1753205816168.png)
  - [s3 Bucket Setup](docs/screenshots/Screenshot_22-7-2025_184657_us-east-1.console.aws.amazon.com.jpeg)
  - [s3 Bucket Setup](docs/screenshots/Screenshot_22-7-2025_184944_us-east-1.console.aws.amazon.com.jpeg)
  - [s3 Bucket Setup](docs/screenshots/Screenshot_22-7-2025_185839_us-east-1.console.aws.amazon.com.jpeg)
  - [s3 Bucket Setup](docs/screenshots/Screenshot_22-7-2025_19141_us-east-1.console.aws.amazon.com.jpeg)

---

## 📸 Screenshots

You’ll find example screenshots in the `docs/docs/screenshots/` folder showing:
- AWS account creation
- IAM user setup
- EC2 launch configuration
- S3 bucket dashboard

To view inline examples in this guide, see:

