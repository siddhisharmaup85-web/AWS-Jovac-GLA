# AWS JOVAC 2026 – Lecture 2
## Amazon EC2 Deep Dive, Instance Lifecycle, AMI Creation, EBS, Cost Estimation & AWS Infrastructure

![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Cloud](https://img.shields.io/badge/Cloud-Computing-blue)
![AMI](https://img.shields.io/badge/AWS-AMI-green)
![EBS](https://img.shields.io/badge/Storage-EBS-yellow)

---

# 📖 Project Overview

This lecture focused on gaining a deeper understanding of Amazon EC2, including instance types, scalability, instance lifecycle management, Amazon Machine Images (AMI), Elastic Block Store (EBS), AWS Marketplace, and AWS Cost Estimation. A practical lab was also performed to create a custom AMI from an existing Windows EC2 instance. :contentReference[oaicite:0]{index=0}

The session covered both theoretical concepts and hands-on implementation, providing insight into how AWS infrastructure components work together to support scalable and highly available cloud applications.

---

# 🎯 Objectives

- Understand Amazon EC2 and its core concepts.
- Learn different EC2 Instance Types.
- Understand Scalability in AWS.
- Study the EC2 Instance Lifecycle.
- Explore AWS Marketplace.
- Learn about Amazon Machine Images (AMI).
- Understand EBS and Instance Store.
- Compare EBS vs Instance Store.
- Calculate AWS infrastructure costs.
- Create a custom AMI from an EC2 Instance.
- Understand Snapshots and AMI Storage.

---

# ☁️ Introduction to Amazon EC2

Amazon Elastic Compute Cloud (EC2) is a web service that provides scalable virtual servers in the cloud. It enables users to launch and manage virtual machines without purchasing physical hardware.

### Key Benefits

- On-Demand Computing
- Flexible Resource Allocation
- Pay-As-You-Go Pricing
- High Availability
- Secure Infrastructure
- Global Deployment

---

# 🖥️ EC2 Instance Types

AWS provides multiple instance families designed for different workloads.

| Instance Family | Purpose |
|---------------|----------|
| General Purpose | Balanced CPU, Memory, Networking |
| Compute Optimized | High Performance Computing |
| Memory Optimized | In-Memory Databases |
| Storage Optimized | High-Speed Storage Workloads |
| Accelerated Computing | GPU and Machine Learning |

### Example

```text
t2.micro
t3.micro
```

These are commonly used under AWS Free Tier.

---

# 📈 Scalability in AWS

Scalability is the ability to increase or decrease resources according to workload demands.

### Types of Scalability

## Vertical Scaling

Increasing resources of an existing server.

Example:

```text
t2.micro → t2.medium
```

### Advantages

- Easy Implementation
- No Architecture Changes

---

## Horizontal Scaling

Adding multiple servers to distribute workload.

Example:

```text
1 Server → 5 Servers
```

### Advantages

- High Availability
- Better Performance
- Fault Tolerance

---

# 🔄 EC2 Instance Lifecycle

Every EC2 instance goes through various states during its lifetime.

```text
Launch
   ↓
Pending
   ↓
Running
   ↓
Stopping
   ↓
Stopped
   ↓
Starting
   ↓
Running
   ↓
Terminated
```

### Lifecycle States

| State | Description |
|---------|------------|
| Pending | Instance is being created |
| Running | Instance is active |
| Stopping | Shutdown in progress |
| Stopped | Instance is powered off |
| Starting | Instance is booting |
| Terminated | Instance permanently deleted |

---

# 🛒 AWS Marketplace

AWS Marketplace provides ready-to-use software solutions and preconfigured machine images.

### Benefits

- Faster Deployment
- Licensed Software
- Security Verified Images
- Third-Party Solutions

Examples:

- WordPress
- Jenkins
- SQL Server
- Ubuntu Pro

AWS Marketplace images may be:

- Free
- Paid
- Subscription Based

:contentReference[oaicite:1]{index=1}

---

# 📸 Instance Screenshot

AWS allows administrators to capture screenshots of running instances to view the current state of the server without connecting directly. :contentReference[oaicite:2]{index=2}

### Use Cases

- Troubleshooting
- Boot Failure Analysis
- Remote Diagnostics

---

# 🔑 Key Pair Fundamentals

Key Pairs provide secure authentication between users and EC2 instances.

### Components

#### Public Key

Stored in AWS.

#### Private Key

Downloaded to the local machine.

### Important Note

```text
Key Pair cannot be changed after instance creation.
```

:contentReference[oaicite:3]{index=3}

---

# 💾 Introduction to EBS

Amazon Elastic Block Store (EBS) is a persistent block storage service designed for EC2 instances. :contentReference[oaicite:4]{index=4}

### Features

- Persistent Storage
- High Availability
- Snapshots
- Encryption Support
- Dynamic Scaling

---

# ⚖️ EBS vs Instance Store

| Feature | EBS | Instance Store |
|----------|-----|---------------|
| Persistence | Permanent | Temporary |
| Data Retention | Retained after stop | Lost after stop |
| Backup Support | Snapshots Available | Not Available |
| Durability | High | Low |
| Use Case | Databases, Applications | Cache, Temporary Data |

### Important Note

```text
Every server does not support Instance Store.
```

:contentReference[oaicite:5]{index=5}

---

# 💰 AWS Cost Estimation

AWS provides an online calculator to estimate infrastructure costs before deployment. :contentReference[oaicite:6]{index=6}

## Steps to Calculate Cost

### Open AWS Pricing Calculator

```text
https://calculator.aws
```

### Create Estimate

Click:

```text
Create Estimate
```

### Configure Resources

Select:

- Region
- AWS Service
- Instance Type
- Storage
- Usage Hours

### View Estimated Cost

AWS generates estimated monthly costs automatically. :contentReference[oaicite:7]{index=7}

---

# 🌍 AWS Global Infrastructure

## Region

A geographical location containing AWS data centers.

Examples:

```text
Mumbai
Singapore
Ohio
Frankfurt
```

---

## Availability Zone (AZ)

Independent data centers within a Region.

Benefits:

- High Availability
- Disaster Recovery
- Fault Isolation

:contentReference[oaicite:8]{index=8}

---

## Edge Locations

Edge Locations are AWS sites used for content delivery and caching through services such as CloudFront. :contentReference[oaicite:9]{index=9}

### Benefits

- Reduced Latency
- Faster Content Delivery
- Improved User Experience

---

# 🖼️ Amazon Machine Image (AMI)

An Amazon Machine Image (AMI) is a pre-configured template used to create EC2 instances. It contains all necessary information required to launch a virtual machine. :contentReference[oaicite:10]{index=10}

### AMI Components

#### Operating System

Examples:

```text
Amazon Linux
Ubuntu
Windows Server
```

#### Application Software

- Web Servers
- Databases
- Frameworks

#### Root Volume Snapshot

A backup of the operating system and configuration.

#### Launch Permissions

Controls who can launch instances using the AMI.

:contentReference[oaicite:11]{index=11}

---

# 🏗️ Types of AMIs

## Public AMI

Available for everyone.

---

## Paid AMI

Available through AWS Marketplace with additional licensing charges.

---

## Shared AMI

Accessible only to specific AWS accounts authorized by the owner.

:contentReference[oaicite:12]{index=12}

---

# 🧪 Lab Task – Create a Custom AMI

## Objective

Create a reusable AMI from a configured Windows EC2 instance. :contentReference[oaicite:13]{index=13}

---

# Step 1: Launch a Windows EC2 Instance

Configure:

```text
Windows Server
t3.micro
```

---

# Step 2: Access Instance

Use RDP Client.

Retrieve:

- Username
- Password

Connect using Remote Desktop. :contentReference[oaicite:14]{index=14}

---

# Step 3: Create a Text File

Inside the server:

```text
sample.txt
```

This file helps verify that the AMI captures the server state.

:contentReference[oaicite:15]{index=15}

---

# Step 4: Install Software

Install:

```text
Git Bash
```

by copying the installer into the server and completing installation. :contentReference[oaicite:16]{index=16}

---

# Step 5: Stop the Instance

AWS recommends stopping the server before creating an AMI to ensure data consistency. :contentReference[oaicite:17]{index=17}

---

# Step 6: Create AMI

Navigate to:

```text
Actions
   ↓
Images and Templates
   ↓
Create Image
```

:contentReference[oaicite:18]{index=18}

---

# Step 7: Configure AMI

Enter:

```text
AMI Name
```

Choose whether to reboot the instance before image creation. :contentReference[oaicite:19]{index=19}

---

# Step 8: Create Image

Click:

```text
Create Image
```

AMI creation begins. :contentReference[oaicite:20]{index=20}

---

# Step 9: Verify AMI Creation

Navigate to:

```text
EC2
   ↓
AMIs
```

Status:

```text
Available
```

indicates successful creation. :contentReference[oaicite:21]{index=21}

---

# 🔒 AMI Deregistration Protection

Deregistration Protection prevents accidental deletion of AMIs. :contentReference[oaicite:22]{index=22}

### Benefits

- Prevents accidental removal
- Protects production images
- Improves reliability

---

# 🛡️ Termination Protection

AWS allows enabling Termination Protection to prevent accidental deletion of EC2 instances. :contentReference[oaicite:23]{index=23}

### Enable Termination Protection

```text
Actions
   ↓
Instance Settings
   ↓
Enable Termination Protection
```

---

# 📸 EBS Snapshots

An EBS Snapshot is a backup of an EBS volume stored in Amazon S3.

### Benefits

- Disaster Recovery
- Data Backup
- Fast Restoration
- Migration Support

Snapshot progress can be monitored from:

```text
EBS
   ↓
Snapshots
```

:contentReference[oaicite:24]{index=24}

---

# 🔐 Security Concepts Learned

- Key Pair Authentication
- Instance Protection
- AMI Protection
- Snapshot-Based Backup
- Secure Remote Access
- AWS Infrastructure Security

---

# 📚 Learning Outcomes

After completing this lecture, the following concepts were learned:

- Amazon EC2 Fundamentals
- Instance Types
- Scalability Concepts
- EC2 Lifecycle Management
- AWS Marketplace Usage
- Amazon Machine Images (AMI)
- EBS and Instance Store
- AWS Cost Estimation
- Snapshot Management
- AMI Creation Process
- Instance Protection Mechanisms

---

# 🛠️ Technologies and Services Used

| Service | Purpose |
|----------|----------|
| Amazon EC2 | Virtual Servers |
| Amazon EBS | Persistent Storage |
| Amazon AMI | Server Templates |
| AWS Marketplace | Prebuilt Images |
| AWS Pricing Calculator | Cost Estimation |
| RDP | Remote Access |
| Windows Server | Operating System |

---

# 📌 Conclusion

This lecture provided a comprehensive understanding of Amazon EC2 infrastructure, storage services, pricing estimation, scalability, and machine image management. Through the hands-on AMI creation lab, practical experience was gained in creating reusable server templates, managing snapshots, protecting instances, and understanding AWS best practices for cloud infrastructure deployment and management.
