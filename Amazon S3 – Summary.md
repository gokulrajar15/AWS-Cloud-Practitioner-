# 5. Amazon S3 – Summary

Amazon S3 (Simple Storage Service) is a highly scalable and durable object storage service that allows you to store and retrieve any amount of data from anywhere on the web. It provides a simple web interface to store and retrieve data, making it ideal for a wide range of use cases, including backup and restore, archiving, big data analytics, and content distribution.

- **Buckets vs Objects:** Global unique name, tied to a region
- **S3 security:** IAM policy, S3 Bucket Policy (public access), S3 Encryption
- **S3 Websites:** Host a static website on Amazon S3
- **S3 Versioning:** Multiple versions for files, prevent accidental deletes
- **S3 Replication:** Same-region or cross-region, must enable versioning
- **S3 Storage Classes:** Standard, IA, 1Z-IA, Intelligent, Glacier (Instant, Flexible, Deep)
- **Snowball:** Import data onto S3 through a physical device, edge computing
- **Storage Gateway:** Hybrid solution to extend on-premises storage to S3

## types of S3 Storage Classes

- **S3 Standard:** General-purpose storage for frequently accessed data
- **S3 Standard-IA (Infrequent Access):** For data that is accessed less frequently but requires rapid access when needed
- **S3 One Zone-IA:** For infrequently accessed data that does not require multiple Availability Zone resilience
- **S3 Intelligent-Tiering:** Automatically moves data to the most cost-effective access tier based on changing access patterns
- **S3 Glacier Instant Retrieval:** For data that is rarely accessed but requires immediate retrieval when needed
- **S3 Glacier Flexible Retrieval:** For data that is rarely accessed and can tolerate retrieval times of minutes to hours
- **S3 Glacier Deep Archive:** For data that is rarely accessed and can tolerate retrieval times of hours to days, the lowest-cost storage class for long-term data archiving.
