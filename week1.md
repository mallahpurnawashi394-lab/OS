![ssh key](/week-1-1.png)  
                             architecture-diagram.png    
# System Architecture Diagram Explanation  
This diagram illustrates the overall system architecture used for the CMPN202 server administration project. The environment consists of a host workstation, a virtualized Ubuntu Server, and network connectivity to the internet.  
1. User (Student)
•	User: Purnawashi Mallah
•	The student interacts with the system using:
o	Web browser
o	Terminal (CLI)
•	All administration tasks are performed either directly on the host or via the Ubuntu Server terminal.
3. Workstation (Host System)
•	Operating System: Windows 10 / Windows 11
•	The host machine provides:
o	CPU, RAM, and Disk resources
o	VirtualBox hypervisor for virtualization
o	Management interface for starting/stopping the VM
The workstation does not act as a server itself; it only hosts the virtual environment.
5. Virtualization Layer – Oracle VirtualBox
•	Software: Oracle VirtualBox
•	VirtualBox runs on the Windows host and is responsible for:
o	Creating and managing the Ubuntu Server VM
o	Allocating virtual hardware (CPU, RAM, disk)
o	Providing network access using NAT mode
This abstraction allows the server environment to run independently from the host OS.
7. Ubuntu Server Virtual Machine
•	Operating System: Ubuntu Server 24.04 LTS
•	Role: Primary server used throughout CMPN202 tasks
Planned and configured components include:
•	OpenSSH Server – Enables secure remote access
•	UFW Firewall (planned) – For host-based security
•	Monitoring & Tools (planned) – For performance and security monitoring in later weeks
This VM is the core platform for all configuration, security, and evaluation tasks across Weeks 1–7.
9. Network Configuration
•	Network Mode: NAT (Network Address Translation)
•	Network Interface: enp0s3
•	Example IP Address: 10.0.2.15
NAT allows the Ubuntu Server VM to:
•	Access the internet securely
•	Download system updates and packages
•	Communicate with Ubuntu repositories
The VM is isolated from the wider network while still maintaining outbound connectivity.
11. Internet & Ubuntu Repositories
•	The Ubuntu Server connects to:
o	Ubuntu package repositories
o	Security update servers
•	This enables:
o	System updates
o	Software installation
o	Long-term maintenance support
2. Distribution Selection
Why Ubuntu Server 24.04 LTS?
Ubuntu Server 24.04 LTS was selected as the server operating system for this project after comparing it with other popular server distributions such as CentOS Stream, Rocky Linux, and Debian.
Justification:
•	Long-Term Support (LTS): Ubuntu Server 24.04 provides 5 years of standard support, ensuring stability and security updates until 2029.
•	Strong Documentation: Ubuntu has extensive official documentation and community support, which is essential for learning and troubleshooting.
•	Industry Adoption: Ubuntu Server is widely used in enterprise, cloud, and DevOps environments (AWS, Azure, OpenStack).
•	Package Management: Uses apt, which is beginner-friendly and well-documented.
•	Security Features: Includes built-in tools such as UFW firewall, AppArmor, and regular security patches.
•	Cloud & Virtualization Friendly: Optimized for virtual environments like VirtualBox and VMware.
Comparison Summary:
Distribution	Reason Not Chosen
CentOS Stream	Rolling release, less stable for coursework
Rocky Linux	Enterprise-focused, less beginner-friendly
Debian	Very stable but slower package updates
4. Workstation Configuration
 VirtualBox Justification
Host Operating System: Windows 10 / Windows 11
Virtualization Software: Oracle VirtualBox
Why VirtualBox?
•	Free and Open Source
•	Cross-Platform: Works on Windows, Linux, and macOS
•	Easy VM Management: GUI-based VM creation and control
•	Snapshot Support: Allows rollback if configuration errors occur
•	Network Modes: Supports NAT, Bridged, and Internal networking
•	Course Compatibility: Recommended and commonly used in academic environments
Virtual Machine Configuration (Example):
•	CPU: 2 cores
•	RAM: 4 GB
•	Disk: 25 GB (VDI, dynamically allocated)
•	OS: Ubuntu Server 24.04 LTS


 
6. Network Configuration
Network Mode: NAT (Network Address Translation)
Network Interface: enp0s3
Example IP Address: 10.0.2.15
Why NAT was chosen:
•	Allows the VM to access the internet securely
•	Prevents direct exposure of the VM to the external network
•	Simplifies configuration for beginners
•	Ideal for downloading updates and packages
Network Capabilities:
•	Internet access for:
o	System updates
o	Package installation
o	Ubuntu repositories
•	SSH access from the host machine
Security Advantage:
NAT reduces attack surface by isolating the VM from the external network while still allowing outbound traffic.
 
Screenshot 4 – Network Configuration  

5. CLI System Evidence
Command-Line System Specifications
The following commands were executed on the Ubuntu Server VM to document system specifications.
 
 

