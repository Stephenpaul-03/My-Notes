## **Definition**

- AWS **GuardDuty** is a **threat detection service** that continuously monitors AWS accounts, workloads, and data for **suspicious activities, unauthorized access, and security threats**.
- It uses **machine learning, anomaly detection, and threat intelligence** to identify potential risks.

## **Threat Detection & Monitoring**

- Analyzes **VPC Flow Logs, CloudTrail Logs, and DNS logs** for unusual behavior.
- Detects threats like **unauthorized API calls, compromised IAM credentials, and malware activity**.
- Identifies **anomalous data exfiltration** and unusual access patterns.

## **Automated Response & Remediation**

- Works with **Amazon EventBridge** to trigger automatic responses.
- Can **quarantine compromised instances** or **block malicious IPs using AWS WAF**.

## **Continuous & Automated Security Analysis**

- Uses **machine learning models** to detect new threats.
- Leverages **AWS threat intelligence feeds** from **AWS, CrowdStrike, and Proofpoint**.
- Runs **continuously with no manual configuration** required.

## **Multi-Account & Compliance Support**

- Supports **AWS Organizations** for **multi-account threat detection**.
- Helps meet security compliance standards like **PCI DSS, GDPR, and NIST**.

## **Threat Findings & Risk Prioritization**

- Generates **detailed security findings** with severity levels:
    - **Low** – Unusual but non-critical activity.
    - **Medium** – Potential security risks (e.g., access from a suspicious IP).
    - **High** – Active security breaches or malicious behavior.
- Integrates with **AWS Security Hub** for centralized visibility.
