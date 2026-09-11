<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket Logo"/>
</p>

# osTicket - Prerequisites and Installation

This project demonstrates the installation and configuration of **osTicket**, an open-source help desk ticketing system, on a **Windows 11 Azure Virtual Machine**.

## Environments and Technologies Used

- Microsoft Azure
- Azure Virtual Machines
- Windows 11
- Remote Desktop (RDP)
- Internet Information Services (IIS)
- PHP
- MySQL
- HeidiSQL
- osTicket

## Prerequisites

- Windows 10 Azure VM
- IIS with CGI enabled
- PHP Manager for IIS
- IIS URL Rewrite Module
- PHP 7.3.8
- Visual C++ Redistributable
- MySQL 5.5
- HeidiSQL
- osTicket v1.15.8

> **Security Note:** Credentials used in this lab were temporary lab credentials and are not included in this repository.

# Installation Steps

## 1. Create the Azure Virtual Machine

Create a Windows 11 Virtual Machine in Microsoft Azure and connect to it using Remote Desktop (RDP).

<p>
<img width="1366" height="871" alt="image" src="https://github.com/user-attachments/assets/fe11e25b-9af3-47b6-84c0-6da484bc5e72" />
</p>

## 2. Install IIS

Enable Internet Information Services and CGI:

`Control Panel → Programs → Turn Windows features on or off → IIS → World Wide Web Services → Application Development Features → CGI`

<p>
<img width="1297" height="702" alt="image" src="https://github.com/user-attachments/assets/53895e74-4c77-4583-b4c8-f1eae88dea71" />
</p>

## 3. Install PHP and Dependencies

Install:

- PHP Manager for IIS
- IIS URL Rewrite Module
- Visual C++ Redistributable

Create:

`C:\PHP`

Extract PHP 7.3.8 into the `C:\PHP` directory.

<p>
<img width="557" height="465" alt="image" src="https://github.com/user-attachments/assets/69721ef9-ec5e-422f-b4bf-96866ce415bf" />
</p>

## 4. Install MySQL

Install MySQL 5.5 using the standard configuration and create a local administrator account for the lab environment.

<p>
<img width="555" height="432" alt="image" src="https://github.com/user-attachments/assets/75a70e1c-e709-4315-82fd-83467def9f3f" />
</p>

## 5. Configure PHP in IIS

Open IIS Manager as Administrator.

Navigate to:

`PHP Manager → Register new PHP version`

Register:

`C:\PHP\php-cgi.exe`

Restart IIS.

<p>
<img width="1282" height="652" alt="image" src="https://github.com/user-attachments/assets/d2ce4719-7e04-4e6c-a508-88a2bfa9c006" />
</p>

## 6. Install osTicket

Extract the osTicket installation package.

Copy the `upload` folder to:

`C:\inetpub\wwwroot`

Rename the folder to:

`osTicket`

Final path:

`C:\inetpub\wwwroot\osTicket`

Restart IIS and open the osTicket website.

<p>
<img width="1266" height="665" alt="image" src="https://github.com/user-attachments/assets/08cf063e-f774-4a6a-942a-bc4167c5b693" />
</p>

## 7. Enable PHP Extensions

Enable the following extensions in PHP Manager:

- `php_imap.dll`
- `php_intl.dll`
- `php_opcache.dll`

Refresh the osTicket installer to verify the requirements.

<p>
<img width="1266" height="665" alt="image" src="https://github.com/user-attachments/assets/3ec67f40-2de2-4f63-863d-907e5d703225" />
</p>

## 8. Configure osTicket

Rename:

`ost-sampleconfig.php`

to:

`ost-config.php`

Location:

`C:\inetpub\wwwroot\osTicket\include`

Temporarily configure the required file permissions so the installer can modify the configuration file.

<p>
<img width="922" height="577" alt="image" src="https://github.com/user-attachments/assets/315f72b4-a857-4182-98b6-3f740a44d588" />
</p>

## 9. Create the Database

Install and open HeidiSQL.

Connect to the local MySQL server and create a database named:

`osTicket`

<p>
<img width="1055" height="661" alt="image" src="https://github.com/user-attachments/assets/396c3c1f-9998-47ea-87cd-0a3aef99557b" />
</p>

## 10. Complete the Installation

Return to the osTicket installer and configure the Help Desk and database connection.

Database settings:

- Database: `osTicket`
- Server: `localhost`
- User: MySQL lab account

Click **Install Now**.

<p>
<img width="1726" height="915" alt="1" src="https://github.com/user-attachments/assets/0bb0c80d-f8b3-4639-b548-c72809af6452" />
<img width="925" height="716" alt="2" src="https://github.com/user-attachments/assets/f8180296-df8a-4428-a77c-284f629172ff" />
</p>

## 11. Verify the Installation

Staff / Agent Portal:

`http://localhost/osTicket/scp/login.php`

<p>
<img width="1722" height="970" alt="image" src="https://github.com/user-attachments/assets/e35b86f5-93ce-49f7-a6b8-dcacdc54bb96" />
</p>

## 12. Post-Installation Security

Delete:

`C:\inetpub\wwwroot\osTicket\setup`

Restrict permissions on:

`C:\inetpub\wwwroot\osTicket\include\ost-config.php`

Set the configuration file to **Read Only** after installation.

## Skills Demonstrated

- Azure Virtual Machine deployment
- Remote Desktop administration
- IIS configuration
- PHP configuration
- MySQL database administration
- Web application deployment
- NTFS permissions
- Help Desk software installation
- Basic troubleshooting
- Post-installation security

## Project Outcome

Successfully deployed and configured an **osTicket Help Desk environment** on Microsoft Azure using IIS, PHP, and MySQL.
