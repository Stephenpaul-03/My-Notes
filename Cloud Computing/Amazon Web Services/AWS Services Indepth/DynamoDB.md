## **Definition**

- Amazon **DynamoDB** is a **fully managed, serverless NoSQL database** designed for **high-performance, scalable applications**.  
- It provides **millisecond latency**, **automatic scaling**, and **built-in security** while eliminating the need for database maintenance.

## **NoSQL Database Model**

- DynamoDB is a **key-value and document-based database**.  
- Data is stored in **tables**, with **items (rows)** containing flexible **attributes (columns)**.  
- Unlike relational databases, it does not require **fixed schemas or relationships** between tables.

## **Performance & Scalability**

- **Automatic Scaling** – DynamoDB adjusts read/write capacity based on demand.  
- **On-Demand Mode** – Pay only for what you use, no need to provision capacity.  
- **DynamoDB Accelerator (DAX)** – **In-memory caching** for microsecond-level response times.

## **Data Consistency Models**

- **Eventually Consistent Reads (default)** – Faster but may return stale data for a short time.  
- **Strongly Consistent Reads** – Guarantees the latest data but has slightly higher latency.

## **High Availability & Disaster Recovery**

- **Multi-AZ Replication** – Data is automatically replicated across multiple AWS Availability Zones.  
- **Global Tables** – Enables multi-region, active-active replication for globally distributed applications.  
- **Point-in-Time Recovery (PITR)** – Restore to a previous state within the last 35 days.

## **Security & Access Control**

- **Encryption** – Uses **AWS KMS** for data encryption at rest.  
- **IAM Authentication & Policies** – Fine-grained access control using AWS Identity and Access Management.  
- **VPC Endpoints** – Secure access without using the public internet.
