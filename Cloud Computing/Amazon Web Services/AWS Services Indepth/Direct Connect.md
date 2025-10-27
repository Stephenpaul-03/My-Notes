## **Definition**

- **AWS Direct Connect** is a **dedicated, private network connection** between an on-premises data center (or office) and AWS.  
- It provides **higher bandwidth**, **lower latency**, and **more consistent performance** than standard internet-based connections.

## **Private & High-Performance Connectivity**

- Bypasses the public internet for a **secure, high-speed link** to AWS services.  
- Supports speeds from **50 Mbps to 100 Gbps** for demanding workloads.  
- Reduces network congestion and minimizes **latency fluctuations**.

## **Virtual Interfaces (VIFs)**

- **Private VIF** – Connects to a **VPC** via a Virtual Private Gateway.  
- **Public VIF** – Provides access to **AWS public services** (e.g., S3, DynamoDB) without using the internet.  
- **Transit VIF** – Connects to **AWS Transit Gateway** for multiple VPCs and hybrid cloud setups.

## **Redundancy & High Availability**

- Can be **paired with VPN** for failover scenarios.  
- Supports **multiple Direct Connect locations** for redundancy.  
- Works with **AWS Direct Connect Gateway** to access multiple regions.

## **Security & Compliance**

- **Traffic never passes through the public internet**, reducing exposure to cyber threats.  
- Works with AWS **IAM, VPC Security Groups, and Network ACLs** for access control.
