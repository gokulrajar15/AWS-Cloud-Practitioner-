# 12. Security and Governance

## 12.1 Shared Responsibility Model
In the Shared Responsibility Model, AWS is responsible for the security of the cloud infrastructure, while customers are responsible for securing their data and applications within the cloud. This means that AWS manages the physical security of data centers, network infrastructure, and hardware, while customers are responsible for configuring security settings, managing access controls, and protecting their data.

## 12.2 DDoS Protection on AWS
AWS provides multiple services to protect against Distributed Denial of Service (DDoS) attacks:

- **AWS Shield Standard**: Automatically protects all AWS customers from common DDoS attacks at no additional cost. It covers attacks such as SYN/UDP floods, reflection attacks, and other layer 3/layer 4 threats.
- **AWS Shield Advanced**: Offers enhanced DDoS protection with 24/7 access to the AWS DDoS Response Team (DRP), advanced mitigation, and protection for services like EC2, ELB, CloudFront, Global Accelerator, and Route 53. It also helps reduce costs during usage spikes caused by DDoS events (optional, paid service).
- **AWS WAF (Web Application Firewall)**: Protects web applications from common web exploits (layer 7 attacks) such as SQL injection and cross-site scripting (XSS). Allows custom rules, IP blocking, geo-matching, and rate-based rules for DDoS mitigation. Can be deployed on Application Load Balancer, API Gateway, and CloudFront.
- **CloudFront and Route 53**: Provide global edge network availability protection and, when combined with AWS Shield, offer attack mitigation at the edge.

AWS recommends leveraging Auto Scaling to ensure applications are ready to scale in response to increased traffic during attacks.

## 12.3 AWS Network Firewall
AWS Network Firewall is a managed service that protects your entire Amazon VPC, providing Layer 3 to Layer 7 protection. It enables inspection and filtering of traffic in any direction:

- VPC to VPC traffic
- Outbound to the internet
- Inbound from the internet
- To and from Direct Connect & Site-to-Site VPN

With AWS Network Firewall, you can define rules to inspect, block, or allow traffic, helping secure your network and monitor activity across your VPC environments.

## 12.4 AWS Firewall Manager
AWS Firewall Manager is a security management service that helps you centrally configure and manage firewall rules across all accounts in your AWS Organization.

- Manage security rules for VPC Security Groups, Application Load Balancer, WAF, AWS Shield Advanced, and AWS Network Firewall.
- Enforce a common set of security policies across multiple accounts.
- Automatically apply rules to new resources as they are created, ensuring compliance across all current and future accounts in your organization.

Firewall Manager simplifies security administration and helps maintain consistent protection and compliance at scale.

## 12.5 Penetration Testing on AWS Cloud
AWS customers are allowed to carry out security assessments or penetration tests against their AWS infrastructure without prior approval for certain services, including:

- Amazon EC2 instances, NAT Gateways, and Elastic Load Balancers
- Amazon RDS
- Amazon CloudFront
- Amazon Aurora
- Amazon API Gateways
- AWS Lambda and Lambda Edge functions
- Amazon Lightsail resources
- Amazon Elastic Beanstalk environments

Prohibited activities include:
- DNS zone walking via Amazon Route 53 Hosted Zones
- Denial of Service (DoS), Distributed Denial of Service (DDoS), Simulated DoS, Simulated DDoS
- Port flooding
- Protocol flooding
- Request flooding (login request flooding, API request flooding)

For other simulated events, contact aws-security-simulated-event@amazon.com. For more information, visit: https://aws.amazon.com/security/penetration-testing/

## 12.6 AWS KMS (Key Management Service)
AWS KMS is a managed service that handles encryption keys for AWS services. Whenever you hear "encryption" for an AWS service, it's most likely managed by KMS.

- Encryption opt-in: EBS volumes, S3 buckets (SSE-S3 enabled by default, SSE-KMS opt-in), Redshift database, RDS database, EFS drives
- Encryption automatically enabled: CloudTrail Logs, S3 Glacier, Storage Gateway

## 12.7 AWS Secrets Manager
AWS Secrets Manager is designed for securely storing secrets, such as database credentials and API keys. It supports:

- Forced rotation of secrets every X days
- Automated generation of secrets on rotation (using Lambda)
- Integration with Amazon RDS (MySQL, PostgreSQL, Aurora)
- Secrets are encrypted using KMS
- Mostly meant for RDS integration

