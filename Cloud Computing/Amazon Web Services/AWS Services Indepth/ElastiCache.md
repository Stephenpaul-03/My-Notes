## **Definition**

- Amazon **ElastiCache** is a **fully managed in-memory caching service** designed to improve application performance by **reducing database load and latency**.  
- It supports two popular caching engines:  
  - **ElastiCache for Redis** – High-performance, in-memory key-value store with advanced data structures.  
  - **ElastiCache for Memcached** – Simple, distributed caching system for quick data retrieval.

## **High Performance & Low Latency**

- **In-memory caching** enables sub-millisecond response times.  
- Reduces database read load by serving frequently accessed data from cache.  
- Supports **millions of requests per second** for real-time applications.

## **Use Case-Based Engine Selection**

- **Redis** – Advanced caching, pub/sub messaging, leaderboards, and real-time analytics.  
- **Memcached** – Simple caching for read-heavy workloads, session storage, and database acceleration.

## **Scalability & High Availability**

- **Auto-scaling & Cluster Mode** – Automatically scales cache capacity based on workload.  
- **Multi-AZ with Automatic Failover** – Provides **high availability and disaster recovery**.  
- **Sharding (Redis Cluster Mode Enabled)** – Distributes data across multiple nodes for better scalability.

## **Security & Compliance**

- **Encryption with AWS KMS** – Encrypts data at rest and in transit.  
- **IAM & VPC Integration** – Secure access control and private network access.  
- **Access Control Lists (ACLs) for Redis** – Fine-grained user permissions.
