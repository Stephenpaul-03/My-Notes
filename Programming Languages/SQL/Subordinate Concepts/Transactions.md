## Definition

- A **transaction** is a **single unit of work** that consists of one or more SQL operations, executed as a **whole**. Either *all* the operations in the transaction succeed, or **none** do.
- Think of it like a group project - either everyone turns in their part, or the whole thing flops.

## SQL Transaction Control Commands

| Command | What it Does |
| --- | --- |
| `BEGIN TRANSACTION` or `START TRANSACTION` | Starts a transaction block. |
| `COMMIT` | Permanently saves all changes made in the transaction. |
| `ROLLBACK` | Undoes all changes made in the current transaction. |
| `SAVEPOINT` | Marks a point within a transaction you can roll back to. |
| `RELEASE SAVEPOINT` | Removes a savepoint. |
| `ROLLBACK TO SAVEPOINT` | Rolls back part of a transaction up to a specific savepoint. |
| `SET TRANSACTION` | Configures isolation level or access mode. |
## **Examples**

```sql
--- **Basic Transaction ---**
BEGIN TRANSACTION;

UPDATE accounts SET balance = balance - 1000 WHERE account_id = 1;
UPDATE accounts SET balance = balance + 1000 WHERE account_id = 2;

COMMIT;

--- **SavePoints** ---
BEGIN;

UPDATE users SET email = 'user@site.com' WHERE id = 1;
SAVEPOINT after_email_update;

UPDATE users SET username = 'new_name' WHERE id = 1;

ROLLBACK TO after_email_update;

COMMIT;

```
## Isolation Levels (SQL Standard)

| Level                | Description                                       | Dirty Read | Non-repeatable Read | Phantom Read |
| -------------------- | ------------------------------------------------- | ---------- | ------------------- | ------------ |
| **READ UNCOMMITTED** | No isolation at all. Danger zone.                 | Yes        | Yes                 | Yes          |
| **READ COMMITTED**   | Only sees committed changes. Default in many DBs. | No         | Yes                 | Yes          |
| **REPEATABLE READ**  | Prevents changes to rows during the transaction.  | No         | No                  | Yes          |
| **SERIALIZABLE**     | Highest level. Locks rows & range.                | No         | No                  | No           |

| Read Issue              | When it Happens              | Blocked By Isolation Level        |
| ----------------------- | ---------------------------- | --------------------------------- |
| **Dirty Read**          | Read uncommitted data        | `READ COMMITTED` or higher        |
| **Non-Repeatable Read** | Read same row, value changes | `REPEATABLE READ`, `SERIALIZABLE` |
| **Phantom Read**        | Same query returns diff rows | Only blocked by `SERIALIZABLE`    |
## When to Use
- **Money moves** — bank transfers, e-commerce payments, etc.
- **Multi-step updates** that must succeed/fail as a unit.
- **Data integrity** is crucial and cannot be compromised.
- **Batch processing** or importing a ton of records.
## When not to Use
- For **read-only** queries.
- In **extremely high throughput systems** (transactions add overhead).
- When **eventual consistency** is acceptable (like caching or analytics).
## Analogy
- A transaction is like shopping at a store with a cart:
- You grab items (queries), change your mind (rollback/savepoint), and only when you're done and happy, you go pay (commit).
- If you rage quit mid-trip, you leave the cart and bounce (rollback). No damage done.