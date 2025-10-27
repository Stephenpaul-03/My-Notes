## Definition

`MERGE` allows to perform **INSERT**, **UPDATE**, and **DELETE** in a single SQL command by comparing a **source** table with a **target** table.
## Syntax

```sql
MERGE target_table AS target
USING source_table AS source
ON target.id = source.id

WHEN MATCHED THEN
    UPDATE SET target.name = source.name

WHEN NOT MATCHED THEN
    INSERT (id, name) VALUES (source.id, source.name)

WHEN NOT MATCHED BY SOURCE THEN
    DELETE;

```

## Real-World Example

given a live table `Employees` and receive an updated feed in `UpdatedEmployees`.

```sql
MERGE Employees AS emp
USING UpdatedEmployees AS upd
ON emp.emp_id = upd.emp_id

WHEN MATCHED THEN
    UPDATE SET
        emp.name = upd.name,
        emp.salary = upd.salary

WHEN NOT MATCHED THEN
    INSERT (emp_id, name, salary)
    VALUES (upd.emp_id, upd.name, upd.salary)

WHEN NOT MATCHED BY SOURCE THEN
    DELETE;

```

## What each clause means:

| Clause                       | What it does                                            |
| ---------------------------- | ------------------------------------------------------- |
| `WHEN MATCHED`               | Update existing row in target that matches source       |
| `WHEN NOT MATCHED`           | Insert new row from source that doesn’t exist in target |
| `WHEN NOT MATCHED BY SOURCE` | Delete row in target that doesn't exist in source       |

## Caution

- `MERGE` statements can be **dangerous** if not handled carefully — esp. with `DELETE`.
- Always test on a sandbox before letting it near production.
- Most common in **SQL Server**, **Oracle** and **PostgreSQL** (via `INSERT ... ON CONFLICT`, similar behavior).
- **MySQL** doesn’t support native `MERGE`, but you can simulate with `INSERT ... ON DUPLICATE KEY UPDATE`.
## Analogy Time

<aside>

Think of `MERGE` like syncing your phone contacts:

- If the contact is already there → update their info.
- If they’re new → add them.
- If they’re no longer in your synced list → delete them.
</aside>