# 3. Elastic Load Balancer (ELB) – Summary

Elastic Load Balancing (ELB) is a service that automatically distributes incoming application traffic across multiple targets, such as EC2 instances, containers, and IP addresses. It helps improve the availability and scalability of your applications by ensuring that traffic is evenly distributed and that your application can handle varying levels of load.

	- AWS guarantees that it will be working
	- AWS takes care of upgrades, maintenance, high availability
	- AWS provides only a few configuration knobs
	- Application Load Balancer (HTTP / HTTPS only) – Layer 7
	- Network Load Balancer (ultra-high performance, allows for TCP) – Layer 4
	- Gateway Load Balancer – Layer 3
	- Classic Load Balancer (retired in 2023) – Layer 4 & 7
 
