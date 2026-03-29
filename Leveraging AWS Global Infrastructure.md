# 10. Leveraging AWS Global Infrastructure

## 10.1 AWS Global Infrastructure

### Why make a global application?

- A global application is an application deployed in multiple geographies.
- On AWS: this could be Regions and/or Edge Locations.
- **Decreased Latency**
	- Latency is the time it takes for a network packet to reach a server.
	- It takes time for a packet from Asia to reach the US.
	- Deploy your applications closer to your users to decrease latency, better experience.
- **Disaster Recovery (DR)**
	- If an AWS region goes down (earthquake, storms, power shutdown, politics)…
	- You can fail-over to another region and have your application still working.
	- A DR plan is important to increase the availability of your application.
- **Attack protection:** distributed global infrastructure is harder to attack.
## 10.2 Amazon Route 53 Overview

- **Route 53** is a Managed DNS (Domain Name System) service.
- DNS is a collection of rules and records which helps clients understand how to reach a server through URLs.

### Common DNS Records in AWS
- `A record (IPv4)`: www.google.com → 12.34.56.78
- `AAAA record (IPv6)`: www.google.com → 2001:0db8:85a3:0000:0000:8a2e:0370:7334
- `CNAME`: search.google.com → www.google.com (hostname to hostname)
- `Alias`: example.com → AWS resource (e.g., ELB, CloudFront, S3, RDS, etc.)

### Route 53 Routing Policies

- **Simple Routing Policy**: No health checks. Maps a domain to a single resource (e.g., foo.example.com → 11.22.33.44).
- **Weighted Routing Policy**: Distributes traffic across multiple resources based on assigned weights (e.g., 70%, 20%, 10%).
- **Latency Routing Policy**: Routes traffic to the region that provides the lowest latency for the user.
- **Failover Routing Policy**: Used for disaster recovery. Routes traffic to a primary resource unless it is unhealthy, then fails over to a secondary resource.

### 10.3 Amazon CloudFront Overview

- **CloudFront** is a Content Delivery Network (CDN) from AWS.
- Improves read performance by caching content at the edge locations.
- Enhances user experience by delivering content closer to users.
- Provides hundreds of Points of Presence globally (edge locations, caches).
- Offers DDoS protection due to its global distribution and integrates with AWS Shield and AWS Web Application Firewall.


### 10.4 S3 Transfer Acceleration

- S3 Transfer Acceleration increases transfer speed by uploading files to an AWS edge location, which then forwards the data to the S3 bucket in the target region.
- Uses AWS global edge locations for fast uploads, both public and private.
- Useful for transferring files across continents or to distant regions.
- Test the tool at: https://s3-accelerate-speedtest.s3-accelerate.amazonaws.com/en/accelerate-speed-comparison.html

### 10.5 AWS Global Accelerator

- AWS Global Accelerator improves global application availability and performance using the AWS global network.
- Leverages AWS internal network to optimize the route to your application (up to 60% improvement).
- Provides 2 Anycast IP addresses for your application; traffic is sent through AWS Edge Locations.
- Edge locations forward the traffic to your application, ensuring efficient and reliable delivery.

### 10.6 AWS Outposts

- AWS Outposts enables hybrid cloud by allowing businesses to keep on-premises infrastructure alongside AWS cloud infrastructure.
- Two ways to manage IT systems:
	- One for the AWS cloud (using AWS console, CLI, APIs)
	- One for on-premises infrastructure
- AWS Outposts are "server racks" that provide the same AWS infrastructure, services, APIs, and tools to build applications on-premises just as in the cloud.
- AWS will set up and manage Outposts Racks within your on-premises infrastructure, enabling you to leverage AWS services on-premises.

### 10.7 AWS WaveLength

- WaveLength Zones are infrastructure deployments embedded within telecommunications providers' datacenters at the edge of 5G networks.
- Brings AWS services (e.g., EC2, EBS, VPC) to the edge of 5G networks.
- Enables ultra-low latency applications through 5G networks.
- Traffic remains within the Communication Service Provider (CSP) network.
- Provides high-bandwidth and secure connection to the parent AWS Region.
- No additional charges or service agreements required.
- Use cases: Smart Cities, ML-assisted diagnostics, Connected Vehicles, Interactive Live Video Streams, AR/VR, Real-time Gaming, and more.


### 10.8 AWS Local Zones

- AWS Local Zones place AWS compute, storage, database, and other selected services closer to end users for latency-sensitive applications.
- Allows you to extend your VPC to more locations—an "extension of an AWS Region".
- Compatible with EC2, RDS, ECS, EBS, ElastiCache, Direct Connect, and more.
- Example:
	- AWS Region: N. Virginia (us-east-1)
	- AWS Local Zones: Boston, Chicago, Dallas, Houston, Miami, etc.

## 10. Cloud Integration

### 10.1 SQS – Simple Queue Service

Queueing is a form of asynchronous service-to-service communication used in serverless and microservices architectures. It helps decouple and scale microservices, distributed systems, and serverless applications.

- Fully managed message queuing service
- Decouples and scales microservices, distributed systems, and serverless applications
- Two types of queues:
	- Standard Queues: unlimited throughput, at-least-once delivery, best-effort ordering
	- FIFO Queues: limited throughput, exactly-once processing, first-in-first-out delivery
- Use cases: decoupling application components, buffering and batch processing, asynchronous workflows, and more.


### 10.2 Amazon Kinesis

Data streaming service for real-time data processing and analytics.

- Collect, process, and analyze real-time streaming data
- Three main services:
	- Kinesis Data Streams: real-time data streaming for custom applications
	- Kinesis Data Firehose: fully managed service for loading streaming data into data lakes, warehouses, and analytics services
	- Kinesis Data Analytics: real-time analytics on streaming data using SQL
- Use cases: real-time analytics, log and event data collection, real-time metrics and reporting, and more.

### 10.3 Amazon SNS – Simple Notification Service

- Fully managed pub/sub messaging service
- The "event publishers" only send messages to one SNS topic.
- As many "event subscribers" as needed can listen to the SNS topic notifications.
- Each subscriber to the topic will get all the messages.
- Supports up to 12,500,000 subscriptions per topic and 100,000 topics limit.

### 10.4 Amazon MQ

- Managed message broker service for Apache ActiveMQ and RabbitMQ
- Supports industry-standard APIs and protocols (e.g., JMS, NMS, AMQP, STOMP, MQTT, WebSocket)
- Provides a managed message broker service for Apache ActiveMQ and RabbitMQ, making it easy to set up and operate message brokers in the cloud
- Use cases: application decoupling, message queuing, pub/sub messaging, and more
