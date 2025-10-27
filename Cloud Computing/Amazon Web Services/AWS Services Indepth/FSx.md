## **Definiton**

- Amazon **FSx** is a **fully managed file storage service** designed for applications that require **high-performance, scalable, and feature-rich file systems**. FSx provides **two main file system options**:
- **Amazon FSx for Windows File Server** – Native Windows file system for Windows-based applications.
- **Amazon FSx for Lustre** – High-performance, low-latency storage for HPC (High-Performance Computing) and big data workloads.
## **FSx for Windows File Server** (FSx for Windows)

- Fully managed **Windows-native SMB file system**.
- **Active Directory (AD) integration** for authentication and access control.
- **Multi-AZ Deployment** – High availability with automatic failover.
- **SSD and HDD options** – Choose based on performance needs.
- Supports **Shadow Copies** for point-in-time file recovery.
- **Scales up to petabytes** with automatic backups.
- **Use Case:** Windows applications, shared home directories, enterprise applications (SAP, SQL Server).

## **FSx for Lustre**

- **High-performance, low-latency file storage** optimized for computing workloads.
- **Seamless integration with Amazon S3** – Move data between FSx and S3 for **big data processing**.
- **Up to hundreds of GBps throughput and millions of IOPS**.
- **Parallel distributed file system** – Best for large-scale ML, analytics, and HPC workloads.
- **Use Case:** Machine learning, big data analytics, financial modeling, video rendering.

## **Security & Compliance**

- **IAM & Active Directory Authentication** restricts user access.
- **AWS KMS Encryption** secures data at rest and in transit.
- **Automatic Backups & Snapshots** support disaster recovery.
