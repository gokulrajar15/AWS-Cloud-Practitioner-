# 15. Other Services – Summary

This section covers additional AWS services that are useful for cloud operations, management, and integration, but do not fit into the main categories above.

## 15.1 AWS WorkSpaces

Amazon WorkSpaces is a Managed Desktop as a Service (DaaS) solution that allows easy provisioning of Windows or Linux desktops.

- Eliminates the need to manage on-premise VDI (Virtual Desktop Infrastructure)
- Fast and quickly scalable to thousands of users
- Secured data, integrates with AWS KMS
- Pay-as-you-go service with monthly or hourly rates

WorkSpaces provides secure access to virtual desktops, which can connect to corporate data centers or AWS Cloud resources.
## 15.2 Amazon AppStream 2.0

Amazon AppStream 2.0 is a Desktop Application Streaming Service.

- Delivers applications to any computer without the need to acquire or provision infrastructure
- Applications are accessed directly from within a web browser

This service enables users to run desktop applications remotely and securely, making them available on-demand from anywhere.
## 15.3 AWS IoT Core

AWS IoT Core is a managed service for the Internet of Things (IoT), enabling the connection of internet-connected devices to the AWS Cloud.

- Easily connect IoT devices to AWS
- Serverless, secure, and scalable to billions of devices and trillions of messages
- Applications can communicate with devices even when they aren’t connected
- Integrates with many AWS services (Lambda, S3, SageMaker, etc.)
- Build IoT applications that gather, process, analyze, and act on data

## 15.4 AWS AppSync

AWS AppSync is a service for storing and syncing data across mobile and web apps in real-time.

- Uses GraphQL (mobile technology from Facebook)
- Client code can be generated automatically
- Integrates with DynamoDB and Lambda
- Supports real-time subscriptions
- Enables offline data synchronization (replaces Cognito Sync)
- Provides fine-grained security
- AWS Amplify can leverage AppSync in the background

## 15.5 AWS Amplify

AWS Amplify is a set of tools and services that helps you develop and deploy scalable full stack web and mobile applications.

- Provides authentication, storage, API (REST, GraphQL), CI/CD, PubSub, analytics, AI/ML predictions, monitoring, and source code integration from AWS, GitHub, etc.
- Amplify Studio offers a visual interface for building and managing app data models
- Integrates with many AWS backend services: S3, Cognito, AppSync, API Gateway, SageMaker, Lex, Lambda, DynamoDB

Amplify simplifies the process of connecting frontend applications to AWS backend resources, enabling rapid development and deployment.

## 15.6 AWS Infrastructure Composer

AWS Infrastructure Composer is a visual tool for designing and building serverless applications quickly on AWS.

- Allows you to deploy AWS infrastructure code without needing to be an expert in AWS
- Configure how resources interact with each other
- Generates Infrastructure as Code (IaC) using CloudFormation
- Can import existing CloudFormation/SAM templates to visualize and modify them

This tool streamlines the process of creating, configuring, and managing AWS resources visually, making infrastructure management more accessible.

## 15.7 AWS Device Farm

AWS Device Farm is a fully-managed service that tests your web and mobile apps against desktop browsers, real mobile devices, and tablets.

- Run tests concurrently on multiple devices to speed up execution
- Ability to configure device settings (GPS, language, Wi-Fi, Bluetooth, etc.)
- Provides reports, logs, screenshots, and more from real devices (not emulators)

## 15.8 AWS Backup

AWS Backup is a fully-managed service to centrally manage and automate backups across AWS services.

- Supports on-demand and scheduled backups
- Supports PITR (Point-in-time Recovery)
- Retention periods, lifecycle management, backup policies
- Cross-region backup
- Cross-account backup (using AWS Organizations)

## 15.9 AWS Elastic Disaster Recovery (DRS)

AWS Elastic Disaster Recovery (formerly CloudEndure Disaster Recovery) enables quick and easy recovery of physical, virtual, and cloud-based servers into AWS.

- Protects critical databases (Oracle, MySQL, SQL Server), enterprise apps (SAP), and data from ransomware attacks
- Continuous block-level replication for servers
- Provides failover and fallback between corporate data centers and AWS Cloud

## 15.10 AWS DataSync

AWS DataSync moves large amounts of data from on-premises to AWS.

- Can synchronize to Amazon S3 (any storage class), Amazon EFS, Amazon FSx for Windows
- Replication tasks can be scheduled hourly, daily, weekly
- Replication tasks are incremental after the first full load

## 15.11 AWS Application Migration Service (MGN)

AWS Application Migration Service (MGN) helps migrate applications from on-premises or other clouds to AWS.
- Replicates entire application stack (OS, applications, data) to AWS
- Provides continuous replication with minimal downtime
- Supports lift-and-shift migrations without needing to modify applications
- After migration, applications can be modernized using AWS services if desired

## 15.12 AWS Migration Evaluator

AWS Migration Evaluator (formerly TSO Logic) helps assess the cost and performance of migrating on-premises workloads to AWS.
- Collects data on on-premises workloads to analyze resource usage and performance
- Provides recommendations for right-sizing AWS resources and estimating migration costs
- Helps identify potential cost savings and performance improvements in AWS

## 15.13 AWS Migration Hub

AWS Migration Hub provides a single location to track the progress of application migrations across multiple AWS and partner migration tools.
- Provides visibility into the migration status of applications and resources
- Integrates with AWS Application Migration Service, AWS Database Migration Service, and partner tools like CloudEndure, Corent, etc.
- Allows you to monitor and manage migrations from a central dashboard, regardless of the tools being used

## 15.14 AWS Fault Injection Simulator

AWS Fault Injection Simulator is a fully-managed service for running controlled chaos engineering experiments on AWS applications.
- Helps identify weaknesses and improve resilience of applications by simulating failures
- Provides a library of pre-built fault templates (CPU, memory, network, etc.) and allows custom faults
- Integrates with CloudWatch, X-Ray, and other monitoring tools to analyze the impact of faults on applications
- Enables testing of application behavior under failure conditions to improve reliability and performance

## 15.15 AWS Ground Station
AWS Ground Station is a fully-managed service that enables you to control satellite communications, process satellite data, and scale operations without having to worry about building or managing ground station infrastructure.
- Provides access to a global network of ground stations for satellite communication
- Allows you to schedule satellite contacts and receive data directly into AWS services like S3, Lambda, etc.
- Supports a wide range of satellite frequencies and data formats

## 15.16 AWS Pinpoint
AWS Pinpoint is a flexible and scalable outbound and inbound marketing communications service.
- Allows you to engage with customers across multiple channels (email, SMS, push notifications, voice)
- Provides analytics and targeting capabilities to optimize campaigns
- Integrates with other AWS services for data storage, processing, and analysis
- Supports personalized messaging and segmentation to improve customer engagement