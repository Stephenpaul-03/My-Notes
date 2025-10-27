## **Definition**

- AWS IAM (Identity and Access Management) is a service that enables you to securely manage access to AWS services and resources. 
- It allows fine-grained permissions, authentication, and authorization to ensure the right users and systems have the appropriate access.

## **IAM Identities**

- **IAM Users** – Individual accounts assigned to people or applications.
- **IAM Groups** – Collections of users sharing the same permissions.
- **IAM Roles** – **Temporary access credentials** assigned to AWS services or external users.
- **IAM Policies** – JSON-based rules defining **who can access what** and what actions they can perform.

## **Authentication & Security**

- **MFA (Multi-Factor Authentication)** – Adds extra security to IAM users and roles.
- **IAM Access Keys** – Used for programmatic access via the AWS CLI or SDKs.
- **Federated Access** – Enables **SSO (Single Sign-On)** using services like **Active Directory, SAML, and OIDC**.

## **Secure Access to AWS Services**

- **Instance Profiles** – Assign IAM roles to **EC2 instances** for secure API access.
- **Cross-Account Access** – Allow resources in **one AWS account to access another** securely.

## **Permissions & Access Control**

- **Least Privilege Principle** – Grant only the necessary permissions to users and services.
- **Managed Policies** – Predefined AWS policies for common use cases.
- **Customer-Managed Policies** – Custom policies created by users.
- **Inline Policies** – Policies embedded directly within a user, group, or role.
- **Permission Boundaries** – Restricts the **maximum permissions** an IAM identity can get.
- **Service Control Policies (SCPs)** – Enforce permissions **across multiple AWS accounts** in AWS Organizations.
