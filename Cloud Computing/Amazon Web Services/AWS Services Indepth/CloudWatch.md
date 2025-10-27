## **Definition**

- **Amazon CloudWatch** is a **monitoring and observability service** that provides **real-time insights** into AWS resources, applications, and services.  
- It collects and tracks **metrics, logs, and events**, helping detect anomalies, troubleshoot issues, and optimize performance.

## **Logs (CloudWatch Logs)**

- **Log Groups & Log Streams** – Stores logs from EC2, Lambda, API Gateway, VPC Flow Logs, etc.  
- **Log Insights** – Allows querying and analyzing log data for troubleshooting.  
- **Log Retention & Export** – Can retain logs for compliance or export to **S3 & Elasticsearch**.

## **CloudWatch Agent**

- **Collects system-level metrics** (CPU, memory, disk, network usage) from on-premises or EC2 instances.  
- Supports both **Linux & Windows** environments.

## **Metrics & Alarms**

- **Metrics** – Collects performance data from AWS services (e.g., CPU usage of EC2, latency of RDS).  
- **Custom Metrics** – Users can publish their own application-specific metrics.  
- **Alarms** – Triggers automated actions based on metric thresholds (e.g., send alerts, auto-scale EC2).

## **Events & Automation (CloudWatch Events / EventBridge)**

- **Event-driven Automation** – Detects changes in AWS services and triggers actions via **Lambda, SNS, or SQS**.  
- **Event Rules** – Defines how AWS services react to system or application changes.  
- **EventBridge** – An advanced event bus for integrating AWS and third-party applications.

## **CloudWatch Dashboards**

- **Visualizes real-time data** from AWS services in a single view.  
- Supports **multi-account and multi-region** monitoring.  
- Customizable with **graphs, charts, and widgets**.
