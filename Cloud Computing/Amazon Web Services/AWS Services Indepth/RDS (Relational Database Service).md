## Definition

- Amazon **RDS (Relational Database Service)** is a **fully managed database service** that simplifies the setup, operation, and scaling of relational databases. 
- It automates **database provisioning, patching, backups, and scaling**, reducing operational overhead.

## **Supported Database Engines**

Amazon RDS supports multiple database engines:

1. **Amazon Aurora** (AWS-native, MySQL/PostgreSQL compatible)
2. **MySQL**
3. **PostgreSQL**
4. **MariaDB**
5. **Oracle**
6. **SQL Server**

## **Automated Management**

- **Automated Backups & Snapshots** – Supports point-in-time recovery.
- **Automated Software Patching** – Keeps the database up to date with minimal downtime.
- **Database Monitoring** – Integrated with **Amazon CloudWatch** for real-time performance insights.

## **Security & Compliance**

- **Encryption** – Uses AWS KMS for encrypting data at rest and in transit.
- **IAM Authentication** – Allows users to connect using AWS IAM instead of traditional database credentials.
- **VPC Integration** – Enables private network access for enhanced security.

## **High Availability & Disaster Recovery**

- **Multi-AZ Deployment** – Provides automatic failover to a standby instance in a different Availability Zone (AZ).
- **Read Replicas** – Improves read performance by creating **replicated read-only instances**.
- **Cross-Region Replication** – Ensures disaster recovery by replicating the database across regions.

## **Performance & Scalability**

- **Vertical Scaling** – Increase instance size for more CPU/RAM.
- **Horizontal Scaling** – Use Read Replicas to distribute traffic.
- **Amazon Aurora** – Offers up to **5x faster performance** than MySQL and **3x faster** than PostgreSQL.
