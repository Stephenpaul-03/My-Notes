## **Definition**

- AWS **WAF (Web Application Firewall)** helps protect web applications and APIs against **common web threats**, such as **SQL injection (SQLi), cross-site scripting (XSS), and bot attacks**.
- It provides **customizable rule-based filtering** to control and monitor incoming traffic.

## **Protection Against Web Threats**

AWS WAF helps mitigate:

- **SQL Injection (SQLi)** – Prevents attackers from injecting malicious SQL queries.
- **Cross-Site Scripting (XSS)** – Blocks scripts that could compromise users’ browsers.
- **DDoS Attacks** – Works with **AWS Shield** to prevent excessive traffic floods.
- **Bots & Scrapers** – Identifies and blocks unwanted bots.
- **IP Address Restrictions** – Allows or blocks traffic from specific IP addresses or geolocations.

## **Web ACLs (Access Control Lists)**

AWS WAF rules are **grouped into Web ACLs** that define **how incoming traffic is filtered**. Each Web ACL consists of:

- **Rules** – Define traffic filtering logic (e.g., block SQL injection attempts).
- **Rule Actions** – Allow, block, or count traffic matching specific conditions.
- **Rule Prioritization** – Ensures rules are evaluated in a specific order.

## **Predefined & Custom Rules**

- **Managed Rule Groups** – Predefined security rules from AWS & third-party providers (e.g., OWASP Top 10 protections).
- **Custom Rules** – Users can create their own rules using AWS WAF’s rule engine.

## **Real-Time Monitoring & Logging**

- **CloudWatch Integration** – Logs traffic patterns and blocked requests.
- **AWS Firewall Manager** – Centralized security management for multiple accounts.

## **Integration with AWS Services**

AWS WAF works seamlessly with:

- **Amazon CloudFront** – Protects web applications at the edge.
- **Application Load Balancer (ALB)** – Filters traffic before reaching backend servers.
- **API Gateway** – Secures RESTful APIs from malicious requests.
- **AWS Shield Advanced** – Enhances protection against large-scale DDoS attacks.
