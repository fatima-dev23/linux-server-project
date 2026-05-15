TechNova Solutions: Linux Server Environment Setup 🚀
Student Name: Fatima Sarwar
Role: Linux System Administrator
Environment: Ubuntu 22.04.5 LTS (Oracle VM VirtualBox)  


📝 Project Scenario
As a System Administrator for TechNova Solutions, I was tasked with building a secure, multi-user Linux environment. The project involved setting up a professional directory structure, managing departmental user groups, configuring strict file permissions, and deploying a functional web server.

📂 1. Project Structure

I created a centralized project directory using the following command:
sudo mkdir -p technova_project/{website,backup,logs,scripts,developers_data}
Verified Structure:
website/: Contains the company landing page.
backups/: Secure storage for system archives.
logs/: Directory for system and application logs.
scripts/: Automation and maintenance scripts.
developers_data/: Shared storage for the development team.


👥 2. User & Group Management

To ensure departmental isolation and security, I created dedicated groups and users:
User	Team (Group)	Role
ahmed	frontend_team	Frontend Developer
sana	backend_team	Backend Developer
usman	devops_team	DevOps Engineer


🔍 User Verification (Task 4)

Using id and getent, I verified the system identities:
UID (User ID): A unique numerical value assigned by Linux to identify a user.
GID (Group ID): A unique number identifying the user's primary group.
Supplementary Groups: Additional groups the user belongs to, granting them permissions beyond their primary group (e.g., Ahmed is in both ahmed and frontend_team).


🔐 3. Permissions & Ownership

I applied the Principle of Least Privilege to secure the environment:
Website (755): Owned by ahmed. Public can read; owner has full control.
Backups (700): Owned by root. Only the SuperUser can access.
Logs (755): Owned by sana.
Scripts (744): Owned by usman.
Verification used: ls -ld and stat.


🌐 4. Web Deployment (Apache2)

I installed and configured the Apache Web Server to host the TechNova landing page.
Installation: sudo apt install apache2 -y
Service Management: Started and enabled Apache via systemctl.
Deployment: Created a custom index.html inside the website folder.
Website Content:
Company: TechNova Solutions
Managed By: DevOps Student: Fatima Sarwar


📡 5. Network Verification

I verified the server's connectivity and identity:
Ping Test: Successfully pinged google.com with 0% packet loss.
Hostname: fatima-VirtualBox


💡 Networking Concepts:

IP Address: The unique numerical label (like 142.250.202.238) assigned to the server for network communication.
Network Interface: The software/hardware bridge (e.g., enp0s3) that connects the VM to the network.
Packet Transmission: Data is broken into small "packets" that travel across the network and are reassembled at the destination.


📊 6. System Monitoring (Current Status)

Based on the top, free -m, df -h, and uptime commands, here is the server's health:
Available RAM: 6227 MB
Disk Usage: 60% (14GB Used of 24GB Total)
System Uptime: 2 hours and 59 minutes


📦 7. Bonus Task: Backup

To ensure data persistence, I created a compressed backup of the entire project:
sudo tar -czvf tech_backup.tar.gz technova_project/
