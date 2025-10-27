## **Definition**

- AWS **Secrets Manager** is a **managed service for securely storing, managing, and retrieving secrets**, such as **database credentials, API keys, and application passwords**.
- It automates **secret rotation, access control, and auditing** to enhance security.

## **Secure Storage & Encryption**

- Stores **secrets (e.g., passwords, API keys, tokens, SSH keys)** securely.
- Uses **AWS KMS (Key Management Service)** to encrypt secrets **at rest and in transit**.

## **Automatic Secret Rotation**

- Supports **automatic rotation of credentials** for:
    - **RDS databases (MySQL, PostgreSQL, Aurora, etc.)**
    - **Other applications via AWS Lambda functions**
- Reduces **security risks from long-lived credentials**.

## **Secure Access & Permissions**

- Uses **IAM policies and resource-based policies** to control **who can access secrets**.
- Supports **fine-grained access control** to specific secrets.
- Allows **applications and AWS services** to retrieve secrets securely via the AWS SDK or CLI.

## **Versioning & Audit Logging**

- Maintains **multiple versions** of secrets to track changes.
- Logs all secret access and changes via **AWS CloudTrail** for security auditing.

## **Integration with AWS Services**

- Works with **RDS, Redshift, DocumentDB, Lambda, ECS, and EC2**.
- Can be used with **AWS Systems Manager Parameter Store** for centralized configuration management.
