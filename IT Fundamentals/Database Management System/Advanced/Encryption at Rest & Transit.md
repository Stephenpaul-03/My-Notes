## **Encryption in Rest**

### **# What’s getting encrypted?**

- **Files**: logs, configs, reports
- **Databases**: table data, indexes, temp files
- **Object storage**: images, blobs, backups
- **Virtual machines/disks**: EC2, EBS, etc.

### **# How is it encrypted?**

- Usually with **AES (Advanced Encryption Standard)** : AES-256
- Encryption is done **by the OS**, the **DBMS**, or **storage layer** (like a cloud provider).

### **# Methods:**

1. **Full Disk Encryption (FDE)**
    - Encrypts entire storage — OS, apps, files.
    - Tools: BitLocker (Windows), LUKS (Linux), FileVault (macOS).
2. **Database-Level Encryption**
    - Encrypts DB files/tables directly.
    - Tools: TDE (Transparent Data Encryption) in SQL Server, Oracle, MySQL, PostgreSQL.
3. **Field-Level Encryption**
    - Specific columns like passwords or card numbers.
    - You do it manually or via functions (e.g., `pgcrypto` for PostgreSQL).

### **# Key Handling**

- **KMS (Key Management System)** is a MUST.
- Tools: AWS KMS, Azure Key Vault, HashiCorp Vault.
- Use **envelope encryption** — wrap the data key with a master key.
## **Encryption in Transit**

### **# What’s Getting Encrypted ?**

- API requests
- Database connections
- Files between client/server
- Microservices chitchat

### **# How’s it encrypted?**

- Using **TLS (Transport Layer Security)** — aka the upgraded version of SSL.
- Encrypts at **Layer 4 (TCP)** or **Layer 7 (App level)**.

### **# Common Use Cases**

1. **HTTPS for web apps**
    - Use TLS certs. Enforce `HTTPS` with HSTS.
    - Use TLS 1.2 or 1.3 — don’t touch SSL 3.0 or TLS 1.0/1.1. They're fossils.
2. **Database connections**
    - Set up TLS between app ↔ DB
    - Example: PostgreSQL with `sslmode=require`
    
    ```bash
    psql "sslmode=require host=mydb.example.com dbname=mydb user=admin"
    
    ```
    
3. **Messaging Queues & APIs**
    - Use mutual TLS (mTLS) for service-to-service.
    - Encrypt everything over gRPC, REST, or GraphQL APIs.
4. **SSH, SCP, SFTP**
    - Don’t use unencrypted FTP or telnet. That's hacker bait.

## **# What happens without encryption in Transit ?**

- Anyone on the same network (like a public Wi-Fi or rogue employee) can **sniff your traffic** and read passwords, tokens, personal data.
- At rest? Disk gets cloned - boom, entire DB is theirs.

## **TL;DR**

| Layer | Tech Used | Typical Algorithms |
| --- | --- | --- |
| At Rest | AES, TDE, FDE | AES-128/192/256 |
| In Transit | TLS 1.2/1.3, SSH | RSA, ECDSA, AES-GCM |
| Key Management | KMS, HSM, Vault | Envelope encryption |
