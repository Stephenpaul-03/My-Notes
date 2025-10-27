## **Definition**

- AWS Trusted Advisor is a service that provides real-time guidance on best practices for cost optimization, security, performance, fault tolerance, and service limits.
- It helps AWS users identify misconfigurations, optimize resources, and improve security & resilience.

## **Five Pillars of Trusted Advisor**

1. **Cost Optimization** – Identifies **unused or underutilized resources** (e.g., idle EC2 instances, unassociated EIPs).
2. **Security** – Flags **security vulnerabilities** (e.g., open S3 buckets, weak IAM policies, lack of MFA).
3. **Performance** – Detects **bottlenecks** (e.g., overutilized EC2 instances, missing CloudFront caching).
4. **Fault Tolerance** – Recommends **high availability improvements** (e.g., enabling Multi-AZ for RDS).
5. **Service Limits** – Warns when **resource usage nears AWS account limits** (e.g., EC2 instance count).

## **Types of AWS Trusted Advisor Checks**

- **Core Checks (Free)** – Basic security and service limit checks.
- **Full Checks (Business & Enterprise Support Plans)** – Advanced recommendations for all five categories.

## **Integration & Automation**

- **AWS Organizations Support** – View recommendations for multiple AWS accounts.
- **Programmatic Access** – Use **AWS SDKs & APIs** to automate monitoring and remediation.
- **Alerts & Notifications** – Integrates with AWS **SNS** for real-time notifications.
