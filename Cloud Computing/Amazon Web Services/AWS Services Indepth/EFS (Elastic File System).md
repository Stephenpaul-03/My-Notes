## **Definition**

- Amazon **EFS** is a **fully managed, scalable, shared file storage** service that allows multiple EC2 instances to access the same file system **simultaneously**.  
- It is ideal for applications that require **shared storage**, such as **web applications, machine learning, and big data analytics**.

## **Performance Modes**

- **General Purpose Mode (Default)** – Low-latency, best for web servers and microservices.  
- **Max I/O Mode** – Higher throughput for **big data and analytics** workloads.

## **Fully Managed & Scalable**

- **Automatic Scaling** – Grows and shrinks **on demand** (no need to pre-provision storage).  
- **Highly Available** – Data is replicated across **multiple AZs** for durability.  
- **Multiple EC2 Instances** – Can be mounted by **hundreds or thousands** of instances at once.

## **Storage Classes & Cost Optimization**

EFS supports **automatic tiering** to reduce storage costs:  

- **EFS Standard** – High-performance storage for frequently accessed data.  
- **EFS Infrequent Access (EFS-IA)** – Lower-cost storage for less frequently accessed data.  
- **Lifecycle Management** – Moves data **automatically** between **Standard** and **IA** based on access patterns.

## **Security & Access Control**

- **IAM Permissions** – Restrict access at the user or application level.  
- **Encryption** – Data is encrypted **at rest** (AWS KMS) and **in transit** (TLS).  
- **Security Groups & NFS Access** – Uses **NFSv4** protocol and security groups for access control.

## **Backup & Disaster Recovery**

- **AWS Backup Integration** – Automates EFS backups with lifecycle policies.  
- **Cross-Region Replication** – Allows **disaster recovery** by replicating data to another AWS region.
