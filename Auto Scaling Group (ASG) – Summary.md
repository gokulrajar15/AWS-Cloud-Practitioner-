# 4. Auto Scaling Group (ASG) – Summary

Auto Scaling Groups (ASG) is a service that allows you to automatically adjust the number of EC2 instances in your application based on demand. It helps ensure that you have the right amount of compute capacity to handle traffic while optimizing costs.

- In real-life, the load on your websites and applications can change
- In the cloud, you can create and get rid of servers very quickly
- The goal of an Auto Scaling Group (ASG) is to:
	- Scale out (add EC2 instances) to match an increased load
	- Scale in (remove EC2 instances) to match a decreased load
	- Ensure a minimum and maximum number of machines are running
	- Automatically register new instances to a load balancer
	- Replace unhealthy instances
- **Cost Savings:** Only run at optimal capacity (principle of the cloud)
