# AWS JOVAC 2026 – Lecture 1
## AWS EC2 Windows and Linux Instance Creation & Remote Access

![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Cloud Computing](https://img.shields.io/badge/Cloud-Computing-blue)
![Windows Server](https://img.shields.io/badge/Windows-Server-green)
![Linux](https://img.shields.io/badge/Linux-EC2-yellow)

---

# 📖 Project Overview

This project was completed as part of the **AWS JOVAC 2026 Training Program**. The objective was to understand the fundamentals of cloud computing, create AWS accounts, explore AWS Regions and Availability Zones, and gain hands-on experience with Amazon EC2 by creating and accessing both Windows and Linux virtual machines. :contentReference[oaicite:0]{index=0}

The project covers:

- Introduction to Cloud Computing
- AWS Account Setup
- AWS Regions and Availability Zones
- Creating a Windows EC2 Instance
- Accessing Windows EC2 using Remote Desktop Protocol (RDP)
- Creating a Linux EC2 Instance
- Accessing Linux EC2 using SSH
- Security Group Configuration
- Key Pair Authentication
- Instance Management and Termination

---

# ☁️ Introduction to Cloud Computing

Cloud Computing is the delivery of computing services such as servers, storage, networking, databases, and software over the internet. Instead of purchasing physical hardware, users can rent resources on demand.

### Benefits of Cloud Computing

- Scalability
- Cost Efficiency
- High Availability
- Security
- Global Accessibility
- Faster Deployment

---

# 🚀 Amazon Web Services (AWS)

Amazon Web Services (AWS) is a cloud platform that provides over 200 cloud services, including:

- EC2 (Elastic Compute Cloud)
- S3 (Simple Storage Service)
- VPC (Virtual Private Cloud)
- RDS (Relational Database Service)
- IAM (Identity and Access Management)

---

# 🌍 AWS Regions and Availability Zones

AWS infrastructure is distributed globally.

### Region
A Region is a geographical location containing AWS data centers.

Examples:

- Mumbai (ap-south-1)
- Singapore (ap-southeast-1)
- Ohio (us-east-2)

### Availability Zone (AZ)
An Availability Zone is an isolated data center within a region.

Benefits:

- Fault Tolerance
- High Availability
- Disaster Recovery

To view Availability Zones:

```text
AWS Console → VPC → Subnets
```

---

# 🖥️ Task 1 – Create and Access a Windows EC2 Instance

## Step 1: Select AWS Region

Choose a suitable AWS Region according to requirements. :contentReference[oaicite:1]{index=1}

---

## Step 2: Open EC2 Dashboard

```text
AWS Console → Services → EC2
```

---

## Step 3: Launch Instance

Click:

```text
Launch Instance
```

Configure:

### Instance Name

```text
Windows-Server
```

### Operating System

```text
Microsoft Windows Server 2019 Base
```

### Instance Type

```text
t3.micro
```

Free Tier eligible. :contentReference[oaicite:2]{index=2}

---

## Step 4: Create Key Pair

A Key Pair is used for secure authentication between AWS and the user machine. AWS stores the public key while the private key is downloaded locally. :contentReference[oaicite:3]{index=3}

Example:

```text
windows-key.pem
```

---

## Step 5: Configure Networking

### Availability Zone

```text
1a
```

### Security Group Rules

| Type | Port |
|--------|--------|
| RDP | 3389 |
| HTTP | 80 |
| HTTPS | 443 |

Security Groups act as virtual firewalls that control inbound and outbound traffic. :contentReference[oaicite:4]{index=4}

---

## Step 6: Configure Storage

```text
30 GB SSD
```

:contentReference[oaicite:5]{index=5}

---

## Step 7: Launch Instance

Click:

```text
Launch Instance
```

Instance state becomes:

```text
Running
```

:contentReference[oaicite:6]{index=6}

---

## Step 8: Obtain Public IP

The instance can be accessed using:

- Public IPv4 Address
- Public DNS

:contentReference[oaicite:7]{index=7}

---

# 🔐 Access Windows EC2 Instance

## Step 1: Open Instance

Select the running instance.

Click:

```text
Connect
```

:contentReference[oaicite:8]{index=8}

---

## Step 2: Retrieve Administrator Password

Navigate to:

```text
RDP Client → Get Password
```

Upload the downloaded PEM file.

Click:

```text
Decrypt Password
```

The Windows administrator password becomes visible. :contentReference[oaicite:9]{index=9}

---

## Step 3: Open Remote Desktop

Press:

```text
Win + R
```

Type:

```text
mstsc
```

This launches Microsoft Remote Desktop Connection. :contentReference[oaicite:10]{index=10}

---

## Step 4: Connect

Enter:

```text
Public IP Address
```

Then enter:

```text
Username
Password
```

The Windows Server is successfully accessed. :contentReference[oaicite:11]{index=11}

---

# 🐧 Task 2 – Create and Access a Linux EC2 Instance

The Linux instance follows the same creation procedure as the Windows instance. :contentReference[oaicite:12]{index=12}

---

## Step 1: Launch Linux Instance

Configure:

### Instance Name

```text
Linux-Server
```

### Operating System

```text
Amazon Linux 2023
```

or

```text
Ubuntu Server
```

### Instance Type

```text
t2.micro
```

---

## Step 2: Configure Security Group

Add SSH access.

| Type | Protocol | Port |
|--------|----------|--------|
| SSH | TCP | 22 |

SSH is required for Linux instances because RDP is used only for Windows machines. :contentReference[oaicite:13]{index=13}

---

## Step 3: Launch Instance

Click:

```text
Launch Instance
```

The Linux machine is created successfully. :contentReference[oaicite:14]{index=14}

---

# 🔐 Access Linux EC2 Instance

## Required Software

Install either:

- Git Bash
- PuTTY

Git Bash was used in this project. :contentReference[oaicite:15]{index=15}

---

## Step 1: Locate PEM File

Example:

```text
linux-key.pem
```

:contentReference[oaicite:16]{index=16}

---

## Step 2: Open Git Bash

Navigate to the folder containing the PEM file.

Right Click →

```text
Git Bash Here
```

:contentReference[oaicite:17]{index=17}

---

## Step 3: Set File Permissions

```bash
chmod 400 linux-key.pem
```

---

## Step 4: Connect Using SSH

### Amazon Linux

```bash
ssh -i linux-key.pem ec2-user@PUBLIC-IP
```

### Ubuntu

```bash
ssh -i linux-key.pem ubuntu@PUBLIC-IP
```

---

## Step 5: Successful Login

After authentication:

```text
[ec2-user@ip-xxx-xxx-xxx-xxx ~]$
```

Linux instance accessed successfully. :contentReference[oaicite:18]{index=18}

---

# 🧪 Basic Linux Commands

### Check Current User

```bash
whoami
```

### Print Working Directory

```bash
pwd
```

### List Files

```bash
ls
```

### Create Folder

```bash
mkdir demo
```

### Create File

```bash
touch test.txt
```

### View System Information

```bash
uname -a
```

---

# 🔒 Security Concepts Learned

## Security Groups

Acts as a virtual firewall controlling network traffic.

### Windows

```text
Port 3389 (RDP)
```

### Linux

```text
Port 22 (SSH)
```

---

## Key Pair Authentication

AWS generates:

### Public Key

Stored in AWS.

### Private Key

Downloaded to local machine.

Used for secure authentication during connection. :contentReference[oaicite:19]{index=19}

---

# ⚠️ Common Errors

## Permission Denied

```bash
Permission denied (publickey)
```

### Fix

Use correct username:

```bash
ec2-user
```

or

```bash
ubuntu
```

Verify correct PEM file.

---

## Connection Timed Out

Check:

- Public IP
- Security Group
- Port 22 Open

---

# 🗑️ Instance Termination

After completing the tasks:

```text
EC2 Dashboard
      ↓
Select Instance
      ↓
Instance State
      ↓
Terminate Instance
```

Both Windows and Linux instances should be terminated after use to avoid unnecessary charges. :contentReference[oaicite:20]{index=20} :contentReference[oaicite:21]{index=21}

---

# 📚 Learning Outcomes

By completing this project, the following concepts were learned:

- Cloud Computing Fundamentals
- AWS Account Management
- AWS Regions and Availability Zones
- Amazon EC2 Service
- Windows Server Deployment
- Linux Server Deployment
- Security Groups Configuration
- Key Pair Authentication
- SSH Connectivity
- Remote Desktop Connectivity
- Cloud Resource Lifecycle Management

---

# 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| AWS EC2 | Virtual Machine Hosting |
| Windows Server 2019 | Windows Environment |
| Amazon Linux / Ubuntu | Linux Environment |
| Git Bash | SSH Access |
| Remote Desktop | Windows Access |
| Security Groups | Firewall Rules |
| SSH | Secure Linux Connection |
| RDP | Secure Windows Connection |

---

# 📌 Conclusion

This project provided hands-on experience with Amazon EC2 by creating, configuring, accessing, and managing both Windows and Linux virtual machines. It demonstrated secure authentication using key pairs, remote administration using RDP and SSH, security group configuration, and proper cloud resource management practices.
