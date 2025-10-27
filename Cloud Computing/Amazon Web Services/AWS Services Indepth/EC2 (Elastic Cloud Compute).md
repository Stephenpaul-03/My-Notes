## **Definition**

- Amazon **EC2** is a **scalable cloud-based virtual server** that provides resizable compute capacity.  
- It allows users to **launch, configure, and manage virtual machines (instances)** on AWS.

## **EC2 Instance Types**

- **General Purpose** – Balanced compute, memory, and networking (e.g., **t3, m5**).  
- **Compute Optimized** – High-performance processors (e.g., **c5** for gaming, HPC).  
- **Memory Optimized** – High RAM for databases & analytics (e.g., **r5, x1**).  
- **Storage Optimized** – High-speed SSD/NVMe for big data (e.g., **i3, d2**).  
- **Accelerated Computing** – Uses GPUs or FPGAs (e.g., **p4, g5** for AI/ML).

## **Security & Networking**

- **Security Groups** – Act as a **firewall** controlling inbound/outbound traffic.  
- **Key Pairs** – Used for secure SSH/RDP access.  
- **Elastic IPs** – Static IPv4 addresses for persistent access.  
- **Placement Groups** – Controls instance placement for **low latency or high availability**.

## **Pricing Models**

- **On-Demand** – Pay per second/minute with no long-term commitment.  
- **Reserved Instances (RIs)** – 1- or 3-year commitment for lower cost.  
- **Spot Instances** – Up to **90% cheaper** but can be terminated anytime.  
- **Savings Plans** – Flexible pricing based on usage commitment.  
- **Dedicated Hosts** – Physical server for compliance requirements.

## **Auto Scaling & Load Balancing**

- **Auto Scaling Groups (ASG)** – Automatically **adds/removes** instances based on demand.  
- **Elastic Load Balancer (ELB)** – Distributes traffic across multiple instances.

## **EC2 Storage Options**

- **Amazon EBS (Elastic Block Store)** – Persistent block storage for EC2.  
- **Instance Store (Ephemeral Storage)** – Temporary, high-speed storage tied to the instance lifecycle.  
- **EFS (Elastic File System)** – Shared storage across multiple instances.

## **EC2 Purchasing Options for Scalability**

- **Launch Templates** – Predefined configurations for faster instance launching.  
- **Amazon Machine Images (AMI)** – Custom OS & software configurations for fast deployment.
