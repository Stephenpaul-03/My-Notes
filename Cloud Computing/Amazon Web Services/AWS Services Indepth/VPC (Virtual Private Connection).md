## Definition
- Amazon **VPC (Virtual Private Cloud)** is a **logically isolated network** within AWS that allows you to **control networking, security, and connectivity** for your AWS resources. 
- It functions like a traditional **data center network**, but with AWS’s **scalability and security**.
## **Network Components**

- **Subnets** – Logical divisions of a VPC that **separate resources** into private and public zones.
- **Route Tables** – Define how traffic is routed within the VPC and to external networks.
- **Internet Gateway (IGW)** – Allows public access to the internet for instances in a public subnet.
- **NAT Gateway / NAT Instance** – Enables private subnet instances to access the internet without being exposed.
- **VPC Peering** – Directly connects two VPCs for secure communication.
- **AWS Transit Gateway** – Connects multiple VPCs and on-premises networks at scale.
- **Elastic IP (EIP)** – Static public IP address that can be attached to AWS resources.
- **Endpoints (Gateway & Interface)** – Private connectivity to AWS services without using the internet.

## **Security & Access Control**

- **Security Groups (SGs)** – **Instance-level firewall** rules controlling inbound/outbound traffic.
- **Network ACLs (NACLs)** – **Subnet-level firewall** rules controlling inbound/outbound traffic.
- **VPC Flow Logs** – Capture network traffic for monitoring and security analysis.
- **PrivateLink** – Secure access to AWS services **without exposing traffic to the public internet**.

## **Connectivity Options**

- **Direct Connect (DX)** – Private, high-speed connection between on-premises data centers and AWS.
- **VPN (Virtual Private Network)** – Secure encrypted connection between AWS and on-premises networks.
- **Hybrid Cloud Integration** – Combine on-premises infrastructure with AWS using DX or VPN.
