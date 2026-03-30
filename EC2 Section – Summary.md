## 2. EC2 Section – Summary

EC2 (Elastic Compute Cloud) is a core AWS service that provides resizable compute capacity in the cloud. It allows you to run virtual servers, known as EC2 instances, which can be configured with various operating systems, instance types, and storage options to meet your specific needs.

- **EC2 Instance:** AMI (OS) + Instance Size (CPU + RAM) + Storage + Security Groups + EC2 User Data
- **Security Groups:** Firewall attached to the EC2 instance
- **EC2 User Data:** Script launched at the first start of an instance
- **SSH:** Start a terminal into our EC2 Instances (port 22)
- **EC2 Instance Role:** Link to IAM roles
- **Purchasing Options:** On-Demand, Spot, Reserved (Standard + Convertible), Dedicated Host, Dedicated Instance

### 2.1 EC2 Instance Storage – Summary

- **EBS volumes:**
	- Network drives attached to one EC2 instance at a time
	- Mapped to an Availability Zone
	- Can use EBS Snapshots for backups / transferring EBS volumes across AZ
- **AMI:** Create ready-to-use EC2 instances with our customizations
- **EC2 Image Builder:** Automatically build, test and distribute AMIs
- **EC2 Instance Store:**
	- High performance hardware disk attached to our EC2 instance
	- Lost if our instance is stopped / terminated
- **EFS:** Network file system, can be attached to 100s of instances in a region
- **EFS-IA:** Cost-optimized storage class for infrequently accessed files
- **FSx for Windows:** Network File System for Windows servers
- **FSx for Lustre:** High Performance Computing Linux file system

# 2.2 Info: High Availability & Scalability for EC2

**High Availability** and **Scalability** are key concepts for EC2:

- **Vertical Scaling:** Increase instance size (scale up/down)
	- Example: From t2.nano (0.5GB RAM, 1 vCPU) to u-12tb1.metal (12.3TB RAM, 448 vCPUs)
- **Horizontal Scaling:** Increase number of instances (scale out/in)
	- Auto Scaling Group
	- Load Balancer
- **High Availability:** Run instances for the same application across multiple Availability Zones (AZ)
	- Auto Scaling Group multi AZ
	- Load Balancer multi AZ
