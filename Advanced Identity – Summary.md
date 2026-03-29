# 14. Advanced Identity – Summary

Advanced identity topics in AWS focus on managing temporary credentials, federated access, and cross-account permissions. These are essential for secure, scalable, and flexible access control in complex cloud environments.

## 14.1 AWS STS (Security Token Service)

AWS STS enables you to create temporary, limited-privileges credentials to access your AWS resources. You can configure the expiration period for these short-term credentials.

**Use cases:**
- Identity federation: Manage user identities in external systems and provide them with STS tokens to access AWS resources
- IAM Roles for cross/same account access
- IAM Roles for Amazon EC2: Provide temporary credentials for EC2 instances to access AWS resources

## 14.2 AWS Cognito
AWS Cognito is a service that provides user sign-up, sign-in, and access control for web and mobile applications. It allows you to authenticate users through social identity providers (like Facebook, Google, and Amazon) or your own identity provider.
**Use cases:**
- User authentication and access control for web and mobile applications
- Integration with social identity providers
- User management and synchronization across devices

## 14.3 AWS Directory Service
AWS Directory Service allows you to set up and run Microsoft Active Directory (AD) in the AWS Cloud or connect your AWS resources with an existing on-premises AD. It provides multiple directory types, including AWS Managed Microsoft AD, Simple AD, and AD Connector.

**Use cases:**
- **AWS Managed Microsoft AD:**
	- Create your own AD in AWS, manage users locally, supports MFA
	- Establish "trust" connections with your on-premises AD
- **AD Connector:**
	- Directory gateway (proxy) to redirect to on-premises AD, supports MFA
	- Users are managed on the on-premises AD
- **Simple AD:**
	- AD-compatible managed directory on AWS
	- Cannot be joined with on-premises AD

## 14.4 AWS Single Sign-On (SSO)
AWS Single Sign-On (SSO) is a cloud-based service that simplifies managing SSO access to multiple AWS accounts and business applications. It allows you to centrally manage SSO access and user permissions across all your AWS accounts and applications.

**Use cases:**
- Centralized SSO access management for multiple AWS accounts and applications
- Integration with existing identity providers (like Microsoft Active Directory)
- Simplified user access management and permissions control across AWS resources and applications

