## **Definition**

- AWS **Inspector** is an **automated vulnerability management service** that scans AWS workloads for **security vulnerabilities, misconfigurations, and compliance risks**.
- It helps detect **unpatched software, exposed ports, and security flaws** in EC2 instances, container images, and Lambda functions.

## **Automated Vulnerability Scanning**

- **Continuously scans AWS workloads** for known security risks.
- Identifies **CVE (Common Vulnerabilities and Exposures)** in EC2 instances, container images, and Lambda functions.
- Uses **AWS Systems Manager Agent (SSM Agent)** to collect security findings from EC2 instances.

## **Container & Lambda Security**

- Scans **Amazon Elastic Container Registry (ECR)** images for vulnerabilities.
- Checks **Lambda functions** for insecure permissions and outdated dependencies.

## **Severity-Based Findings & Risk Prioritization**

- Uses the **Amazon Inspector Risk Score** to rank security issues based on severity.
- **Integrates with AWS Security Hub** for centralized threat visibility.
- Provides **remediation recommendations** for detected vulnerabilities.

## **Continuous & On-Demand Assessments**

- Supports **real-time vulnerability detection** for workloads.
- Allows users to run **on-demand security assessments** when needed.

## **Compliance & Security Standards**

- Helps organizations **meet compliance requirements** (e.g., CIS, PCI DSS, NIST).
- Ensures workloads **adhere to security best practices**.
