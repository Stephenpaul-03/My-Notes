## Compute Services

| Service Name                | Brief Description                                                                            | Use Cases                                                                       |
| --------------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| EC2                         | Scalable virtual servers in the cloud for running applications.                              | Hosting web applications, batch processing, running backend servers.            |
| Lambda                      | Serverless compute service that runs code in response to events without managing servers.    | Serverless microservices, real-time file processing, event-driven applications. |
| ECS                         | Managed service for running Docker containers at scale.                                      | Running containerized microservices, web applications, batch jobs.              |
| EKS                         | Fully managed Kubernetes service for deploying containerized applications.                   | Orchestrating large-scale Kubernetes workloads, hybrid cloud deployments.       |
| Fargate                     | Serverless compute engine for running containers without managing servers.                   | Running short-lived containers without managing servers.                        |
| Lightsail                   | Simplified cloud hosting for websites, applications, and databases with predictable pricing. | Hosting small websites, blogs, and lightweight applications.                    |
| Batch                       | Fully managed service for running batch computing jobs at scale.                             | Batch data processing, compute-intensive workloads.                             |
| Elastic Load Balancer (ELB) | Distributes incoming traffic across multiple EC2 instances.                                  | Distributing traffic to multiple EC2 instances for high availability.           |
## Storage Services

| Service Name    | Brief Description                                               | Use Cases                                                                     |
| --------------- | --------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| S3              | Object storage for scalable data storage and backup.            | Storing backup files, hosting static websites, data lake storage.             |
| EBS             | Block storage for EC2 instances, providing persistent storage.  | Persistent storage for EC2 instances, databases, application data.            |
| EFS             | Scalable file storage for EC2 instances with shared access.     | File storage for web applications, shared storage for multiple EC2 instances. |
| AWS Backup      | Centralized service for automating backups across AWS services. | Centralized backup management for databases, EBS, RDS, and more.              |
| FSx             | Managed file storage for Windows and Lustre workloads.          | Windows-based file systems, high-performance computing workloads.             |
| Glacier         | Low-cost, long-term archival storage with retrieval options.    | Archival of infrequently accessed data.                                       |
| Storage Gateway | Hybrid cloud storage integration between on-premises and AWS.   | Seamless integration of on-premises environments with AWS cloud storage.      |
## Databases

| Service Name | Brief Description                                                                       | Use Cases                                                                   |
| ------------ | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| RDS          | Managed relational database service supporting multiple engines like MySQL, PostgreSQL. | Hosting transactional databases like MySQL, PostgreSQL, and SQL Server.     |
| DynamoDB     | NoSQL key-value and document database with millisecond latency.                         | Storing session data, shopping cart data, IoT data, leaderboards.           |
| Redshift     | Fully managed data warehouse for large-scale analytics.                                 | Data warehousing for business intelligence and analytics.                   |
| Aurora       | High-performance relational database compatible with MySQL and PostgreSQL.              | High-performance relational database for SaaS applications.                 |
| ElastiCache  | In-memory caching service for improved database performance.                            | Caching database queries, reducing database load, improving response times. |
| Neptune      | Fully managed graph database for relationships and network analysis.                    | Social networking applications, fraud detection, recommendation engines.    |
| Timestream   | Fully managed time-series database for IoT and real-time analytics.                     | Real-time IoT data ingestion and analysis.                                  |
| MemoryDB     | In-memory database optimized for microservices.                                         | Low-latency, highly available data store for microservices.                 |
## Networking & Content Delivery

| Service Name                | Brief Description                                                                | Use Cases                                                                   |
| --------------------------- | -------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| VPC                         | Isolated cloud environment for AWS resources.                                    | Isolated cloud network for running AWS applications securely.               |
| Route 53                    | Scalable DNS and domain registration service.                                    | DNS hosting for websites, traffic routing, domain registration.             |
| Elastic Load Balancer (ELB) | Distributes incoming traffic across multiple targets.                            | Distributing traffic to multiple EC2 instances for high availability.       |
| CloudFront                  | Global content delivery network (CDN) for low-latency content distribution.      | Accelerating website and API delivery with global caching.                  |
| Direct Connect              | Dedicated network connection between AWS and on-premises data centers.           | Establishing a private, high-speed connection between AWS and data centers. |
| Global Accelerator          | Improves application availability and performance using AWS edge locations.      | Improving performance of global applications with low-latency routing.      |
| PrivateLink                 | Secure, private access to AWS services without exposing traffic to the internet. | Enabling secure communication between VPCs and AWS services.                |
| Transit Gateway             | Centralized hub for connecting multiple VPCs and on-premises networks.           | Simplifying network architecture by interconnecting VPCs and data centers.  |
## Security & Identity

