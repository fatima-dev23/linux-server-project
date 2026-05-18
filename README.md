🧠 TechNova Solutions — Linux Server Environment Setup

Student: Fatima Sarwar
Role: Linux System Administrator
Environment: Ubuntu 22.04.5 LTS (VirtualBox)

📌 Project Overview

This project simulates a real-world Linux server environment for TechNova Solutions.
It focuses on secure user management, structured directory architecture, Apache web hosting, and system monitoring using core Linux tools.


📂 1. System Architecture

Created a structured directory layout for better organization and scalability:

sudo mkdir -p technova_project/{website,backup,logs,scripts,developers_data}
Structure:
website/ → Hosted Apache web content
backups/ → System and project backups
logs/ → Application/system logs
scripts/ → Automation scripts
developers_data/ → Team-related files


👥 2. User & Group Management

Implemented role-based access using Linux groups:

User	Group	Role
Ahmed	frontend_team	Frontend Developer
Sana	backend_team	Backend Developer
Usman	devops_team	DevOps Engineer

Verified using:

id
getent group


🔐 3. Permissions & Security

Applied Principle of Least Privilege:

Directory	Permission	Owner	Access Control
website	755	ahmed	Public read, owner full control
backups	700	root	Restricted access
logs	755	sana	Controlled access
scripts	744	usman	Read-only for others

Verified using:

ls -ld
stat


🌐 4. Apache Web Server Deployment

Installed and configured Apache2 for hosting the website.

Steps:
sudo apt install apache2 -y
sudo systemctl enable apache2
sudo systemctl start apache2
Deployment:

Hosted a custom index.html inside the project website directory.

📡 5. Network & System Verification
Verified internet connectivity using ping
Checked hostname configuration
Confirmed network interface availability
System Tools Used:
ping
hostname
ip a


📊 6. System Monitoring

Monitored system health using built-in Linux tools:

RAM Usage: ~6227 MB available
Disk Usage: ~60%
Uptime: ~2 hours 59 minutes

Commands used:

top
free -m
df -h
uptime


📦 7. Backup Strategy

Created compressed backup for portability and recovery:

tar -czvf tech_backup.tar.gz technova_project/


🧠 Key Learning Outcomes

Linux file system structure & permissions
User & group management (RBAC concept)
Apache web server deployment
System monitoring & diagnostics
Backup & recovery basics
