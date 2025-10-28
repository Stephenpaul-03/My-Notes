## **Auditing**

- Auditing is the **tracking and recording** of everything that happens in your systems — logins, logouts, changes, queries, failures, and suspicious stuff.
- In humanese:
- Who did what, when, where, and how.
- If something shady goes down, you need **receipts**.
### **# What gets audited?**

| Thing Tracked          | Examples                         |
| ---------------------- | -------------------------------- |
| **User activity**      | Login attempts, password changes |
| **Data access**        | SELECT/INSERT/UPDATE/DELETE      |
| **System changes**     | Schema updates, config changes   |
| **Permission changes** | GRANT/REVOKE, role assignments   |
| **Failed attempts**    | Access denied, invalid creds     |
### **# Reasons**

- **Detect insider threats**
- **Forensics after a breach**
- **Meet compliance standards**
- **Prove you’re not reckless**
### **# Real-World Tech**

- **Database auditing**
    - PostgreSQL: `pgaudit`
    - Oracle: `AUDIT` statements
    - SQL Server: Built-in Audit feature
- **OS auditing**
    - Linux: `auditd`, SELinux logs
    - Windows Event Viewer
- **Cloud auditing**
    - AWS CloudTrail
    - GCP Audit Logs
    - Azure Monitor
## **Compliance**

- Compliance is following a **set of rules and regulations** (industry, legal, or organizational) to make sure you're not leaking data, cutting corners, or setting your company up for lawsuits.
### **# Common Compliance Frameworks:**

| Acronym | Stands For | Who Cares? |
| --- | --- | --- |
| **GDPR** | General Data Protection Regulation | EU citizens’ data |
| **HIPAA** | Health Insurance Portability and Accountability Act | US healthcare |
| **PCI-DSS** | Payment Card Industry Data Security Standard | Anyone handling credit cards |
| **SOX** | Sarbanes-Oxley Act | Public companies (financial integrity) |
| **ISO 27001** | International Security Standard | Global orgs, high-trust environments |
### **# Typical Compliance Requirements**

- **Encryption at rest + in transit**
- **Access control & RBAC**
- **Audit logs and retention policies**
- **Incident response plans**
- **Data retention + deletion policies**
- **User consent & data privacy**
### **# Consequences of Non-Compliance**

| Violation | Consequence |
| --- | --- |
| GDPR breach | Up to €20 million or 4% of global revenue |
| HIPAA fail | Fines + criminal charges |
| PCI-DSS fail | Blocked from processing cards |
| SOX violation | Jail time for execs |