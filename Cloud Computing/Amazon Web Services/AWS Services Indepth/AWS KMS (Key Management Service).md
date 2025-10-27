## **Definition**

- AWS Key Management Service (KMS) is a managed encryption service that allows users to create, manage, and control cryptographic keys for securing AWS resources and applications.
- It integrates with various AWS services to encrypt data at rest and in transit.

## **Centralized Key Management**

- **Create, rotate, and disable encryption keys** within AWS.
- Supports **Customer Managed Keys (CMKs)** and **AWS Managed Keys**.
- Provides fine-grained **access control using IAM policies and key policies**.

## **Key Types in AWS KMS**

- **AWS Managed Keys** – Automatically managed by AWS for services like **S3, RDS, and EBS**.
- **Customer Managed Keys (CMKs)** – Users **create and control** their own encryption keys.
- **CloudHSM-backed Keys** – Provides **hardware security module (HSM) protection** for high-security use cases.

## **Key Policies & Access Control**

- Uses **IAM policies, key policies, and grants** to manage key access.
- Can restrict **who can use, modify, or delete a key**.
- Supports **logging key usage via AWS CloudTrail** for auditability.

## **Encryption & Decryption**

- Encrypts and decrypts **data, files, and passwords** across AWS services.
- Works with **S3, EBS, RDS, DynamoDB, Lambda, and more** for built-in encryption.
- Uses **AES-256 encryption standard** for securing data.

## **Data Protection & Compliance**

- Helps **meet regulatory compliance** (e.g., **PCI DSS, HIPAA, GDPR**).
- Ensures **data is encrypted before storage** to prevent unauthorized access.
- Supports **Bring Your Own Key (BYOK)** for custom encryption key management.
