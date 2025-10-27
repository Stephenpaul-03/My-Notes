## Definition

- Amazon Route 53 is a highly available and scalable Domain Name System (DNS) web service that helps route user traffic to applications hosted in AWS or other locations. 
- It also supports domain registration and health checking for fault-tolerant architectures.

## **DNS Management**

- **Domain Name Resolution** – Converts human-readable domain names (e.g., `example.com`) into IP addresses.
- **Private & Public DNS** –
    - **Public Hosted Zones** – Routes traffic over the internet.
    - **Private Hosted Zones** – Routes traffic inside an **Amazon VPC** (internal networks).

## **Domain Registration & Management**

- Route 53 can **register and manage domain names** (e.g., `.com`, `.net`, `.org`).
- Supports **DNSSEC (Domain Name System Security Extensions)** for added security.

## **Health Checks & Monitoring**

- **Route 53 Health Checks** – Monitor the health of web servers, applications, or endpoints.
- Can trigger **failover routing** to redirect traffic if a resource becomes unavailable.

## **Traffic Flow & Global Scalability**

- **Integrates with AWS Global Accelerator** for optimized global performance.
- Works with **CloudFront (CDN)** and **Elastic Load Balancing (ELB)** for efficient traffic distribution.

## **Routing Policies**

Route 53 supports multiple **routing policies** for directing traffic based on business needs:

1. **Simple Routing** – Maps a domain to a single IP (basic configuration).
2. **Weighted Routing** – Distributes traffic across multiple endpoints based on weight percentages.
3. **Latency-Based Routing** – Routes users to the AWS region with the **lowest latency**.
4. **Geolocation Routing** – Routes users based on their physical location (country, state, or continent).
5. **Geoproximity Routing** – Routes traffic based on a user's location with bias settings to shift traffic.
6. **Failover Routing** – Uses health checks to switch traffic to a backup resource in case of failure.
7. **Multi-Value Answer Routing** – Provides multiple IP addresses and balances traffic among them.
