## **Definition**

- **AWS Lambda** is a **serverless computing service** that lets you run code without provisioning or managing servers.
- It **automatically scales** and charges only for execution time.

## **Event-Driven Execution**

- AWS Lambda runs code in response to **triggers** (e.g., an S3 file upload, an API Gateway request, or a database update).
- Common event sources:
    - **S3** – Runs a function when a file is uploaded.
    - **DynamoDB Streams** – Processes data changes in real time.
    - **API Gateway** – Executes functions when an HTTP request is received.
    - **SNS/SQS** – Triggers functions via messaging.

## **Deployment & Monitoring**

- **AWS CloudWatch Logs** – Monitors function execution and logs errors.
- **AWS X-Ray** – Provides tracing and debugging for Lambda invocations.
- **Layers** – Reusable code components shared across multiple functions.

## **Scaling & Performance**

- **Automatic Scaling** – Lambda scales **horizontally** by running multiple instances of your function in parallel.
- **Cold Starts** – Initial execution may have a slight delay due to container startup.
- **Provisioned Concurrency** – Keeps functions **warm** to reduce cold start delays.

## **Pricing Model**

- **Pay-per-execution** – You only pay for the compute time used.
- **Free tier**: 1 million requests & 400,000 GB-seconds per month.

## **Security & Permissions**

- Uses **IAM roles** to grant permissions for AWS services.
- **VPC Integration** – Can run inside a private VPC for secure networking.

## **Supported Languages**

- Python
- Node.js
- Java
- C# (.NET Core)
- Ruby
- Go

## **Execution & Time Limits**

- **Max execution time**: 15 minutes per function.
- **Memory allocation**: 128 MB to 10 GB.
- **Ephemeral storage**: 512 MB (or up to 10 GB if configured).
