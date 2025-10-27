## **Definition**

- AWS **CloudTrail** is a service that enables **logging, monitoring, and auditing** of AWS API calls and actions across an AWS account.
- It provides visibility into **who did what, when, and from where**, helping with security analysis, compliance, and troubleshooting.

## **Event Logging & Visibility**

- Records **API calls and AWS Management Console actions** across services.
- Captures **who made the request, what action was taken, and when it occurred**.
- Includes details like **IAM user, IP address, and request parameters**.

## **Types of Events**

- **Management Events** – Track AWS **account-level activities** (e.g., creating an EC2 instance, modifying IAM policies).
- **Data Events** – Logs **data access actions** (e.g., S3 object reads, Lambda function executions).
- **Insights Events** – Detects **unusual API activity** that deviates from normal patterns.

## **Trail Configuration**

- **Event History** – Shows last **90 days of API activity** without needing a trail.
- **Single-Region & Multi-Region Trails** – Captures events across all AWS regions for centralized logging.
- **Organization Trails** – Enables logging across multiple AWS accounts via AWS Organizations.

## **Security & Compliance**

- **Multi-Region & Multi-Account Logging** – Centralized logging across all AWS accounts in an organization.
- **Immutable Logs** – Logs stored in S3 can be encrypted and protected with **MFA Delete** and **S3 Object Lock**.
- **Integration with AWS Security Hub & GuardDuty** – Helps detect security threats.
