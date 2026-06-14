# AWS JOVAC 2026 – Lecture 3
## Operating System Fundamentals and AMI-Based Instance Deployment

![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Operating System](https://img.shields.io/badge/OS-Fundamentals-blue)
![AMI](https://img.shields.io/badge/Amazon-Machine%20Image-green)
![Windows Server](https://img.shields.io/badge/Windows-Server-yellow)

---

# 📖 Project Overview

This lecture focused on understanding Operating System fundamentals, including the purpose, functions, components, and interfaces of an OS. The practical session continued the Amazon Machine Image (AMI) lab from the previous lecture by demonstrating how to launch a new EC2 instance from a custom AMI and verify that previously installed software and files were preserved. :contentReference[oaicite:0]{index=0}

The session combined theoretical concepts of operating systems with hands-on AWS implementation, helping learners understand how AMIs can be used as reusable templates for rapid server deployment.

---

# 🎯 Objectives

- Understand the concept of an Operating System.
- Learn the functions of an Operating System.
- Study the major components of an Operating System.
- Differentiate between CLI and GUI interfaces.
- Understand Server OS and Client OS.
- Continue working with Amazon Machine Images (AMI).
- Launch a new EC2 instance from a custom AMI.
- Verify persistence of files and installed software.
- Understand private AMIs and reusable server templates.

---

# 💻 Introduction to Operating System

An Operating System (OS) is system software that acts as an intermediary between users and computer hardware. It manages system resources and provides an environment for applications to execute efficiently. :contentReference[oaicite:1]{index=1}

### Examples of Operating Systems

#### Client Operating Systems

- Windows 10
- Windows 11
- macOS
- Ubuntu Desktop

#### Server Operating Systems

- Windows Server 2019
- Windows Server 2022
- Ubuntu Server
- Amazon Linux
- Red Hat Enterprise Linux

---

# 🖥️ What is an Operating System?

An Operating System is responsible for controlling hardware resources and providing services to application programs.

### Main Purpose

```text
User
 ↓
Operating System
 ↓
Hardware
```

The OS acts as a bridge between users and hardware resources.

---

# ⚙️ Functions of an Operating System

An Operating System performs several critical functions.

## 1. Process Management

Responsible for:

- Creating processes
- Scheduling processes
- Terminating processes
- Managing CPU utilization

---

## 2. Memory Management

Responsible for:

- Allocating memory
- Deallocating memory
- Managing RAM usage
- Virtual memory management

---

## 3. File Management

Responsible for:

- Creating files
- Deleting files
- Organizing directories
- Managing permissions

---

## 4. Device Management

Controls:

- Keyboard
- Mouse
- Printer
- Storage Devices
- Network Interfaces

---

## 5. Security Management

Provides:

- Authentication
- Authorization
- Access Control
- User Management

---

## 6. Resource Management

Efficiently manages:

- CPU
- Memory
- Storage
- Network Resources

---

# 🏗️ Components of an Operating System

An Operating System consists of multiple components working together.

```text
User
 ↓
Shell / GUI
 ↓
Kernel
 ↓
Hardware
```

### Major Components

#### Kernel

Core component responsible for managing hardware resources.

#### File System

Manages storage and organization of files.

#### Device Drivers

Enable communication with hardware devices.

#### System Libraries

Provide APIs and services for applications.

#### User Interface

Allows interaction between users and the operating system.

---

# 🖱️ Operating System Interfaces

Operating Systems provide different methods for user interaction. :contentReference[oaicite:2]{index=2}

---

## Command Line Interface (CLI)

A text-based interface where commands are typed manually.

### Examples

```bash
dir
cd
mkdir
ls
pwd
```

### Advantages

- Faster for experienced users
- Less resource consumption
- Powerful automation capabilities

### Examples of CLI Environments

- Command Prompt
- PowerShell
- Linux Terminal
- Git Bash

---

## Graphical User Interface (GUI)

A visual interface using windows, icons, buttons, and menus.

### Advantages

- Easy to learn
- User friendly
- Visual navigation

### Examples

- Windows Desktop
- Ubuntu Desktop
- macOS

---

# 🖥️ Server OS vs Client OS

| Feature | Client OS | Server OS |
|----------|-----------|-----------|
| Purpose | Personal Use | Server Management |
| Users | Single User | Multiple Users |
| Performance | Standard | High Performance |
| Hardware Support | Limited | Advanced |
| Examples | Windows 11 | Windows Server 2019 |

---

## Client Operating System

Designed for end users.

Examples:

```text
Windows 11
macOS
Ubuntu Desktop
```

---

## Server Operating System

Designed for hosting applications and services.

Examples:

```text
Windows Server 2019
Amazon Linux
Ubuntu Server
```

---

# 🖼️ AMI Lab Continuation

The practical session continued the AMI lab created in the previous lecture. :contentReference[oaicite:3]{index=3}

---

# 🔍 Viewing Created AMIs

After successful AMI creation:

```text
EC2
 ↓
Images
 ↓
AMIs
```

The created AMI appears in the AMI section. :contentReference[oaicite:4]{index=4}

---

# ⚙️ Customizing AMI Display Attributes

AWS allows customization of displayed attributes.

### Steps

```text
Preferences (Gear Icon)
 ↓
Select Required Attributes
```

This helps administrators view only relevant AMI information. :contentReference[oaicite:5]{index=5}

---

# 🗑️ Terminating Original Instance

After AMI creation, the original instance can be terminated safely because the AMI now contains the complete server configuration. :contentReference[oaicite:6]{index=6}

---

# 🚀 Launching a New Instance from AMI

The primary objective of the lab is to recreate the server using the AMI template. :contentReference[oaicite:7]{index=7}

---

## Step 1: Open AMI Section

Navigate to:

```text
EC2
 ↓
AMIs
```

Select:

```text
My AMIs
```

:contentReference[oaicite:8]{index=8}

---

## Step 2: Launch Instance

Click:

```text
Launch Instance from AMI
```

---

## Step 3: Select Instance Type

Choose any instance type according to requirements.

Examples:

```text
t2.micro
t3.micro
```

:contentReference[oaicite:9]{index=9}

---

## Step 4: Select Key Pair

Choose the desired key pair for authentication. :contentReference[oaicite:10]{index=10}

---

## Step 5: Select Availability Zone

The instance can be launched in:

- Same Availability Zone
- Different Availability Zone

depending on project requirements. :contentReference[oaicite:11]{index=11}

---

# 🔒 Private AMI Verification

After launching the instance:

### Open Instance Details

Check:

```text
AMI Used
```

The details should indicate that a **Private AMI** was used for instance creation. :contentReference[oaicite:12]{index=12}

---

# 🌐 Accessing the New Instance

Use the same procedure followed previously for Windows Server access.

### Requirements

- Public IP Address
- Username
- Password

### Connection Method

```text
RDP Client
 ↓
Enter Public IP
 ↓
Enter Credentials
 ↓
Connect
```

:contentReference[oaicite:13]{index=13}

---

# ✅ Verification of AMI Functionality

After logging in to the new instance, verify that the AMI successfully preserved the server state.

### Check for TXT File

Verify that the text file created in the original instance exists.

Example:

```text
sample.txt
```

### Check for Git Bash

Verify that Git Bash remains installed.

This confirms that the AMI captured the complete system configuration. :contentReference[oaicite:14]{index=14}

---

# 🏗️ AMI Deployment Architecture

```text
Original EC2 Instance
        │
        ▼
 Create AMI
        │
        ▼
 Private AMI
        │
        ▼
 Launch New EC2 Instance
        │
        ▼
 Same Files + Same Software + Same Configuration
```

---

# 🔐 Security Concepts Learned

## Key Pair Authentication

Secure access to EC2 instances.

---

## Private AMIs

Restrict access to authorized AWS users.

---

## Template-Based Deployment

Ensures consistent server configurations.

---

## Reusable Infrastructure

Reduces deployment time and configuration errors.

---

# 📚 Learning Outcomes

After completing this lecture, the following concepts were learned:

- Operating System Fundamentals
- Functions of Operating Systems
- Components of Operating Systems
- CLI vs GUI
- Server OS vs Client OS
- Amazon Machine Image Management
- Private AMIs
- Instance Recreation Using AMIs
- Infrastructure Replication
- Template-Based Cloud Deployment

---

# 🛠️ Technologies and Services Used

| Technology / Service | Purpose |
|---------------------|----------|
| AWS EC2 | Virtual Servers |
| Amazon AMI | Server Templates |
| Windows Server | Operating System |
| RDP Client | Remote Access |
| Git Bash | Installed Software Verification |
| AWS Console | Infrastructure Management |

---

# 📌 Conclusion

This lecture introduced Operating System fundamentals and demonstrated how Amazon Machine Images (AMIs) simplify cloud infrastructure deployment. By launching a new EC2 instance from a custom AMI, the exact server environment—including installed software, files, and configurations—was replicated successfully. This practical implementation highlighted the importance of reusable infrastructure, rapid deployment, consistency, and efficient cloud resource management.
