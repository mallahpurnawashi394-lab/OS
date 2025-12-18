Assessment Week 4 
Phase 4: Initial System Configuration & Security 
Implementation 
1. SSH Configuration with Key-Based Authentication 
1.1 Generate SSH key (on workstation – Windows PowerShell / Git Bash) 
ssh-keygen -t ed25519 -C "purnawashi@cmpn202" 
 Press Enter for default location 
 Set passphrase (recommended)
![ssh key](images/ssh-key-generation.png)
Screenshot evidence: SSH key generation success 
1.2 Test key-based SSH login 
ssh purnawashi@10.0.2.15 
Logs in without password 
Screenshot: Successful SSH login prompt 
3. SSH Hardening (Disable Root Login & Password Login) 
Hardened SSH configuration with custom port, disabled root login, and user restrictions 
Key Implementation Steps: 
1. Generated 4096-bit RSA key pair on workstation: 
ssh-keygen -t rsa -b 4096 -f ~/.ssh/asus_server_key 
2. Copied public key to server: 
ssh-copy-id -i ~/.ssh/asus_server_key.pub -p 22 asus123@192.168.56.103 
3. Modified /etc/ssh/sshd_config: o Changed port from 22 to 2222 o Set 
PasswordAuthentication no o Set PermitRootLogin no o Added AllowUsers 
asus123 sysadmin 
4. Restarted SSH service: 
sudo systemctl restart ssh  
5. Firewall Configuration Firewall Status 
Status: active 
To       
Action  From 
2222/tcp ALLOW   192.168.56.1 
UFW firewall configured to only allow port 2222 from the workstation IP (192.168.56.1) 
Implementation: 
# Enable and configure firewall 
sudo ufw allow 2222/tcp 
sudo ufw allow from 192.168.56.1 to any port 2222 
sudo ufw --force enable 
3. User & Privilege Management (Non-root Admin User) 
User sysadmin may run the following commands on asus: 
(ALL : ALL) ALL 
Created ‘sysadmin’ user with full sudo privileges Implementation Steps: 
1. Created new user: 
sudo adduser sysadmin 
2. Added to sudo group: 
sudo usermod -aG sudo sysadmin 
3. Configured sudo privileges: 
sudo visudo 
4. SSH Connection Verification Successful SSH Connection with Key 
Screenshot: sudo access confirmation 
4. Firewall Configuration (UFW) 
Configuration Verification Script Created verify-config.sh to validate all configurations: 
bash 
#!/bin/bash 
echo "=== Server Configuration Verification ===" 
echo "1. SSH Configuration:" 
sudo grep -E "Port|PermitRootLogin|PasswordAuthentication|AllowUsers" 
/etc/ssh/sshd_config 
echo "2. Firewall Status:" 
sudo ufw status 
echo "3. User Privileges:" 
sudo -lU sysadmin 
echo "4. SSH Service Status:" 
systemctl status ssh --no-pager | head -10 
Screenshot: Full firewall ruleset 
5. Service Status Verification SSH Service Status 
Active: active (running) since Wed 2025-12-17 11:54:38 UTC 
SSH service running and enabled to start on boot 
7. Administrative Constraint Compliance  
All configurations were performed: 
 Via SSH 
 From workstation 
 As non-root user 
 Using sudo
