## Definition

- Amazon **S3** is an **object storage service** that provides **scalable, durable, and secure** storage for any type of data. 
- It is commonly used for **backup, static website hosting, data lakes, and content distribution**.
## **S3 Storage Classes**

S3 offers multiple storage classes based on **cost, durability, and retrieval speed**:

- **S3 Standard** – General-purpose, low-latency storage for frequently accessed data.
- **S3 Intelligent-Tiering** – Automatically moves data between high- and low-cost storage tiers.
- **S3 Standard-IA (Infrequent Access)** – Lower cost for data accessed less frequently.
- **S3 One Zone-IA** – Cheaper than Standard-IA, but stores data in only one AWS region.
- **S3 Glacier** – Low-cost, cold storage for archiving (retrieval in minutes to hours).
- **S3 Glacier Deep Archive** – Cheapest storage for long-term archival (retrieval in 12+ hours).

![S3.png](../images/S3.png)
## **Buckets & Objects**

- **Buckets** – Logical containers for storing objects (files).
- **Objects** – Individual data items stored inside an S3 bucket.
- **Keys** – The unique identifier for an object inside a bucket.
## **Data Durability & Availability**

- **99.999999999% (11 nines) durability** – Protects against data loss.
- **High availability** – Designed for **99.99% uptime** in Standard storage class.
## **Performance & Cost Optimization**

- **Multipart Uploads** – Splits large files for faster uploads.
- **S3 Transfer Acceleration** – Uses AWS Edge locations to speed up uploads.
- **Requester Pays** – Shifts data transfer costs to the downloader.
## **Security & Access Control**

- **IAM Policies** – Controls who can access S3 resources.
- **Bucket Policies** – Define access rules at the bucket level.
- **ACLs (Access Control Lists)** – Grant permissions at the object level.
- **Encryption**:
    - **Server-Side Encryption (SSE)** – Encrypts data at rest using **SSE-S3, SSE-KMS, or SSE-C**.
    - **Client-Side Encryption** – Data is encrypted before being uploaded.
## **Data Lifecycle Management**

- **Lifecycle Policies** – Automatically move or delete objects based on age.
- **Versioning** – Keeps multiple versions of objects to prevent accidental deletion.
- **Replication**:
    - **Cross-Region Replication (CRR)** – Copies data across AWS regions.
    - **Same-Region Replication (SRR)** – Copies data within the same AWS region.
## **Static Website Hosting**

- S3 can host **static websites** with custom domains and CloudFront integration.
- Supports **index.html and error.html** pages.
