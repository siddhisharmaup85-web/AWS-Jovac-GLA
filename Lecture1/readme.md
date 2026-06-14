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
