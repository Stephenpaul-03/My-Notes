## **Definition**

- AWS **Multi-Factor Authentication (MFA)** is a **security feature** that enhances account protection by requiring users to provide **two forms of authentication** when signing in. 
- This reduces the risk of unauthorized access due to compromised passwords.

## **Two-Factor Authentication (2FA)**

- Requires users to enter:
    1. **Something they know** (password)
    2. **Something they have** (MFA device-generated code)

## **MFA for AWS Accounts**

- **AWS Root User MFA** (Highly recommended for securing AWS account)
- **IAM User MFA** (Required for sensitive operations and admin access)
- **MFA for AWS CLI & SDK** (Can enforce MFA for programmatic access using temporary security credentials)

## **Supported MFA Methods**

- **Virtual MFA Devices** (Most common)
    - Uses **TOTP (Time-Based One-Time Password)** applications like:
        - **Google Authenticator**
        - **Authy**
        - **Microsoft Authenticator**
- **Hardware MFA Devices**
    - **FIDO2 security keys** (e.g., **YubiKey, Titan Security Key**)
    - **OTP-based hardware tokens**
- **SMS & Email MFA** (For AWS Root User only, but less secure)

## **MFA Enforcement & Policies**

- **IAM Policies** can be configured to **require MFA** before allowing access to sensitive resources.
- **AWS Organizations & SCPs** (Service Control Policies) can enforce MFA across multiple accounts.

## **Integration with AWS Services**

- **AWS IAM** – Enforce MFA for user logins.
- **AWS SSO (Single Sign-On)** – Supports MFA for federated access.
- **AWS Cognito** – Enables MFA for application authentication.
