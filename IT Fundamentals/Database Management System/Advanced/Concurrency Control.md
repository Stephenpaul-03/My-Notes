## **Definition**

- Concurrency control ensures the **correctness, consistency, and isolation** of concurrent transactions in a database system, preventing data anomalies such as **dirty reads, lost updates, and inconsistent reads**.

## **Key Terminologies**

- **Concurrent Execution**: Simultaneous execution of multiple transactions on the same database system, maximizing resource utilization and throughput while preserving consistency.
- **Dirty Reads**: Occur when a transaction reads data written by another uncommitted transaction. If the other transaction rolls back, the read data becomes invalid, leading to inconsistency.
- **Lost Updates**: Happen when two or more transactions read the same data and update it based on the read value, but one update overwrites the other, resulting in the loss of data.
- **Inconsistent Reads (Non-repeatable Reads)**: Arise when a transaction reads the same data item more than once and finds different values due to updates from other concurrent transactions.
- **Phantom Reads**: A specific type of inconsistency where a transaction reads a set of rows that satisfy a condition, but a subsequent read within the same transaction returns a different set due to inserts/deletes by other transactions.

## **ACID Properties**

1. **Atomicity** – *"All or Nothing"*
    - Guarantees the indivisibility of a transaction. If any part fails, the entire transaction is rolled back.
2. **Consistency** – *"Maintaining Valid Data States"*
    - Ensures that a transaction transforms the database from one valid state to another, maintaining all defined rules and constraints.
3. **Isolation** – *"Concurrent Transactions Don't Interfere"*
    - Ensures that concurrently executing transactions produce the same results as if they were executed serially.
4. **Durability** – *"Persisting Changes"*
    - Once a transaction commits, its changes are permanent and survive system failures.

## **Lock Manager**

- **Lock Manager**: A centralized system component that controls access to data items by granting or denying locks based on concurrent transaction requirements.
- **Lock Table**: A data structure used by the lock manager to track granted, requested, and waiting locks on each data item.

## **Concurrency Control Protocols**

### **# **Lock-Based Protocols****

1. **Simplistic Lock Protocol**:
    - A transaction locks a data item before using it and releases it after use, without enforcing ordering or structured locking.
2. **Pre-claiming Protocol**:
    - Requires a transaction to declare all locks it will need before it begins execution; if all can be granted, it proceess. Otherwise, it waits.
3. **Two-Phase Locking (2PL)**:
    - Divides the transaction lifecycle into two phases:
        - **Growing Phase**: Only acquiring locks.
        - **Shrinking Phase**: Only releasing locks.
    - Ensures serializability.
4. **Strict Two-Phase Locking (Strict 2PL)**:
    - A stronger form of 2PL where all **exclusive locks** are held until the transaction commits or aborts.
    - Guarantees **cascadeless recoverability**.

### **# **Timestamp-Based Protocols****

1. **Basic Timestamp Ordering**:
    - Assigns a unique timestamp to each transaction and orders operations based on timestamps to avoid conflicts.
    - Ensures serializability by aborting or delaying conflicting operations.
2. **Strict Timestamp Ordering**:
    - Extends the basic protocol to delay both read and write operations until conflicting older transactions are committed.
3. **Thomas’s Write Rule**:
    - An optimization where obsolete writes (based on timestamp comparisons) are ignored rather than aborting the transaction, improving concurrency.

## **# **Graph-Based Protocols****

- Use **precedence graphs** to avoid circular wait conditions that cause deadlocks.
1. **Tree Protocol**:
    - Restricts the locking order to a tree structure:
        - First lock can be on any data item.
        - Subsequent locks must be on children of the previously locked item.
        - Once a lock is released, it cannot be re-acquired.
    - Prevents deadlocks and ensures serializability.

## **Transaction Schedules**

Schedules define the order in which operations of concurrent transactions are executed.

1. **Recoverable Schedules**
    - A transaction commits only after all transactions it read from have committed.
    - Prevents **cascading aborts** by ensuring dependencies are resolved safely.
    - Required for **reliable recovery** in failure scenarios.
2. **Cascadeless Schedules**
    - Transactions can read only committed data, thereby avoiding the possibility of cascading rollbacks.
    - Enforced by **Strict 2PL** and **Timestamp Ordering Protocols**.
3. **Strict Schedules**
    - A special class of cascadeless schedules where **no transaction can read or write** a data item until the last transaction that wrote it has committed.
    - Simplifies recovery and logging.
