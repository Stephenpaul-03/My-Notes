## **Recoverability**

- **Recoverability** is a fundamental property of a Database Management System (DBMS) that ensures data integrity and consistency following system failures. It guarantees that:
  - **Committed transactions** have their effects permanently recorded.
  - **Uncommitted transactions** are fully rolled back during recovery.
## **Levels of Recoverability**

1. **No-Undo Logging**
    - Ensures durability of committed transactions but lacks mechanisms to reverse changes made by uncommitted ones, risking inconsistency in the presence of failures.

2. **Undo Logging**
    - Supports rollback of uncommitted transactions to maintain consistency. However, it may discard committed updates that depend on failed transactions.

3. **Redo Logging**
    - Ensures durability by reapplying changes from committed transactions. However, it does not support undo operations, making it inadequate for handling failures involving uncommitted transactions.

4. **Undo-Redo Logging**
    - Provides full recoverability by supporting both undo and redo operations. This ensures a consistent state is restored regardless of transaction commit status at the time of failure.

## **Recoverability of Schedules**

A **schedule** defines the execution order of interleaved transactions. Recoverability ensures that transaction dependencies do not lead to inconsistencies.

- **Recoverable Schedule**
    - A schedule where a transaction commits only after all transactions it depends on have also committed. This prevents inconsistencies arising from premature commits.
  
- **Irrecoverable Schedule**
    - Occurs when a transaction commits after reading uncommitted data from another transaction, and the latter fails. This results in an inconsistent state that cannot be corrected.

- **Recoverable with Cascading Rollback**
    - A recoverable schedule where the failure of one transaction necessitates rollback of other dependent transactions. Although the database remains consistent, the rollback chain increases system overhead.

- **Cascadeless Recoverable Schedule**
    - The most robust form of recoverability where transactions do not read uncommitted data from others. This eliminates cascading rollbacks and ensures clean, isolated transaction execution.

## **Types of Recovery Techniques**

Recovery techniques in DBMS are designed to manage failures and maintain data integrity. These include:

- **Rollback / Undo Recovery**
    - Rollback operates on the principle of reversing the effects of transactions that have not completed successfully.
    - If a transaction fails before committing, all of its changes are rolled back using the transaction log, which maintains a detailed record of all operations.
    - The system restores the database to the last known consistent state prior to the transaction’s execution.

- **Commit / Redo Recovery**
    - The commit/redo technique re-applies the operations of successfully completed (committed) transactions following a failure.
    - The system scans the transaction log and reapplies the changes recorded, ensuring that no committed updates are lost.
    - This process brings the database to its most recent consistent state by persisting all changes that were committed before the crash.

- **Checkpoint Recovery**
    - **Checkpointing** involves saving the state of the database at regular intervals.
    - At each checkpoint, the system ensures that all transactions prior to the checkpoint have either been committed or aborted.
    - This allows the recovery process to ignore transactions prior to the checkpoint, significantly reducing recovery time and overhead.
    - The checkpoint data is stored in non-volatile memory to survive system failures.

## **Recovery Mechanisms**

- **Deferred Update (No-Undo/Redo Algorithm)**
    - Updates are deferred until the transaction reaches its commit point.
    - All changes are first written to a local workspace. If the transaction fails before committing, there is nothing to undo.
    - Upon successful commit, the changes are written to the database, and redo may be required.
        - **Recovery Requirement**: Redo only
        - **Advantages**: No need for undo operations; simplifies recovery.

- **Immediate Update (Undo/Redo Algorithm)**
    - Database pages may be updated before a transaction commits, but changes are logged beforehand.
    - If a transaction fails, its changes must be undone. If a failure occurs after commit, changes must be redone.
        - **Recovery Requirement**: Both undo and redo
        - **Advantages**: Faster responsiveness; supports complex operations.

- **Shadow Paging**
    - Shadow paging ensures atomicity and durability.
    - It uses two page directories—**current** and **shadow**.
    - All changes are written to a new page. Once a transaction commits, the current directory is updated to reference the new pages.
    - This technique avoids the need for logging.
        - **Advantages**: No need for log-based undo/redo.
        - **Limitations**: Complex to manage and scale for large systems.

- **Buffering and Caching**
    - DBMS maintains a cache in memory to hold disk pages.
    - Changes are made in memory buffers before being flushed to disk.
    - A **dirty bit** flags modified buffers.
    - This mechanism supports delayed writes and optimizes I/O operations but adds complexity to recovery.

- **Backward Recovery (Undo)**
    - Also known as **rollback**, this method reverts the database to a previous consistent state by undoing the effects of incomplete or failed transactions.
    - It is useful when no recent backup is available and the focus is on reversing incorrect modifications.

- **Forward Recovery (Redo)**
    - Also known as **roll forward**, this technique reapplies valid transactions using logs or saved data to bring the database forward to the current consistent state.
    - It ensures recovery from backups and supports point-in-time recovery.

## **Backup Mechanisms**

- **Full Database Backup**
    - Captures the entire database, including all data and metadata. It serves as a foundational recovery snapshot and is typically scheduled at regular intervals.

- **Differential Backup**
    - Stores only data changes that have occurred since the last full backup. To restore, both the last full backup and the most recent differential backup are needed.

- **Transaction Log Backup**
    - Captures all transaction log entries, enabling recovery to a specific point in time. It ensures that even if the main database files are lost, committed transactions can be restored.
