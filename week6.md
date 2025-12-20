# Week 6 — Performance Evaluation and Analysis  
Phase 6: Performance Evaluation and Analysis  
The objective of Week 6 was to evaluate system performance under different workloads and 
analyse operating system behaviour. Performance testing focused on CPU, memory, disk I/O, 
network throughput, latency, and service response times.  
Testing Methodology  
Performance metrics were collected using standard Linux monitoring tools executed via SSH:  

![ssh key](/week-6-1.png)

All tests were conducted under baseline conditions and then repeated under simulated load.  
Testing Scenarios  
1. Baseline Performance Testing
 System idle with SSH service running
 No additional workload
3. Application Load Testing
 CPU load generated using stress
 Memory allocation tested with stress --vm
 Disk activity simulated using file read/write operations
5. Bottleneck Identification
 Observed CPU spikes during stress testing
 Minor memory pressure when multiple processes executed simultaneously
7. Optimisation Testing
Two optimisations were implemented:
1. Disabled unnecessary services using systemctl disable
3. Enabled automatic updates to reduce performance impact during peak usage
Performance Metrics Table

![ssh key](/week-6-2.png)  

Network Performance Analysis  
 NAT networking provided stable outbound connectivity   
 Latency remained low and consistent  
 No packet loss observed during testing  

Optimisation Results  

![ssh key](/week-6-3.png)  

Conclusion (Week 6)  
The Ubuntu Server demonstrated stable performance under both baseline and load conditions.  
Performance bottlenecks were minimal and acceptable for a small server environment.  
Implemented optimisations improved efficiency and reliability.  


