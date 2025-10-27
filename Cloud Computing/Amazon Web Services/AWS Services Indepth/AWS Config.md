## **Definition**

- AWS **Config** is a **resource inventory, compliance auditing, and configuration monitoring service**.
- It helps organizations **track changes, enforce security policies, and ensure compliance** across AWS resources

## **Resource Configuration Tracking**

- Continuously **monitors and records** changes to AWS resource configurations.
- Supports **EC2, S3, IAM, VPC, RDS, Lambda, and more**.
- Provides a **detailed timeline** of resource modifications for auditing and troubleshooting.

## **Compliance & Governance**

- **Config Rules** – Defines security policies (e.g., “S3 buckets must be encrypted”).
- **Managed Rules** – Predefined AWS security & compliance rules (e.g., **PCI DSS, HIPAA, NIST**).
- **Custom Rules** – Users can create custom compliance checks using **AWS Lambda**.

## **Change Management & Alerts**

- **Configuration Snapshots** – Captures full system configuration at a point in time.
- **Change Detection** – Detects unauthorized changes and integrates with **SNS for alerts**.
- **Integration with CloudTrail** – Provides deeper insight into **who made the changes and when**.

## **Multi-Account & Multi-Region Auditing**

- Supports **AWS Organizations** to enforce policies across multiple AWS accounts.
- Centralized dashboard for monitoring compliance across regions and accounts.
