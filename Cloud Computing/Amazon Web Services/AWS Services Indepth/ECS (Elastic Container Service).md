## **Definition**

- Amazon **ECS** is a **fully managed container orchestration service** that helps run, manage, and scale containerized applications using **Docker**.  
- It provides **tight integration with AWS services** for seamless deployment and scaling.

## **ECS Launch Types**

ECS offers two ways to run containers:  

- **Fargate (Serverless Mode)** – No need to manage servers; AWS handles infrastructure.  
- **EC2 (Self-Managed Mode)** – Runs on EC2 instances that you manage.

## **Scaling & Monitoring**

- **Auto Scaling** – Increases or decreases container instances based on demand.  
- **CloudWatch Logs** – Monitors logs from running containers.  
- **CloudTrail** – Tracks ECS API calls for auditing.

## **ECS Components**

- **Task Definition** – A blueprint defining how to run a container (CPU, memory, networking, environment variables).  
- **Task** – A running instance of a Task Definition (can have one or more containers).  
- **Service** – Manages how many tasks run and replaces unhealthy ones automatically.  
- **Cluster** – A logical group of tasks and services (runs on EC2 instances or Fargate).

## **ECS vs. EKS vs. Kubernetes**

- **ECS** – AWS-managed, easy-to-use container orchestration.  
- **EKS (Elastic Kubernetes Service)** – Fully managed **Kubernetes** on AWS.  
- **Kubernetes** – Open-source container orchestration platform, requires more setup.

## **Networking & Security**

- **Elastic Load Balancer (ELB)** – Distributes traffic across containers.  
- **AWS VPC Integration** – ECS tasks run inside a VPC with security groups.  
- **IAM Roles** – Fine-grained access control for ECS services and tasks.

## **Storage & Persistent Data**

- **Amazon EFS** – Attach persistent storage to ECS tasks.  
- **EBS Volumes** – Store data that persists across task restarts.
