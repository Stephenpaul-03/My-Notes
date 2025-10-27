## **Definition**

- Amazon Aurora is a fully managed, high-performance relational database designed for scalability, reliability, and cost-efficiency.
- It is MySQL- and PostgreSQL-compatible, offering up to 5x the performance of MySQL and 3x the performance of PostgreSQL while providing enterprise-grade availability and security.

## **Performance & Scalability**

- **Distributed, Fault-Tolerant Storage** – Data is **replicated across six copies in three Availability Zones (AZs)**.
- **Auto-Scaling Storage** – Automatically increases storage capacity **up to 128 TB** per database instance.
- **Parallel Query Processing** – Executes queries faster by distributing workloads.
- **Aurora Serverless** – Automatically scales compute and storage capacity **based on demand**.

## **High Availability & Disaster Recovery**

- **Multi-AZ Deployment** – Automatic failover between primary and standby instances.
- **Read Replicas** – Supports **up to 15 low-latency read replicas** for load balancing.
- **Global Database** – Allows replication across multiple AWS regions for disaster recovery and low-latency reads.

## **Security & Compliance**

- **Encryption** – Uses **AWS KMS** for encrypting data at rest and in transit.
- **IAM Authentication** – Secure access control using AWS Identity and Access Management (IAM).
- **VPC Isolation** – Allows secure database access within private networks.

## **Cost Optimization**

- **Pay-as-you-go pricing** – Charges based on storage and compute usage.
- **Aurora Serverless v2** – Auto-scales instantly to handle spikes in traffic, reducing costs for intermittent workloads.
