# Week 7 — Security Audit and System Evaluation  
Phase 7: Security Audit and System Evaluation  
The goal of Week 7 was to conduct a security audit and evaluate the overall system 
configuration.  
# Security Audit Tools Used  
 Lynis – System security audit  
 nmap – Network security scanning  
 sshd_config review – SSH hardening verification  
 systemctl – Service inventory and justification  

# Lynis Security Audit  
 Lynis was executed using:
```
 sudo lynis audit system
```
 Audit identified:  
o Strong SSH configuration  
o Firewall enabled (UFW)  
o Automatic updates active  
 Minor hardening suggestions were reviewed and addressed where appropriate  
# Network Security Assessment (nmap)  
 Network scan performed from host machine:  
```
 nmap -sS <server-ip>
```  
 Results:  
o Only SSH (port 22) was accessible  
o All unnecessary ports were closed  
 Confirms minimal attack surface  
# SSH Security Verification  
 Password authentication disabled after key-based authentication enabled  
 Root login disabled  
 SSH access restricted to authorised user only  
# Service Inventory and Justification  
Service Status    Justification  
SSH Enabled Remote administration  
UFW Enabled Firewall protection  
cron Enabled System scheduling  
Others Disabled Reduced attack surface  
# Risk Assessment  
  Risk    Mitigation  
Brute-force SSH    Fail2ban + key-based auth  
Unpatched vulnerabilities Automatic updates  
Unauthorized access    Firewall + user privileges  

Residual risk is considered low for the intended system usage. 
