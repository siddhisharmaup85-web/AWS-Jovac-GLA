# (Lecture - 1)
# AWS EC2 Windows Server Setup 

## 📌 Overview
This project documents the process of creating and accessing a Windows Server instance on Amazon Web Services (AWS) using EC2 (Elastic Compute Cloud).

The project covers:
- Introduction to Cloud Computing
- AWS Account Creation
- AWS Regions and Availability Zones
- EC2 Instance Launch
- Security Groups Configuration
- Remote Desktop (RDP) Access
- Instance Management

## 🛠 Technologies Used
- Amazon Web Services (AWS)
- EC2 (Elastic Compute Cloud)
- Windows Server 2019 Base
- RDP (Remote Desktop Protocol)

## 🚀 Steps Performed

### 1. AWS Account Setup
- Created an AWS account.
- Explored AWS Management Console.
- Learned about Regions and Availability Zones.

### 2. Launching an EC2 Instance
- Selected the required AWS Region.
- Opened EC2 Dashboard.
- Clicked **Launch Instance**.
- Configured:
  - Instance Name
  - Windows Server 2019 Base AMI
  - Instance Type: `t3.micro`

### 3. Key Pair Creation
- Generated a Key Pair.
- Downloaded the Private Key (.pem).
- Used the key for secure authentication.

### 4. Network Configuration
- Selected Availability Zone.
- Created a Security Group.
- Allowed:
  - RDP (3389)
  - HTTP (80)
  - HTTPS (443)

### 5. Storage Configuration
- Allocated 30 GB SSD storage.

### 6. Launch Instance
- Launched the EC2 instance.
- Verified instance status as **Running**.

### 7. Accessing the Windows Server
- Opened EC2 Console.
- Selected the instance.
- Clicked **Connect → RDP Client**.
- Retrieved and decrypted the administrator password using the private key.
- Connected using:
  - Public IP Address
  - Username
  - Password

## 🔐 Security Features
- Key Pair Authentication
- Security Groups
- Controlled Remote Access via RDP

## 📷 Learning Outcomes
After completing this project, I learned:
- Basics of Cloud Computing
- AWS Regions and Availability Zones
- EC2 Instance Deployment
- Security Group Configuration
- Windows Server Remote Access
- AWS Resource Management

## 🧹 Cleanup
To avoid unnecessary AWS charges:
- Stop or Terminate the EC2 instance after use.

## 📚 References
- AWS Documentation
- AWS EC2 User Guide
- JOVAC AWS Training Program

# Task Given 
# AWS EC2 Linux Instance Setup and Access

## Project Overview
This project demonstrates how to create, access, and terminate a Linux EC2 instance on Amazon Web Services (AWS). The instance is accessed securely using SSH through Git Bash and a PEM private key file.

## Objectives
- Create a Linux EC2 instance on AWS
- Configure security groups for SSH access
- Connect to the Linux instance using Git Bash
- Verify successful connection
- Terminate the instance after use

## Prerequisites
- AWS Account
- AWS EC2 Access
- Git Bash installed on Windows
- PEM Key Pair downloaded during instance creation
- Internet Connection

## Steps Performed

### 1. Create a Linux EC2 Instance
1. Login to AWS Management Console.
2. Navigate to EC2 Dashboard.
3. Click **Launch Instance**.
4. Choose a Linux AMI (Amazon Linux/Ubuntu).
5. Select instance type (e.g., t2.micro).
6. Create or select an existing Key Pair.
7. Configure Security Group.
8. Launch the instance.

### 2. Configure Security Group
Add an inbound rule:

| Type | Protocol | Port | Source |
|--------|----------|--------|---------|
| SSH | TCP | 22 | My IP |

SSH is required for Linux instances, whereas RDP is used for Windows instances.

### 3. Access the Linux Instance
1. Download and install Git Bash.
2. Open the folder containing the PEM file.
3. Right-click and select **Git Bash Here**.
4. Connect using SSH:

```bash
ssh -i your-key.pem ec2-user@<Public-IP>
