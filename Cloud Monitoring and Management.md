# 11. Cloud Monitoring and Management

### 11.1 AWS CloudWatch metrics and CloudWatch alarm

- CloudWatch Metrics: collect and track metrics, collect and monitor log files, set alarms, and automatically react to changes in your AWS resources

#### Amazon CloudWatch Alarms

- Alarms are used to trigger notifications for any metric.
- Alarm actions include:
	- **Auto Scaling:** increase or decrease EC2 instances "desired" count
	- **EC2 Actions:** stop, terminate, reboot, or recover an EC2 instance
	- **SNS notifications:** send a notification into an SNS topic
- Various options: sampling, %, max, min, etc.
- You can choose the period on which to evaluate an alarm.
- Example: create a billing alarm on the CloudWatch Billing metric.
- Alarm States: OK, INSUFFICIENT_DATA, ALARM

### 11.2 AWS CloudTrail

- AWS CloudTrail provides governance, compliance, and audit for your AWS Account.
- CloudTrail is enabled by default, ensuring all API activity is tracked automatically.
- Get a history of events and API calls made within your AWS Account via:
	- Console
	- SDK
	- CLI
	- AWS Services
- Logs from CloudTrail can be sent to CloudWatch Logs or S3 for centralized monitoring and long-term retention.
- A trail can be applied to all regions (default) or a single region for granular control.
- If a resource is deleted in AWS, investigate CloudTrail first for a complete audit trail.

### 11.3 Amazon CloudWatch Logs

- CloudWatch Logs can collect logs from various AWS services and resources:
	- Elastic Beanstalk: application logs
	- ECS: container logs
	- AWS Lambda: function logs
	- CloudTrail: filtered event logs
	- CloudWatch log agents: on EC2 machines or on-premises servers
	- Route53: DNS query logs
- Enables real-time monitoring and analysis of logs for operational visibility.
- Adjustable CloudWatch Logs retention for compliance and cost optimization.

### 11.4 Amazon EventBridge (formerly CloudWatch Events)

- EventBridge enables event-driven architectures by scheduling cron jobs (scheduled scripts) and defining event patterns to react to AWS service activities.
- Example: Schedule a Lambda function to run every hour, or trigger an SNS topic with email notification when an IAM Root User signs in.
- Supports triggering Lambda functions, sending SQS/SNS messages, and integrating with other AWS services for automated workflows.

### 11.5 AWS X-Ray

- AWS X-Ray helps developers analyze and debug production applications, especially those built using a microservices architecture.
- Provides insights into application performance and identifies bottlenecks by tracing requests as they travel through the application.
- X-Ray collects data about requests, including latency, errors, and exceptions, and visualizes it in a service map for easy analysis.
- Use cases: performance optimization, error analysis, and debugging of distributed applications.

### 11.6 AWS Health Dashboard – Service History
- Shows all regions and all services health status in a single view.
- Displays historical information for each day, allowing you to track past service interruptions and performance.
- Offers an RSS feed for real-time updates and notifications.
- Previously called AWS Service Health Dashboard.

### 11.7 AWS Health Dashboard – Your Account
- Previously called AWS Personal Health Dashboard (PHD).
- Provides alerts and remediation guidance when AWS is experiencing events that may impact your account.
- Offers a personalized view into the performance and availability of AWS services underlying your resources.
- Displays relevant and timely information to help manage events in progress and provides proactive notifications for scheduled activities.
- Can aggregate health data from an entire AWS Organization for centralized monitoring.
