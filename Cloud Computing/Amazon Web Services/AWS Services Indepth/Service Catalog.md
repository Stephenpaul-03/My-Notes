## Definition

- AWS Service Catalog enables organizations to create, manage, and distribute approved IT resources in a centralized manner. 
- It ensures that users deploy pre-approved AWS services that align with security, compliance, and cost control policies.
## **Centralized Resource Management**

- **Pre-approved Products** – Administrators define and publish AWS resources (EC2, RDS, VPC, etc.) as **products**.
- **Self-Service Portal** – End users can deploy only the approved resources without requiring admin access.
- **Version Control** – Maintains different versions of products for updates and rollback.

## **Portfolio & Product Structure**

- **Portfolios** – Collections of approved AWS **products** assigned to specific users or teams.
- **Products** – AWS resources defined using **CloudFormation templates**.
- **Constraints** – Enforce policies such as allowed instance types or VPC configurations.

## **Security & Compliance**

- **IAM Integration** – Restricts access to specific users or roles.
- **Tagging Policies** – Ensures cost allocation and resource tracking.
- **AWS Organizations Integration** – Standardizes IT resource deployments across multiple accounts.

## **Automation & Governance**

- **CloudFormation & Terraform Support** – Deploys infrastructure as code.
- **ServiceNow & Jira Integration** – Works with IT service management (ITSM) tools.
- **Automated Provisioning** – Streamlines deployments while enforcing governance policies.
