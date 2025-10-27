## **Definition**

- Amazon **Elastic Load Balancer (ELB)** is a **fully managed load balancing service** that automatically distributes incoming application traffic across multiple targets, such as EC2 instances, containers, IP addresses, and Lambda functions.  
- It ensures **high availability, fault tolerance, and scalability** for applications.

## **Types of Load Balancers in AWS**

1. **Application Load Balancer (ALB)** – **Layer 7 (HTTP/HTTPS) Load Balancer**  
   - Routes traffic based on **content** (host-based, path-based, or header-based routing).  
   - Supports **WebSockets**, HTTP/2, and redirect rules.  
   - Works well with **microservices and container-based architectures (ECS, EKS, Fargate)**.  
   - **Ideal for:** Web applications, APIs, and modern architectures.

2. **Network Load Balancer (NLB)** – **Layer 4 (TCP/UDP) Load Balancer**  
   - Handles **millions of requests per second** with low latency.  
   - Supports **static IP addresses** and **TLS termination**.  
   - **Ideal for:** High-performance applications, gaming servers, and financial services.

3. **Gateway Load Balancer (GWLB)** – **Traffic Load Balancer for Security Appliances**  
   - Used for routing traffic through **third-party security appliances** (firewalls, IDS/IPS).  
   - **Ideal for:** Centralized security inspections and traffic monitoring.

## **Key Load Balancing Features**

- **Automatic Scaling** – ELB can dynamically adjust to changing traffic demands.  
- **Cross-Zone Load Balancing** – Ensures even distribution across multiple Availability Zones.  
- **SSL/TLS Termination** – Offloads SSL decryption to ELB to reduce backend load.  
- **Sticky Sessions** – Ensures users connect to the same backend instance.  
- **Health Checks** – Monitors instance health and automatically reroutes traffic to healthy targets.  
- **Integration with Auto Scaling** – Works with Auto Scaling Groups to manage capacity automatically.
