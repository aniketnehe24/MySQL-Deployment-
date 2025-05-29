# MySQL-Deployment-
## 📌 Project Scope

- Install and configure MySQL Server
- - Harden MySQL for production
- Manage users and databases
- - Setup firewall and service management
- Perform basic backups
---

## ✅ Prerequisites

- RHEL/CentOS/AlmaLinux 8 or 9
- - sudo/root access
- Internet connection
---

## 🚀 Step-by-Step MySQL Deployment

### 1. Update Your System

```bash
sudo dnf update -y

2. Install MySQL Server
sudo dnf install @mysql -y

> If @mysql doesn't work, use:



sudo dnf install mysql-server -y

3. Start and Enable MySQL Service
sudo systemctl enable mysqld
sudo systemctl start mysqld

4. Secure MySQL Installation
sudo mysql_secure_installation

Choose secure options:

Set strong root password

Remove anonymous users

Disallow remote root login

Remove test DB

Reload privileges



---

🔐 Firewall Configuration

sudo firewall-cmd --permanent --add-service=mysql
sudo firewall-cmd --reload


---

👤 User and Privilege Management

Create New Database and User

mysql -u root -p

CREATE DATABASE admin_db;
CREATE USER 'adminuser'@'localhost' IDENTIFIED BY 'StrongPassword!';
GRANT ALL PRIVILEGES ON admin_db.* TO 'adminuser'@'localhost';
FLUSH PRIVILEGES;,
EXIT;


---

💾 Backup MySQL Database

Simple Backup Command

mysqldump -u root -p admin_db > /backups/admin_db.sql



> You can automate this with cron for regular backups.




---

🧾 Important File Locations


---

🔁 Service Management

sudo systemctl status mysqld
sudo systemctl restart mysqld
sudo systemctl stop mysqld


---

❌ Uninstall MySQL (Optional)

sudo systemctl stop mysqld
sudo dnf remove mysql-server -y
sudo rm -rf /var/lib/mysql


---

✅ Deployment Complete

Our SQL Server is now deployed, secured, and ready for database operations and user management.