## 12.8 AWS Certificate Manager (ACM)
AWS Certificate Manager lets you easily provision, manage, and deploy SSL/TLS certificates for your websites and applications. Key features:
- Free public SSL/TLS certificates for use with AWS services
- Automatic renewal of certificates before expiration
- Integration with services like Elastic Load Balancing, CloudFront, and API Gateway for seamless deployment
- Supports both public and private certificates, allowing you to secure internal resources as well as public-facing applications
- Simplifies the process of securing your applications with SSL/TLS, ensuring data privacy and integrity  

## 12.9 Amazon GuardDuty
Amazon GuardDuty is an intelligent threat detection service that protects your AWS account using machine learning, anomaly detection, and third-party data. It is easy to enable (30-day trial available) and requires no software installation.

GuardDuty analyzes input data such as:
- CloudTrail Events Logs (unusual API calls, unauthorized deployments)
- CloudTrail Management Events (create VPC subnet, create trail, etc.)
- CloudTrail S3 Data Events (get object, list objects, delete object, etc.)
- VPC Flow Logs (unusual internal traffic, unusual IP addresses)
- DNS Logs (compromised EC2 instances sending encoded data within DNS queries)
- Optional features: EKS Audit Logs, RDS & Aurora, EBS, Lambda, S3 Data Events

GuardDuty can set up EventBridge rules to notify in case of findings, and these rules can target AWS Lambda or SNS. It also protects against cryptocurrency attacks with dedicated findings.

## 12.10 Amazon Inspector
Amazon Inspector provides automated security assessments for AWS resources:

- For EC2 instances: Uses AWS System Manager (SSM) agent to analyze network accessibility and OS vulnerabilities
- For container images pushed to Amazon ECR: Assesses images as they are pushed
- For Lambda functions: Identifies software vulnerabilities in function code and dependencies, assesses functions as they are deployed

Inspector integrates with AWS Security Hub and sends findings to Amazon EventBridge for reporting and automation.
## 12.11 AWS Config
AWS Config helps with auditing and recording compliance of your AWS resources. It records configurations and changes over time, allowing you to store configuration data in S3 (which can be analyzed by Athena).

AWS Config can answer questions such as:
    - Is there unrestricted SSH access to my security groups?
    - Do my buckets have any public access?
    - How has my ALB configuration changed over time?

You can receive alerts (SNS notifications) for any changes. AWS Config is a per-region service and can be aggregated across regions and accounts for centralized compliance monitoring.

## 12.12 Amazon Macie
Amazon Macie is a fully managed data security and data privacy service that uses machine learning and pattern matching to discover and protect sensitive data in AWS.

- Helps identify and alert you to sensitive data, such as personally identifiable information (PII)
- Analyzes S3 buckets to discover sensitive data
- Notifies findings via Amazon EventBridge for integration and automation

Macie is useful for organizations needing to monitor and secure sensitive information stored in AWS, ensuring compliance and data privacy.

## 12.13 AWS Security Hub
AWS Security Hub is a central security tool to manage security across several AWS accounts and automate security checks. It provides integrated dashboards showing current security and compliance status, enabling quick actions.

Security Hub automatically aggregates alerts in predefined or personal findings formats from various AWS services and partner tools, including:
    - AWS Config
    - GuardDuty
    - Inspector
    - Macie
    - IAM Access Analyzer
    - AWS Systems Manager
    - AWS Firewall Manager
    - AWS Health
    - AWS Partner Network Solutions

To use Security Hub, you must first enable the AWS Config Service. Security Hub helps organizations maintain a unified view of their security posture and compliance across AWS environments.


## 12.14 Amazon Detective
Amazon Detective helps analyze, investigate, and quickly identify the root cause of security issues or suspicious activities in AWS environments using machine learning and graph analysis.

- Integrates with GuardDuty, Macie, and Security Hub to provide deeper analysis of security findings
- Automatically collects and processes events from VPC Flow Logs, CloudTrail, GuardDuty, and creates a unified view
- Produces visualizations with details and context to help isolate and resolve security issues

Detective is valuable for organizations needing to investigate complex security incidents and understand the context and root cause behind suspicious activities.

## 12.15 IAM Access Analyzer
IAM Access Analyzer helps identify resources in your AWS environment that are shared with an external entity. It analyzes resource-based policies to determine if any resources are accessible from outside your account.

- Supports services such as S3, KMS, SQS, SNS, IAM roles, Lambda functions, and more
- Provides findings that indicate which resources are shared and with whom, allowing you to review and adjust permissions to ensure that your resources are not unintentionally exposed to external entities. This tool is essential for maintaining the security of your AWS environment by identifying and mitigating potential access risks.