## Definition

- The AWS Well-Architected Framework is a 6 Pillar Architecture that Defines best practices and guidelines.
## Operational Excellence

- Focuses on running and monitoring systems to deliver business value and continuously improve processes and operations.
- **Key Principles**
    - Monitor and improve operations
    - Automate operations
    - Perform regular operations review
    - Incident management
- **Services**
    - CloudWatch
    - CloudTrail
    - AWS Config
    - AWS Systems Manager

## Security

- Focuses on protecting data, systems, and assets to reduce security risks and maintain privacy.
- **Key Principles**
    - Implement Strong IAM
    - Enable Traceability
    - Apply Security to all layers
    - Automate Security best practices
    - Data Protection
- **Services**
    - IAM (Identity and Access Management)
    - AWS Shield
    - AWS Macie
    - AWS WAF (Web Application Firewall)

## Reliability

- Ensures that the system can recover from failures, scale with demand, and continue to function without interruption.
- **Key Principles**
    - Design for Failure
    - Automate Recovery
    - Test and Simulate Recovery
    - Scalable Infrastructure
- Services
    - Route 53
    - Auto Scalaing
    - RDS Multi-AZ
    - S3 Cross-Region Replication

## Performance Efficiency

- Focuses on using computing resources efficiently to meet system requirements and reduce bottlenecks.
- **Key Principles**
    - Use Serverless architecture
    - Use Caching Solution
    - Choose the Right DB
    - Optimize Performance Monitoring
- **Services**
    - Lambda
    - Cloudfront
    - RDS/Aurora/DynamoDB
    - Auto Scaling

## Cost Optimization

- Focuses on managing costs while maximizing value without compromising performance or reliability
- **Key Principles**
    - Right Size Resources
    - Use Spot Instances
    - Monitor and Optimze Cost
    - Automate Scaling
- **Services**
    - AWS Cost Explorer
    - AWS Budgets
    - Spot Instances
    - AWS Trusted Advisors

## Sustainability

- Focuses on minimizing the environmental impact of running cloud workloads by optimizing resource utilization.
- **Key Principles**
    - Use Energy-Efficient Infrastructure
    - Optimize Resource Usage
    - Reduce Storage Footprint
    - Track Carbon Footprint
- **Services**
    - AWS Autoscaling
    - AWS Compute Optimizer
    - S3 Lifecycle policies