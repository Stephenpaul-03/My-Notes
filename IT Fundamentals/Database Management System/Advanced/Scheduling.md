## **Definition**

- A **schedule** defines the order in which the operations of concurrent transactions are executed.
- The primary goal of scheduling is to **ensure correctness** and **maintain database consistency** when multiple transactions operate simultaneously.
- Schedules are crucial in the context of **concurrency control** and **transaction isolation**.

## **Types of Schedules**

### **Serial Schedule**

- A **serial schedule** is one where transactions are executed sequentially, with no overlap. That is, a transaction begins **only after** the previous one has **completely finished**.
- This approach guarantees correctness but lacks concurrency and can lead to poor system performance.
- There are two main types of serial schedules:
  - **Conflict Serializable**: A schedule is conflict serializable if it can be transformed into a serial schedule by swapping non-conflicting operations. Conflicts occur if:
    - The operations belong to different transactions.
    - They access the same data item.
    - At least one operation is a write.
  - **View Serializable**: A schedule is view serializable if it results in the same final state as a serial schedule, considering:
    - The same initial reads.
    - Reads reflecting the latest committed writes.
    - The same final writes.

  **Note:** View serializability is more general than conflict serializability, as it includes cases with **blind writes** (writes not based on a prior read), which conflict serializability cannot handle.

### **Non-Serial Schedule**

- A **non-serial schedule** allows interleaving of operations from multiple transactions. While it enables higher throughput, it introduces the risk of inconsistencies.
- These are classified based on their **recovery characteristics**:
  
  - **Recoverable Schedule**:
    - Ensures that a transaction commits only after any other transaction from which it has read data has also committed. This prevents scenarios where a transaction depends on uncommitted (and possibly invalid) data.

  - **Cascading Rollbacks (Cascading Schedules)**:
    - Occur when the failure of one transaction leads to a chain reaction of rollbacks in dependent transactions. These are undesirable due to their complexity and performance impact.

  - **Cascadeless Schedule**:
    - Prevents cascading rollbacks by ensuring that a transaction **only reads committed data**. Transactions must delay reading until the writer has committed, thus avoiding dependencies on uncommitted changes.

  - **Strict Schedule**:
    - The most restrictive and robust form. A transaction is allowed to read or write a data item **only after** the transaction that last wrote to it has **committed or aborted**. This prevents both cascading rollbacks and dirty reads, ensuring high data integrity.

  - **Non-Recoverable Schedule**:
    - A flawed schedule where a transaction commits after reading uncommitted data from another transaction. If the writing transaction aborts later, the committed transaction is left in an inconsistent state, violating atomicity and consistency.

## **Hierarchy of Schedules**

The types of schedules form a **nested hierarchy** in terms of strictness:

- **Strict Schedules** < **Cascadeless Schedules** < **Recoverable Schedules** < **Serializable Schedules**

At the top level, **serial schedules** inherently satisfy all constraints - strict, cascadeless, and recoverable - making them the safest but least performant in high-concurrency environments.