| Service Name         | Brief Description                                                               | Use Cases                                                                             |
| -------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| IAM                  | Controls user access to AWS resources.                                          | Managing permissions and access controls for AWS users and services.                  |
| Cognito              | User authentication and authorization for web and mobile apps.                  | Managing authentication and user sign-up/sign-in workflows.                           |
| Service Catalog      | Manages and deploys approved AWS services within organizations.                 | Deploying standardized AWS resources across teams.                                    |
| AWS Organizations    | Centralized account management and policy enforcement.                          | Managing multiple AWS accounts with shared policies.                                  |
| AWS Control Tower    | Automates multi-account governance and security best practices.                 | Enforcing governance, security, and compliance in AWS multi-account environments.     |
| AWS Shield           | DDoS protection service for AWS applications.                                   | Mitigating volumetric, protocol, and application-layer DDoS attacks.                  |
| AWS WAF              | Web Application Firewall for filtering web traffic and protecting applications. | Blocking cmmon web exploits like SQL injection and XSS.                               |
| AWS Security Hub     | Centralized security and compliance monitoring.                                 | Aggregating, prioritizing, and visualizing security alerts.                           |
| AWS Inspector        | Automated vulnerability assessment for AWS workloads.                           | Scanning EC2 instances for software vulnerabilities and misconfigurations.            |
| AWS KMS              | Managed service for creating and managing encryption keys.                      | Encrypting data at rest and in transit across AWS services.                           |
| AWS Secrets Manager  | Secure storage and automatic rotation of sensitive credentials.                 | Managing API keys, database passwords, and other secrets.                             |
| AWS GuardDuty        | Threat detection and continuous monitoring.                                     | Identifying suspicious activity and unauthorized behavior.                            |
| AWS MFA              | Multi-Factor Authentication for increased account security.                     | Enforcing strong authentication using hardware or virtual MFA devices.                |
| IAM Access Analyzer  | Identifies unintended public or cross-account access to resources.              | Analyzing permissions to ensure least privilege principles.                           |
| AWS Network Firewall | Managed firewall for controlling network traffic in VPCs.                       | Implementing stateful inspection and intrusion prevention rules in VPC traffic flows. |
| AWS Detective        | Investigates security findings using machine learning and graph analysis.       | Root cause analysis of security events and suspicious behaviors.                      |
## Monitoring & Management

| Service Name          | Brief Description                                                             | Use Cases                                                                                    |
| --------------------- | ----------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| CloudWatch            | Monitoring and observability for AWS applications and infrastructure.         | Setting alarms, visualizing metrics, and analyzing logs.                                     |
| CloudTrail            | Logs and monitors AWS API activity for governance and auditing.               | Auditing API activity to meet compliance and forensic requirements.                          |
| AWS Config            | Tracks AWS resource configurations and changes over time.                     | Ensuring compliance and identifying configuration drift.                                     |
| AWS Trusted Advisor   | Provides best practices for security, performance, fault tolerance, and cost. | Optimizing AWS environments by recommending improvements.                                    |
| AWS Macie             | Uses ML to discover and protect sensitive data in S3.                         | Identifying and classifying personally identifiable information (PII).                       |
| Systems Manager (SSM) | Centralized operations hub for managing AWS resources.                        | Running automation scripts, managing patching, and remote management.                        |
| Application Insights  | Automatically detects problems in applications.                               | Diagnosing performance issues and exceptions in applications without manual instrumentation. |
## Billing & Cost Management

| Service Name | Brief Description | Use Cases |
| --- | --- | --- |
| AWS Pricing Calculator | Estimates AWS service costs before deployment. | Forecasting infrastructure costs during architecture planning. |
| AWS Cost Explorer | Analyzes and visualizes AWS usage and spending trends. | Identifying spending patterns, optimizing resource usage, and controlling expenses. |
| AWS Budgets | Sets custom cost and usage thresholds and sends alerts. | Monitoring and alerting for budget overruns and cost thresholds. |
| Savings Plans | Flexible pricing for consistent usage across services (e.g., EC2, Fargate). | Reducing long-term compute costs based on usage commitment. |
## Migration & Transfer

| Service Name                        | Brief Description                                                             | Use Cases                                                                        |
| ----------------------------------- | ----------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| AWS Migration Service               | Assists in migrating workloads to AWS with minimal downtime.                  | Moving enterprise applications and infrastructure to AWS.                        |
| Application Migration Service (MGN) | Automates lift-and-shift migrations of physical, virtual, or cloud servers.   | Quickly rehosting applications with minimal changes.                             |
| Database Migration Service (DMS)    | Migrates on-premises databases to AWS with minimal downtime.                  | Moving databases like Oracle, MySQL, and SQL Server to RDS or Aurora.            |
| Server Migration Service (SMS)      | Automates migration of on-premises virtual machines to AWS.                   | Lifting and shifting VMware or Hyper-V VMs to the cloud.                         |
| SnowBall                            | Rugged device for petabyte-scale data transfer to AWS.                        | Transferring large datasets when network bandwidth is limited or non-viable.     |
| SnowCone                            | Portable edge device for small-scale edge computing and data transfer.        | Running edge workloads in rugged environments with limited connectivity.         |
| SnowMobile                          | Shipping container-sized device for exabyte-scale data migrations.            | Massive-scale data center migration to AWS.                                      |
| DataSync                            | Accelerates and automates data transfers between on-premises storage and AWS. | Synchronizing or migrating datasets quickly for backup or cloud-based analytics. |
| AWS Transfer Family                 | Supports secure transfers using SFTP, FTPS, and FTP into Amazon S3.           | Enabling legacy file transfer workflows using industry-standard protocols.       |
## Analytics & AI/ML

