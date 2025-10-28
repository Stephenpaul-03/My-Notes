## **Definition**

- Access control in computer networks is a core security strategy designed to manage and control who or what can access various resources, whether these are data, devices, or specific areas of a network. 
- It ensures that only authorized users and systems can view or use sensitive information, minimizing the risk of data breaches and unauthorized actions.

## **Types based on categories**

### # **Discretionary Access Control (DAC):**

- The owner of the resource decides who can access it.
- It's flexible but can be less secure if owners assign permissions too broadly.

### # **Mandatory Access Control (MAC):**

- A central authority (often an operating system or security policy framework) restricts access based on defined security levels and classifications.
- Users and owners cannot override these controls.

### # **Role-Based Access Control (RBAC):**

- Access is determined by the user's role within the organization.
- Permissions are centrally managed according to job functions, making this model very popular in enterprises for its scalability and ease of management.

### # **Rule-Based Access Control:**

- Permissions are governed by system-wide rules, such as allowing access only during specific times of day or from certain locations.
- This often overlaps with RBAC or can operate alongside other models.

### # **Attribute-Based Access Control (ABAC):**

- Decisions are made based on attributes (user, resource, environment) and defined policies.
- ABAC allows for context-sensitive and highly granular access decisions.

### # **History-Based and Identity-Based Access Controls:**

- These models consider the user's previous activity or specific identity attributes for access decisions, sometimes used in specialized or high-security environments.

## **Types based on Medium**

### # **Physical Access Control:**

- Involves restricting entry to physical spaces (buildings, rooms, server cages) using locks, keycards, biometrics, and other barriers.

### # **Logical Access Control:**

- Governs access to digital resources, such as files, databases, applications, and networks - typically enforced with passwords, multi-factor authentication (MFA), access control lists (ACLs), and policies

## **Key Components**

- **Authentication:** Verifying the identity of a user, device, or application via credentials like passwords, tokens, or biometrics.
- **Authorization:** Determining what an authenticated user is allowed to access or do.
- **Access:** Granting or denying the requested action based on established policies.
- **Management:** Creating, updating, or revoking permissions and handling user profiles.
- **Auditing:** Monitoring access logs and policy enforcement to detect and correct weaknesses
- 
## **Methods and Technologies**

- **Access Control Lists (ACLs):** Specify which users or system processes are granted access to objects and what operations are allowed.
- **Group Policies:** Common in corporate networks (e.g., Microsoft Active Directory), these allow central management of permissions for groups of users or devices.
- **Credential Types:** Ranging from physical keys and PIN codes to smart cards and biometric data, depending on the level of security required.