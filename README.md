<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket Logo"/>
</p>

# osTicket - Prerequisites and Installation on Azure

## Project Overview

This project demonstrates the deployment and configuration of **osTicket**, an open-source help desk ticketing system, inside a **Microsoft Azure Windows Virtual Machine**.

The lab covers the complete installation process, including:

- Azure Virtual Machine deployment
- Remote Desktop administration
- IIS Web Server configuration
- PHP configuration
- MySQL database installation
- osTicket deployment
- Database creation and connection
- File permissions configuration
- Post-installation security configuration

---

## Environments and Technologies Used

- Microsoft Azure
- Azure Virtual Machines
- Remote Desktop Protocol (RDP)
- Windows 10
- Internet Information Services (IIS)
- PHP
- MySQL
- HeidiSQL
- osTicket

---

## Operating System Used

- Windows 10
- Azure Virtual Machine
- 4 vCPUs

---

## Prerequisites

The following components were used during the installation:

- Microsoft Azure Virtual Machine
- Internet Information Services (IIS)
- CGI
- PHP Manager for IIS
- IIS URL Rewrite Module
- PHP 7.3.8
- Microsoft Visual C++ Redistributable
- MySQL 5.5
- HeidiSQL
- osTicket v1.15.8

> **Security Note:** Credentials used during this project were created specifically for the isolated lab environment. Passwords and sensitive credentials should never be stored in GitHub repositories or production documentation.

---

# Installation Steps

## 1. Create the Azure Virtual Machine

Create a Windows 10 Virtual Machine in Microsoft Azure.

Example configuration:

- **Virtual Machine Name:** `osticket-vm`
- **Operating System:** Windows 10
- **CPU:** 4 vCPUs
- **Administrator Account:** Local lab administrator

After deployment, obtain the public IP address of the Virtual Machine.

<p>
<img src="YOUR_SCREENSHOT_URL" width="80%" alt="Azure Virtual Machine"/>
</p>

---

## 2. Connect to the Virtual Machine Using RDP

Connect to the Azure VM using **Remote Desktop Protocol (RDP)**.

Use the public IP address of the Azure VM and the administrator credentials configured during deployment.

<p>
<img src="YOUR_SCREENSHOT_URL" width="80%" alt="Remote Desktop Connection"/>
</p>

---

## 3. Download the osTicket Installation Files

Inside the Virtual Machine, download and extract the osTicket installation files.

The extracted folder should contain the software and dependencies required for the installation.

Example:

```text
Desktop
└── osTicket-Installation-Files
