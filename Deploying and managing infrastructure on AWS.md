# 8. Deploying and managing infrastructure on AWS

## 8.1 AWS CloudFormation

	CloudFormation is a declarative way of outlining your AWS Infrastructure, for any resources (most of them are supported).

	For example, within a CloudFormation template, you say:
		- I want a security group
		- I want two EC2 instances using this security group
		- I want an S3 bucket
		- I want a load balancer (ELB) in front of these machines

	Then CloudFormation creates those for you, in the **right order**, with the **exact configuration** that you specify.


## 8.2 AWS Cloud Development Kit (CDK)

	- Define your cloud infrastructure using a familiar language:
			- JavaScript/TypeScript, Python, Java, and .NET
	- The code is "compiled" into a CloudFormation template (JSON/YAML)
	- You can therefore deploy infrastructure and application runtime code together
			- Great for Lambda functions
			- Great for Docker containers in ECS / EKS

	**CDK Workflow:**
	1. Write code in your preferred language (e.g., Python, TypeScript)
	2. Use the CDK CLI to synthesize a CloudFormation template
	3. Deploy the template with CloudFormation


## 8.3 AWS Elastic Beanstalk

	- Elastic Beanstalk is a developer-centric view of deploying an application on AWS
	- It uses all the components we've seen before: EC2, ASG, ELB, RDS, etc.
	- But it's all in one view that's easy to make sense of!
	- We still have full control over the configuration
	- Beanstalk = Platform as a Service (PaaS)

## 8.4 Elastic Beanstalk Details
	- Managed service
		- Instance configuration / OS is handled by Beanstalk
		- Deployment strategy is configurable but performed by Elastic Beanstalk
		- Capacity provisioning
		- Load balancing & auto-scaling
		- Application health-monitoring & responsiveness

	- Just the application code is the responsibility of the developer

	- Three architecture models:
		- Single Instance deployment: good for dev
		- LB + ASG: great for production or pre-production web applications
		- ASG only: great for non-web apps in production (workers, etc.)

	- Supports multiple platforms: Java, .NET, Node.js, Python, Ruby, Go, Docker, etc.

## 8.5 AWS CodeCommit

- Before pushing the application code to servers, it needs to be stored somewhere
- Developers usually store code in a repository, using the Git technology
- A famous public offering is GitHub, AWS’ competing product is CodeCommit
- **CodeCommit:**
	- Source-control service that hosts Git-based repositories
	- Makes it easy to collaborate with others on code
	- The code changes are automatically versioned
- **Benefits:**
	- Fully managed
	- Scalable & highly available
	- Private, Secured, Integrated with AWS

---

## 8.6 AWS CodeBuild

- Code building service in the cloud
- Compiles source code, runs tests, and produces packages that are ready to be deployed (by CodeDeploy for example)
- **Benefits:**
	- Fully managed, serverless
	- Continuously scalable & highly available
	- Secure
	- Pay-as-you-go pricing – only pay for the build time

---

## 8.7 AWS CodeDeploy

- Used to deploy applications automatically
- Works with EC2 Instances
- Works with On-Premises Servers
- Hybrid service
- Servers / Instances must be provisioned and configured ahead of time with the CodeDeploy Agent

---

## 8.8 AWS CodeArtifact

- Software packages depend on each other to be built (code dependencies), and new ones are created
- Storing and retrieving these dependencies is called artifact management
- Traditionally you need to setup your own artifact management system
- **CodeArtifact** is a secure, scalable, and cost-effective artifact management for software development
- Works with common dependency management tools such as Maven, Gradle, npm, yarn, twine, pip, and NuGet
- Developers and CodeBuild can then retrieve dependencies straight from CodeArtifact

---

## 8.9 AWS Systems Manager (SSM)

- Helps you manage your EC2 and On-Premises systems at scale
- Another Hybrid AWS service
- Get operational insights about the state of your infrastructure
- Suite of 10+ products
- Most important features are:
    - Patching automation for enhanced compliance
    - Run commands across an entire fleet of servers
    - Store parameter configuration with the SSM Parameter Store
- Works for Linux, Windows, MacOS, and Raspberry Pi OS (Raspbian)

### 8.10 SSM Session Manager

- Allows you to start a secure shell on your EC2 and on-premises servers
- No SSH access, bastion hosts, or SSH keys needed
- No port 22 needed (better security)
- Supports Linux, macOS, and Windows
- Send session log data to S3 or CloudWatch Logs
