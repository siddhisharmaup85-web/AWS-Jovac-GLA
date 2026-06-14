# Lecture1
# AWS EC2 Linux Instance Setup and Access

## 📌 Project Title
AWS EC2 Linux Instance Creation, Remote Access using SSH, and Instance Termination

---

## 📖 Project Description

This project demonstrates the complete process of creating, accessing, managing, and terminating a Linux-based Virtual Machine (EC2 Instance) on Amazon Web Services (AWS). The task introduces the fundamentals of cloud computing and Infrastructure as a Service (IaaS) by using AWS EC2.

The Linux instance is accessed securely through SSH (Secure Shell) using a PEM key pair and Git Bash. This project helps users understand how cloud servers are deployed and managed in real-world environments.

---

## 🎯 Objectives

- Understand AWS EC2 services.
- Launch a Linux Virtual Machine in AWS.
- Configure Security Groups.
- Connect to the Linux server using SSH.
- Perform basic Linux operations.
- Understand public IP and remote access.
- Terminate cloud resources to avoid unnecessary charges.

---

# What is AWS EC2?

Amazon Elastic Compute Cloud (EC2) is a web service that provides scalable virtual servers in the cloud. EC2 allows users to create and manage virtual machines without purchasing physical hardware.

### Key Features

- On-demand virtual machines
- Multiple operating systems support
- Flexible scaling
- Secure access
- Pay-as-you-go pricing
- High availability

---

# Prerequisites

Before starting, ensure the following requirements are met:

- AWS Account
- Internet Connection
- Git Bash Installed
- Valid Email Address
- AWS Key Pair (.pem file)
- AWS Free Tier Eligible Account

---

# Architecture Overview

```text
User Machine
      │
      │ SSH (Port 22)
      ▼
AWS Security Group
      │
      ▼
Linux EC2 Instance
      │
      ▼
Amazon Cloud Infrastructure
```

---

# Step 1: Login to AWS Console

1. Open AWS Console.
2. Enter credentials.
3. Sign in successfully.
4. Navigate to EC2 Dashboard.

---

# Step 2: Launch a Linux EC2 Instance

### Open EC2 Dashboard

Services → Compute → EC2

### Launch Instance

Click:

```text
Launch Instance
```

### Configure Instance

#### Instance Name

```text
Linux-Server
```

#### Select AMI

Choose:

```text
Amazon Linux 2023
```

or

```text
Ubuntu Server
```

#### Instance Type

```text
t2.micro
```

Free Tier Eligible.

#### Create Key Pair

Click:

```text
Create New Key Pair
```

Example:

```text
linux-key
```

Download:

```text
linux-key.pem
```

Save the PEM file securely.

---

# Step 3: Configure Security Group

A Security Group acts as a virtual firewall.

### Add Inbound Rule

| Type | Protocol | Port | Source |
|--------|----------|--------|---------|
| SSH | TCP | 22 | My IP |

SSH access is required for Linux instances.

---

# Step 4: Launch Instance

Click:

```text
Launch Instance
```

AWS will create the Linux machine.

Instance State:

```text
Running
```

---

# Step 5: Obtain Public IP Address

Select the instance.

Copy:

```text
Public IPv4 Address
```

Example:

```text
65.2.xxx.xxx
```

This IP will be used for SSH connection.

---

# Step 6: Install Git Bash

Download Git Bash from:

https://git-scm.com

Install with default settings.

Verify installation:

```bash
git --version
```

---

# Step 7: Open Git Bash

Move the PEM file to a folder.

Example:

```text
Desktop/AWS-JOVAC
```

Right Click →

```text
Git Bash Here
```

---

# Step 8: Set PEM File Permissions

Run:

```bash
chmod 400 linux-key.pem
```

Purpose:

- Protect private key
- Restrict unauthorized access
- Required by SSH

---

# Step 9: Connect to Linux EC2 Instance

### Amazon Linux

```bash
ssh -i linux-key.pem ec2-user@PUBLIC-IP
```

Example:

```bash
ssh -i linux-key.pem ec2-user@65.2.xxx.xxx
```

### Ubuntu

```bash
ssh -i linux-key.pem ubuntu@PUBLIC-IP
```

Example:

```bash
ssh -i linux-key.pem ubuntu@65.2.xxx.xxx
```

---

# Successful Login

If connection succeeds:

```text
Last login: ...
[ec2-user@ip-172-31-x-x ~]$
```

You are now connected to the Linux server.

---

# Basic Linux Commands

### Current User

```bash
whoami
```

### Current Directory

```bash
pwd
```

### List Files

```bash
ls
```

### Create Directory

```bash
mkdir demo
```

### Enter Directory

```bash
cd demo
```

### Create File

```bash
touch test.txt
```

### View Files

```bash
ls -l
```

### Display Date

```bash
date
```

### System Information

```bash
uname -a
```

---

# Common Errors and Solutions

## Permission Denied

```bash
Permission denied (publickey)
```

### Solution

- Use correct username.
- Use correct PEM file.
- Check file permissions.

Amazon Linux:

```bash
ec2-user
```

Ubuntu:

```bash
ubuntu
```

---

## Connection Timed Out

```bash
Connection timed out
```

### Solution

- Verify Security Group.
- Ensure Port 22 is open.
- Check Public IP.

---

## Host Key Verification Failed

```bash
Host key verification failed
```

### Solution

Remove old key:

```bash
ssh-keygen -R PUBLIC-IP
```

---

# Security Best Practices

- Never share PEM files.
- Restrict SSH access to your IP.
- Terminate unused instances.
- Use strong IAM policies.
- Enable MFA on AWS account.

---

# Instance Termination

After completing the task:

### Select Instance

EC2 Dashboard → Instances

### Click

```text
Instance State
```

### Select

```text
Terminate Instance
```

### Confirm

```text
Terminate
```

Instance State:

```text
Terminated
```

---

# Skills Learned

- Cloud Computing Basics
- AWS EC2 Management
- Linux Administration
- SSH Authentication
- Security Group Configuration
- Remote Server Access
- Cloud Resource Management

---

# Technologies Used

| Technology | Purpose |
|------------|---------|
| AWS EC2 | Virtual Machine Hosting |
| Linux | Operating System |
| Git Bash | SSH Client |
| SSH | Secure Remote Access |
| Security Groups | Firewall Rules |

---

# Learning Outcome

By completing this project, users gain hands-on experience with AWS EC2 services, Linux server deployment, SSH-based remote access, cloud security configuration, and cloud resource lifecycle management. This project provides a strong foundation for cloud computing, DevOps, and system administration concepts.

---

## Author

**AWS JOVAC Training Program**

### Task
Lecture 1 – Create and Access a Linux Machine in EC2

### Platform

Amazon Web Services (AWS)

### Service Used

Amazon Elastic Compute Cloud (EC2)

### Status

✅ Completed Successfully
