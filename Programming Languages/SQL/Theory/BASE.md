**BASE** is a design philosophy for database systems - especially distributed, non-relational (NoSQL) databases -that contrasts the strict guarantees of the ACID properties used in traditional relational databases.

1. **Basically Available:**
    - The system promises availability, meaning each request receives a response (success or failure), but without a guarantee that it contains the most recent data.
2. **Soft State:**
    - The state of the system may change over time, even without new input, because data may be temporarily inconsistent across different nodes.
3. **Eventually Consistent:**
    - The system ensures that, given enough time and in the absence of new updates, all replicas in the distributed environment will converge to the same state.

## BASE vs. ACID

| Aspect | ACID | BASE |
| --- | --- | --- |
| Consistency | Strict, always consistent | Eventual, allows temporary inconsistency |
| Availability | May be sacrificed for consistency | Prioritizes availability |
| State | Hard state, stable immediately | Soft state, changes over time |
| Approach | Transactions must pass all tests | Accepts partial success and delayed convergence |
| Typical Systems | Relational (SQL) | Distributed, NoSQL |

## Reasons

- **Scalability:** BASE is useful for applications that need to scale horizontally across many servers or data centers.
- **Flexibility:** Works well in environments where data is read and written from many locations, such as social networks, real-time analytics, or global e-commerce.
- **Performance:** Reduces the need for global coordination, so reads and writes can be fast and always responded to—even during network partitions.