## **ACID**

**ACID** is a foundational set of properties that ensure **reliable processing of transactions in database management systems**. The acronym stands for:

- **Atomicity**:
    - Guarantees that *all operations within a transaction are treated as a single unit -* either all succeed or none are applied.
    - If part of a transaction fails, the entire transaction is rolled back, preserving data integrity.
- **Consistency**:
    - Ensures that a transaction brings the database from one valid state to another, strictly adhering to predefined rules, constraints, and triggers.
    - This means only valid data (as defined by integrity constraints) is ever written, maintaining correctness at all times
- **Isolation**:
    - Makes sure that *concurrent transactions do not interfere with each other*.
    - Each transaction’s intermediate state is invisible to others, and the final result would be identical whether transactions were executed simultaneously or sequentially
- **Durability**:
    - Guarantees that once a transaction is committed, its changes are *permanently saved*, even in the event of power loss or system failure.
    - Data written by committed transactions will persist.

## **Overview Table**

| Property | Description |
| --- | --- |
| Atomicity | All-or-nothing execution; if any step fails, rollback entire transaction |
| Consistency | Only valid data written; preserves database rules and constraints |
| Isolation | Concurrent transactions do not affect each other; intermediate states are not visible to others |
| Durability | Committed data survives crashes and is persistently stored |