| Service Name | Brief Description | Use Cases |
| --- | --- | --- |
| Athena | Serverless SQL query service to analyze data directly in S3. | Ad hoc querying of large datasets stored in S3 without setting up infrastructure. |
| SageMaker | End-to-end managed ML service for building, training, and deploying models. | Predictive analytics, real-time inference, model training and deployment. |
| Rekognition | Image and video analysis using AI/ML for facial/object detection. | Facial recognition, content moderation, scene detection. |
| QuickSight | Business intelligence service for dashboards and data visualizations. | Creating reports, tracking KPIs, and business metrics visualization. |
| Transcribe | Converts speech to text using ML. | Customer service analysis, subtitling videos, voice interface support. |
| Comprehend | NLP service for text analysis, sentiment detection, and entity recognition. | Social media monitoring, customer sentiment analysis, document classification. |
| Textract | Extracts text and data from scanned documents using AI. | Invoice processing, form extraction, OCR from PDFs. |
| Kinesis | Real-time data streaming service. | Real-time analytics, data ingestion for IoT, application log processing. |
| Glue | Managed ETL service to prepare data for analytics. | Data cleaning, transformation, cataloging before loading into analytics engines. |
| Forecast | Time-series forecasting using ML. | Demand planning, inventory forecasting, capacity planning. |
| Personalize | Real-time recommendation engine powered by ML. | Building recommendation systems for e-commerce, media, or personalized content delivery. |
## IoT & Edge Computing

| Service Name   | Brief Description                                                                 | Use Cases                                                                 |
| -------------- | --------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| IoT Core       | Managed service for secure device connectivity and messaging.                     | Real-time IoT data ingestion, device communication, telemetry processing. |
| IoT Greengrass | Runs AWS services on edge devices for local compute, messaging, and ML inference. | Offline operations, local ML inference, edge analytics.                   |
| IoT SiteWise   | Collects, organizes, and analyzes data from industrial equipment.                 | Industrial IoT applications, predictive maintenance, factory monitoring.  |
| IoT Analytics  | Fully managed analytics service for processing IoT data.                          | Cleaning, processing, storing, and analyzing device telemetry data.       |
| Outposts       | Brings AWS services on-premises for a hybrid experience.                          | Low-latency, on-premise applications with AWS integration.                |
| Wavelength     | Embeds AWS infrastructure in telecom networks for ultra-low latency.              | AR/VR, gaming, real-time machine learning inference at the network edge.  |
## Developer Tools

| Service Name                      | Brief Description                                                                      | Use Cases                                                                               |
| --------------------------------- | -------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| CodeCommit                        | Fully managed source control service that hosts secure Git repositories.               | Version control, collaborative software development, source code hosting.               |
| CodeBuild                         | Fully managed CI service that compiles source code, runs tests, and produces packages. | Continuous integration, automated testing, build automation.                            |
| CodeDeploy                        | Automates code deployments to any instance, including EC2 and on-premises.             | Application updates across environments with minimal downtime.                          |
| CodePipeline                      | CI/CD service for fast and reliable application and infrastructure updates.            | End-to-end automation of software release processes.                                    |
| CodeArtifact                      | Managed artifact repository for storing software packages and dependencies.            | Dependency management, version tracking for application components.                     |
| CodeGuru                          | AI-powered code reviewer and performance analyzer for applications.                    | Code quality analysis, performance profiling, identifying expensive code.               |
| Elastic Beanstalk                 | Platform as a Service for deploying and managing applications quickly.                 | Web app deployment with minimal infrastructure management.                              |
| CloudFormation                    | Infrastructure as Code (IaC) service for modeling and setting up AWS resources.        | Automating infrastructure deployment, version-controlling infrastructure.               |
| Step Functions                    | Serverless orchestration for microservices and workflows.                              | Building and coordinating workflows across AWS services.                                |
| AWS EventBridge                   | Serverless event bus for integrating applications with events from AWS/SaaS apps.      | Event-driven architecture, service decoupling, real-time automation.                    |
| Simple Notification Service (SNS) | Fully managed pub/sub messaging and mobile notification service.                       | Event alerts, application messaging, mobile push notifications.                         |
| Simple Queue Service (SQS)        | Fully managed message queuing service.                                                 | Decoupling microservices, handling asynchronous workloads, ensuring message durability. |
