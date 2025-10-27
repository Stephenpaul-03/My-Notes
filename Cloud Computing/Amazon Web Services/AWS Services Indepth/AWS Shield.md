## **Definition**

- AWS **Shield** is a **managed Distributed Denial of Service (DDoS) protection service** that helps safeguard AWS applications from volumetric, state-exhaustion, and application-layer attacks.
- It provides **automatic threat detection and mitigation** to ensure high availability and security.

## **Two Protection Plans**

AWS Shield comes in **two tiers**:

1. **AWS Shield Standard (Free)**
    - Automatically included for all AWS customers.
    - Provides **basic protection** against common **network and transport layer DDoS attacks** (e.g., SYN floods, UDP reflection attacks).
    - Works **seamlessly with AWS services** like **CloudFront, Route 53, and Elastic Load Balancer (ELB)**.
2. **AWS Shield Advanced (Paid)**
    - **Enhanced DDoS protection** with **real-time detection and automated response**.
    - Covers **application-layer attacks (e.g., HTTP floods, slow POST attacks)**.
    - **24/7 AWS DDoS Response Team (DRT) support**.
    - **Detailed attack analytics and cost protection** to avoid unexpected spikes in AWS bills due to attacks.
    - Works with **AWS WAF, AWS Firewall Manager, and AWS Global Accelerator** for advanced security.

## **DDoS Mitigation Techniques**

- **Automatic Traffic Analysis** – Identifies attack patterns and mitigates threats in real time.
- **Scales Defensively** – AWS infrastructure can **absorb large-scale attacks** without performance impact.
- **Custom Protection Policies** – Users can configure **custom rules and rate limits** for applications.

## **Integration with Other AWS Services**

- Works with **AWS WAF** to block malicious web requests.
- Supports **Route 53 and CloudFront** to absorb DDoS attacks at the edge.
- Provides centralized security management with **AWS Firewall Manager**.
