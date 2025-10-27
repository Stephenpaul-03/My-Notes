## **Definition**

- AWS Global Accelerator is a network acceleration service that improves the availability and performance of applications by using AWS’s global network instead of the public internet. 
- It provides intelligent traffic routing to optimize latency and reliability for global users.

## **Global Anycast IPs**

- Provides **static Anycast IP addresses** that act as a **fixed entry point** for applications.
- Users connect to the nearest AWS **edge location**, reducing **latency and jitter**.

## **Traffic Routing & Health Monitoring**

- **Automatic Failover** – Redirects traffic to healthy endpoints if an issue is detected.
- **Regional Failover** – If an entire AWS region fails, traffic shifts to another region.
- **Intelligent Routing** – Uses AWS’s private backbone network for the best performance.

## **Endpoint Groups & Listeners**

- **Endpoint Groups** – Collection of AWS **resources (ALB, NLB, EC2, or Elastic IPs)**.
- **Listeners** – Accepts traffic on the **Global Accelerator's static IPs** and forwards it to endpoint groups.

## **Performance & Security Enhancements**

- **Bypasses public internet** to reduce congestion and packet loss.
- **DDoS protection** is built-in via **AWS Shield**.
