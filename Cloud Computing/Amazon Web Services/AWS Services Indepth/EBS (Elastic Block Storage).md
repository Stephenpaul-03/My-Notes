## **Definition**

- Amazon **EBS** is a **block storage service** designed for use with **EC2 instances**.  
- It provides **high-performance, durable, and scalable** storage that supports applications requiring persistent storage, such as **databases, big data workloads, and file systems**.

## **EBS Volume Types**

EBS offers different volume types optimized for **performance and cost**:  

**SSD-Based (For high-performance applications)**  
- **gp3 (General Purpose SSD)** – **Baseline: 3,000 IOPS**, scalable to **16,000 IOPS**. Cost-efficient for most workloads.  
- **gp2 (General Purpose SSD)** – **Baseline: 3 IOPS/GB**, burstable to **16,000 IOPS**. Legacy option.  
- **io2 (Provisioned IOPS SSD)** – **Up to 256,000 IOPS** for mission-critical applications (databases, SAP).  
- **io1 (Provisioned IOPS SSD)** – Older version of io2 with similar performance.

**HDD-Based (For high-throughput workloads)**  
- **st1 (Throughput Optimized HDD)** – Best for **big data, log processing, and streaming workloads**.  
- **sc1 (Cold HDD)** – **Lowest-cost storage**, used for infrequently accessed data.

## **Snapshots & Backup**

- **EBS Snapshots** – **Point-in-time backup** of EBS volumes stored in S3.  
- **Incremental Backups** – Only changed data is stored, reducing costs.  
- **Cross-Region Snapshots** – Replicate snapshots to another AWS region for **disaster recovery**.

## **Resizing & Performance Optimization**

- **Elastic Volumes** – Change size, type, or IOPS without downtime.  
- **Multi-Attach (for io1/io2 volumes)** – Attach a single EBS volume to **multiple EC2 instances**.

## **Security & Encryption**

- **Encryption at Rest** – Uses **AWS KMS** (Key Management Service) for encryption.  
- **In-Transit Encryption** – Ensures data is encrypted when moving between EC2 and EBS.  
- **IAM Permissions** – Fine-grained access control to prevent unauthorized access.

## **EBS vs. Other AWS Storage Services**

- **EBS (Elastic Block Store)** → Block storage for EC2 instances (like an external hard drive).  
- **S3 (Simple Storage Service)** → Object storage for any type of data (scalable but not directly attachable).  
- **EFS (Elastic File System)** → Shared file storage for multiple EC2 instances.
