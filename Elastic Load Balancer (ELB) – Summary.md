# 3. Elastic Load Balancer (ELB) – Summary

	- AWS guarantees that it will be working
	- AWS takes care of upgrades, maintenance, high availability
	- AWS provides only a few configuration knobs
	- Application Load Balancer (HTTP / HTTPS only) – Layer 7
	- Network Load Balancer (ultra-high performance, allows for TCP) – Layer 4
	- Gateway Load Balancer – Layer 3
	- Classic Load Balancer (retired in 2023) – Layer 4 & 7
 
# Auto Scaling Groups – Scaling Strategies

- **Manual Scaling:** Update the size of an ASG manually.

- **Dynamic Scaling:** Respond to changing demand
	- **Simple / Step Scaling:**
		- When a CloudWatch alarm is triggered (e.g., CPU > 70%), add 2 units
		- When a CloudWatch alarm is triggered (e.g., CPU < 30%), remove 1 unit
	- **Target Tracking Scaling:**
		- Example: Keep average ASG CPU at around 40%
	- **Scheduled Scaling:**
		- Anticipate scaling based on known usage patterns
		- Example: Increase min. capacity to 10 at 5 pm on Fridays

- **Predictive Scaling:**
	- Uses Machine Learning to predict future traffic ahead of time
	- Automatically provisions the right number of EC2 instances in advance

- Useful when your load has predictable time-based patterns
