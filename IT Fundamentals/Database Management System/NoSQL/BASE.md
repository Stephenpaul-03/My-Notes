## **BASE**

**BASE** is a consistency approach designed for distributed databases, most commonly found in NoSQL and large-scale web applications. It stands for:

- **Basically Available:**
    - The system guarantees availability, meaning it almost always responds to requests, even if not every request returns the most up-to-date information.
    - The goal is to keep the service accessible even during failures.
- **Soft State:**
    - The state of the system may change over time, even without new input.
    - This is because data propagation across distributed nodes is asynchronous, allowing the system's state to temporarily be inconsistent as updates are applied.
- **Eventually Consistent:**
    - Rather than enforcing immediate, strong consistency, BASE systems guarantee that given enough time (and no new updates), all copies of the data will synchronize to the same value.
    - In the interim, temporary inconsistencies are permitted.

## **BASE vs. ACID**

|  | BASE | ACID |
| --- | --- | --- |
| **Goal** | High availability and scalability | Strong consistency and reliability |
| **Approach** | Accepts temporary inconsistency; ensures data becomes consistent eventually | Enforces strict transactional integrity and state |
| **Consistency** | Eventual, not immediate | Immediate (after each transaction) |
| **Use Case** | Large-scale, distributed systems (e.g., social media, e-commerce) | Traditional RDBMS, financial systems |

## **Key Principles of BASE**

- **High Availability:**
    - BASE systems are built for applications that require responding to user queries under nearly all conditions.
- **Partition Tolerance:**
    - They operate effectively even when some parts of the system become unreachable.
- **Relaxed Consistency:**
    - Sacrifices immediate consistency for uptime and partition tolerance, under the philosophy that *eventual* correctness is often “good enough” for large-scale applications.

## **Example Scenario**

A social media news feed may use BASE: 

- when a user posts a new status, some friends see it instantly while others may see it with a slight delay.
- The priority is that no user faces an outage, even if they occasionally see slightly out-of-date data.

## **When to Use BASE**

- Systems needing **continuous availability** and **fault tolerance**.
- Applications where **temporary inconsistency** is acceptable for users.
- Scenarios requiring **horizontal scalability** to handle massive traffic.