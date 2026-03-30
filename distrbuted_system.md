### Scalability, Elasticity, and Agility

- **Scalability:** Ability to accommodate a larger load by making the hardware stronger (scale up), or by adding nodes (scale out)
- **Elasticity:** Once a system is scalable, elasticity means that there will be some "auto-scaling" so that the system can scale based on the load. This is "cloud-friendly": pay-per-use, match demand, optimize costs
- **Agility:** (Not related to scalability – distractor) New IT resources are only a click away, which means that you reduce the time to make those resources available to your developers from weeks to just minutes.

# Scaling Strategies

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
