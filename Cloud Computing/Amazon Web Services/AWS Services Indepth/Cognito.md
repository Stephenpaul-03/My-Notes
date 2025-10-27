## **Definition**

- **Amazon Cognito** is an **authentication, authorization, and user management service** that enables developers to add **sign-in, sign-up, and access control** features to applications.  
- It supports **federated authentication**, **social logins**, and **multi-factor authentication (MFA)**.

## **Cognito User Pools (Authentication & Identity Management)**

- **User Directory** – Stores and manages user profiles securely.  
- **Sign-In & Sign-Up** – Supports username/password authentication with customizable **UI**.  
- **Multi-Factor Authentication (MFA)** – Adds extra security using **SMS or TOTP (Google Authenticator, etc.)**.  
- **Federated Authentication** – Supports login with **Google, Facebook, Apple, Amazon, and enterprise identity providers** via **SAML & OpenID Connect (OIDC)**.  
- **Custom Authentication Flows** – Use **AWS Lambda triggers** for custom authentication logic.

## **Cognito Identity Pools (Authorization & AWS Resource Access)**

- **Grants temporary AWS credentials** (IAM roles) to authenticated users.  
- Allows access to AWS services like **S3, DynamoDB, Lambda, and API Gateway**.  
- Supports both **authenticated (logged-in)** and **unauthenticated (guest)** users.

## **Security & Compliance**

- **Data Encryption** – Uses **AWS KMS** to encrypt user data.  
- **User Account Recovery** – Supports **email/SMS-based password reset**.  
- **Advanced Security Features** – Detects compromised credentials and provides adaptive authentication.

## **Integration & Customization**

- **AWS Amplify** – Seamlessly integrates Cognito for frontend applications.  
- **API Gateway & Lambda** – Works well for securing APIs and backend authentication.  
- **Customizable UI & Hosted UI** – Provides a pre-built authentication UI or allows custom branding.
