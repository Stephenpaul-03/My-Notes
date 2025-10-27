## **Definition**

- **AWS Fargate** is a **serverless compute engine** for containers.  
- It allows running containers **without managing EC2 instances**, making it ideal for **ECS** and **EKS** workloads.

## **How Fargate Works**

- **Runs tasks (ECS) or pods (EKS) directly** without needing to launch EC2 instances.  
- **No need to manage OS, scaling, or patching** – AWS handles it all.  
- **Pay-per-use pricing** – Based on vCPU and memory allocated to tasks/pods.

## **Monitoring & Logging**

- **CloudWatch Logs** – Collect logs from running tasks.  
- **AWS X-Ray** – Trace application requests for debugging.  
- **Container Insights** – Monitor performance and resource usage.

## **Compute & Scaling**

- **Auto Scaling** – Adjusts based on traffic and demand.  
- **Resource Allocation** – Choose CPU (0.25 – 16 vCPU) and memory (0.5 – 120 GB).  
- **Ephemeral Storage** – Default **20GB**, expandable up to **200GB** per task.

## **Networking & Security**

- **VPC Networking** – Each task/pod runs in an **isolated environment** with its own ENI (Elastic Network Interface).  
- **IAM Permissions** – Assign fine-grained access control to containers.  
- **Security Groups & Private Subnets** – Securely deploy workloads in a private network.
