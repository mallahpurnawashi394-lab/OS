# Week 3 — Application Selection for Performance Testing  

Phase 3: Application Selection for Performance Testing  
The objective of this phase is to select representative server applications that generate different 
workload types (CPU, memory, disk I/O, and network). These applications will be used in later 
weeks to evaluate system performance, monitoring, and security behaviour on the Ubuntu Server 
virtual machine.  
1. Application Selection Matrix

![ssh key](/week-3-1.png)

These applications collectively provide a balanced performance testing environment covering all 
major system resources.
 
3. Installation Documentation (SSH-based)
 All applications were installed on the Ubuntu Server 24.04 LTS virtual machine using SSH from 
the host system.

 System Update
``` 
sudo apt update && sudo apt upgrade -y

``` 
Install stress-ng  
```
sudo apt install stress-ng -y

``` 
Install fio  
```
sudo apt install fio -y

``` 
Install iperf3  
```
sudo apt install iperf3 -y

``` 
Install Apache Web Server  
```
sudo apt install apache2 -y

``` 
Apache was enabled and started automatically:  
```
sudo systemctl enable apache2
sudo systemctl start apache2

```
5. Expected Resource Profiles

![ssh key](/week-3-2.png)
 
These expected profiles will be validated during performance testing in Week 6.  
7. Monitoring Strategy   
Monitoring will be performed using built-in Linux tools and additional monitoring utilities in 
later weeks.  
Monitoring Tools  
 top / htop → CPU and memory usage  
 free -h → Memory consumption  
 df -h / iostat → Disk usage and I/O  
 ip a / iperf3 output → Network activity  
 systemctl status apache2 → Web server status  
Monitoring Approach  
 Run each application individually to isolate its resource impact  
 Observe system metrics before, during, and after workload execution  
 Capture screenshots/log outputs as evidence  
 Compare observed behaviour against expected resource profiles  
