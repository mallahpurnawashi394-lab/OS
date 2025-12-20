Week 2 — Security Planning and Testing Methodology

Module: CMPN202  
Student Name: Purnawashi Mallah  
System: Ubuntu Server 24.04 LTS (VirtualBox)  

# Phase 2: Security Planning and Testing Methodology  
This week focuses on designing a security baseline, performance monitoring plan, and identifying security threats with mitigation strategies for the Ubuntu Server environment.  

1. Performance Testing Plan
Objective
To monitor system performance and ensure the Ubuntu Server operates reliably under normal usage conditions.
Monitoring Methodology
Performance monitoring will be conducted using built-in Linux tools accessed remotely via SSH.
Tools Used

![ssh key](/week-2-1.png)
 
Tool	Purpose
top / htop	CPU and memory usage
free -h	RAM availability
df -h	Disk usage
uptime	System load
vmstat	CPU, memory, I/O stats

Testing Approach  
•	Monitor CPU and memory during idle and update operations  
•	Record disk usage after installing services  
•	Observe system load over time  
•	Identify abnormal resource spikes  
Frequency  
•	Daily checks during configuration changes  
•	Weekly review for long-term trends  

2. Security Configuration Checklist
SSH Hardening
•	OpenSSH server installed
•	Password authentication enabled initially
•	Root login disabled (planned)
•	SSH restricted to specific users (planned)
Firewall Configuration
•	UFW (Uncomplicated Firewall) planned
•	Allow only required ports:
o	SSH (Port 22)
•	Default deny incoming traffic
User Privilege Management
•	Non-root user created during installation
•	sudo used for administrative commands
•	Principle of least privilege applied
Automatic Updates
•	Security updates enabled during installation
•	Ensures timely patching of vulnerabilities
Network Security
•	NAT networking used
•	Server not directly exposed to public internet
•	SSH access controlled via VirtualBox host

4. Threat Model and Mitigation Strategies
Threat 1: Unauthorized SSH Access
Risk: Attackers attempting brute-force login
Mitigation:
•	Strong passwords
•	Planned SSH key authentication
•	Firewall restrictions

Threat 2: Unpatched Vulnerabilities  
Risk: Exploits due to outdated software  
Mitigation:  
•	Automatic security updates  
•	Regular system updates using apt  

Threat 3: Excessive User Privileges  
Risk: Accidental or malicious system changes  
Mitigation:  
•	Disable root login  
•	Use sudo only when required  
•	User privilege auditing  

4. Testing Validation Plan 
Security and performance configurations will be validated by:
•	Attempting SSH access
•	Verifying firewall rules
•	Checking running services
•	Monitoring system logs

Week 2 Outcome  
By the end of Week 2:  
•	A baseline security plan is defined  
•	Performance monitoring strategy is established  
•	Key security threats are identified and mitigated  
•	The system is prepared for hardening in Week 4  
 

