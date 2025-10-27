## **Definition**

- Amazon **EKS** is a **fully managed Kubernetes service** that simplifies running Kubernetes on AWS.  
- It provides a **highly available and secure control plane** without needing to manage Kubernetes clusters manually.

## **Kubernetes Basics in EKS**

- **Cluster** – A group of EC2 instances or Fargate tasks running Kubernetes.  
- **Pods** – The smallest deployable unit in Kubernetes (a pod can have one or more containers).  
- **Nodes** – EC2 instances or Fargate tasks that run Kubernetes workloads.  
- **Control Plane** – Managed by AWS; handles scheduling, API access, and cluster state.  
- **Worker Nodes** – Runs applications and connects to the control plane.

## **Storage & Persistent Data**

- **EFS (Elastic File System)** – Shared, scalable file storage for EKS pods.  
- **EBS (Elastic Block Store)** – Block storage for stateful applications.  
- **FSx for Lustre** – High-performance storage for ML and big data workloads.

## **Deployment & Scaling**

- **Auto Scaling** – Uses Cluster Autoscaler or Karpenter for efficient resource allocation.  
- **Load Balancing** – Supports ALB, NLB, and Kubernetes-native services like Ingress.  
- **Fargate for EKS** – Runs Kubernetes pods without managing EC2 instances.

## **Monitoring & Logging**

- **CloudWatch Logs** – Captures logs from Kubernetes clusters.  
- **Amazon Managed Prometheus & Grafana** – Kubernetes-native monitoring solutions.  
- **AWS X-Ray** – Traces application performance in microservices.

## **Security & Networking**

- **IAM Roles for Service Accounts (IRSA)** – Fine-grained access control for Kubernetes workloads.  
- **Amazon VPC CNI** – Provides **native VPC networking** for EKS pods.  
- **EKS Secrets Manager** – Stores sensitive configuration securely.

## **EKS vs. ECS**

- **EKS (Kubernetes-based)** – Uses open-source Kubernetes, supports **multi-cloud** and on-prem via **EKS Anywhere**.  
- **ECS (AWS-native)** – Simpler, tightly integrated with AWS, but not multi-cloud.
