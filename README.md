# LAMP Stack Installation and Configuration on Ubuntu

## Introduction

This guide provides a step-by-step process for installing and configuring the LAMP (Linux, Apache, MySQL/MariaDB, PHP) stack on Ubuntu. The LAMP stack is essential for hosting dynamic websites and web applications. We will also cover how to configure and test the installation by creating a database, writing PHP scripts, and managing backups.

## **Prerequisites**

To proceed with the installation and configuration of the LAMP stack on Ubuntu, ensure you meet the following prerequisites:

**Operating System** :

* A server instance running Ubuntu 22.04 LTS or Ubuntu 24.04.
* Ensure your system is up to date with the latest patches and updates.

**Non-root User with Sudo Privileges** :

* You must have a non-root user configured with sudo privileges to manage software installations and configurations.

**Basic Firewall Setup (UFW)** :

* Ensure the **Uncomplicated Firewall (UFW)** is configured, allowing HTTP (port 80) and HTTPS (port 443) traffic.
* If UFW is not installed, you can install and configure it using:

```bash
sudo apt install ufw
sudo ufw enable
sudo ufw allow OpenSSH
```

**Public IP Address** :

* If you are working on a remote server, ensure that you have the public IP address of the server to access the web services after the LAMP stack is installed.
