# Fitness Data Pipeline — Phase 1: Upload CSV to S3

This project begins a mini data pipeline by uploading a local CSV file (fitness dataset) to AWS S3 using the AWS CLI.

---

## ✅ Prerequisites

### 1. AWS Account
You need access to an AWS account with permission to create IAM users and use S3.

### 2. AWS CLI Installed
Install the AWS CLI:
- Mac/Linux: https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html
- Windows: https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-windows.html

Verify installation:

```bash
aws --version
```
🔐 Step 1: Set Up IAM User & Permissions
1. Create IAM User
Go to the IAM Console

Navigate to Users → Add user

Set user name: fitness-uploader

Select Programmatic access

Click Next → Permissions

2. Attach Permissions
For testing, attach this managed policy:

AmazonS3FullAccess (You can restrict this later)

3. Finish and Save Credentials
Click Create user

Copy the Access Key ID and Secret Access Key

Save them securely — you won't be able to view the secret again

⚙️ Step 2: Configure AWS CLI

Run in your terminal:

```
bash
aws configure
```

Enter the following when prompted:

Access Key ID: (from previous step)

Secret Access Key: (from previous step)

Region: e.g. us-east-1

Output format: json or table (your choice)

📤 Step 3: Upload CSV to S3

Assuming your bucket is named jasraj-fitness-data and your file is cleaned_fitness.csv:

```
bash

aws s3 cp ./cleaned_fitness.csv s3://jasraj-fitness-data/cleaned_fitness.csv
```

You should see:

```
bash

upload: ./cleaned_fitness.csv to s3://jasraj-fitness-data/cleaned_fitness.csv

```

✅ Your data is now in S3.


