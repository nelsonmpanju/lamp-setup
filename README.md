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
* 

## **1. Installing the LAMP Stack**

### **Step 1: Install Apache (Web Server)**

Apache is the web server software responsible for serving web pages. Follow these steps to install and configure Apache:

* **Update the package manager cache** :

```bash
sudo apt update
```

* **Install Apache** :

```bash
sudo apt install apache2 -y
```

* **Enable and start Apache** :

```bash
sudo systemctl enable apache2
sudo systemctl start apache2
```

* **Verify Apache installation** :
  * Open a browser and navigate to `http://localhost` or `http://your-server-ip`. You should see the default Apache page.

![Apache](./screenshots/apache2.png)

### **Step 2: Install MySQL or MariaDB (Database Server)**

You can use either MySQL or MariaDB. For this task, we'll install  **MariaDB** :

* **Install MariaDB** :

```bash
sudo apt install mariadb-server mariadb-client -y
```

* **Secure MariaDB** :
  Run the built-in security script to remove weak defaults:

```bash
sudo mysql_secure_installation
```

* Follow the prompts to set a root password, remove anonymous users, disallow remote root login, and remove the test database.

* **Verify MariaDB installation** :

```bash
sudo systemctl status mariadb
```

![mariadb](./screenshots/mariadb-active.png)
