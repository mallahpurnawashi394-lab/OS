Week 3 — Application Selection for Performance Testing 
Phase 3: Application Selection for Performance Testing 
The objective of this phase is to select representative server applications that generate different 
workload types (CPU, memory, disk I/O, and network). These applications will be used in later 
weeks to evaluate system performance, monitoring, and security behaviour on the Ubuntu Server 
virtual machine. 
 
1. Application Selection Matrix 
Application Workload Type Category Justification 
stress-ng CPU & RAM intensive Performance testing 
tool 
Used to deliberately 
stress CPU cores and 
memory to evaluate 
system limits and 
observe performance 
under heavy load. 
fio Disk I/O intensive Storage benchmark 
Simulates real-world 
disk read/write 
operations to measure 
storage performance 
and latency. 
iperf3 Network intensive Network testing tool 
Measures network 
throughput and latency 
between host and VM, 
useful for NAT network 
evaluation. 
Apache2 Server workload Web server 
Represents a real
world server 
application handling 
HTTP requests, useful 
for combined CPU, 
memory, and network 
load testing. 
These applications collectively provide a balanced performance testing environment covering all 
major system resources. 
 
2. Installation Documentation (SSH-based) 
All applications were installed on the Ubuntu Server 24.04 LTS virtual machine using SSH from 
the host system. 
System Update 
sudo apt update && sudo apt upgrade -y 
Install stress-ng 
sudo apt install stress-ng -y 
Install fio 
sudo apt install fio -y 
Install iperf3 
sudo apt install iperf3 -y 
Install Apache Web Server 
sudo apt install apache2 -y 
Apache was enabled and started automatically: 
sudo systemctl enable apache2 
sudo systemctl start apache2 
3. Expected Resource Profiles 
Application CPU Usage Memory Usage Disk Usage Network Usage 
stress-ng 
fio 
iperf3 
Very High High 
Medium Low 
Medium Low 
Apache2 Medium Medium 
Low 
Very High 
None 
None 
None 
Very High 
Low–Medium Medium 
These expected profiles will be validated during performance testing in Week 6. 
4. Monitoring Strategy 
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
