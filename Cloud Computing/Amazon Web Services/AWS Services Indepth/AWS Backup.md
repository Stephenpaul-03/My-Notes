## **Definition**

- AWS **Backup** is a **fully managed, centralized backup service** that automates data backup across multiple AWS services.
- It simplifies backup management, ensures compliance, and allows for **policy-driven** backup scheduling and lifecycle management.

## **Centralized Backup Management**

- **Single dashboard** to manage backups across AWS services.
- **Supports multiple AWS services** like **EBS, RDS, DynamoDB, EFS, FSx, EC2, and S3**.
- **Automated backup scheduling** to reduce manual effort.

## **Backup Plans & Policies**

- **Backup Plans** → Define **when, how often, and where** backups should be created.
- **Lifecycle Policies** → Automatically transition backups from **hot storage** to **cold storage** (Glacier).
- **Retention Policies** → Automatically delete old backups to optimize cost.

## **Compliance & Audit Logs**

- **AWS Backup Audit Manager** → Helps meet compliance requirements.
- **Integration with AWS Organizations** → Enforce backup policies across multiple AWS accounts.
- **AWS CloudTrail Logging** → Tracks backup activities for security audits.

## **Cross-Region & Cross-Account Backups**

- **Cross-Region Backup** → Store backups in different AWS regions for disaster recovery.
- **Cross-Account Backup** → Back up resources to another AWS account for **security isolation**.

## **Backup Vaults & Security**

- **Backup Vaults** → Store backups securely with encryption.
- **AWS Key Management Service (KMS) Encryption** → Ensures data is protected at rest and in transit.
- **IAM Policies & Access Control** → Restrict who can create, modify, or restore backups.
