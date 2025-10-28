## **Access Control**

Access Control is decides **who gets in**, **what they can see**, and **what they can do** with the data. Think of it as a way to **protect the database** from unauthorized snooping, data leaks, or chaos.
## **# Reasons**

- **Security**: Keeps sensitive stuff safe.
- **Privacy**: Users only see what they’re supposed to.
- **Integrity**: Prevents unauthorized manipulation of data.
- **Accountability**: Tracks who did what.
## **# Types of Access Control**

1. **Discretionary Access Control (DAC)**
    - Owner of the data decides who gets access.
    - Uses **Access Control Lists (ACLs)**.
    - Example: User A owns a table and gives SELECT permission to User B.
2. **Mandatory Access Control (MAC)**
    - Super strict. Based on security levels (like Top Secret, Confidential, etc.).
    - Users and data are tagged with labels, and the system enforces rules.
    - You don’t decide access — policies do.
3. **Role-Based Access Control (RBAC)**
    - Assign permissions to **roles**, and users get roles.
    - Example: "Admin" can do everything, "Clerk" can only read customer data.
    - Super scalable for big systems.
4. **Attribute-Based Access Control (ABAC)**
    - Next-gen stuff. Access depends on user **attributes** (like location, department, time of day).
    - Way more flexible but complex.
## **# Common Permissions in DBMS**

- **SELECT** – Read data
- **INSERT** – Add data
- **UPDATE** – Modify data
- **DELETE** – Remove data
- **EXECUTE** – Run stored procedures
- **GRANT/REVOKE** – Give or take back permissions
