## Temporary Tables

- Temporary Tables are like normal tables, **except they self-destruct** when your session ends (or you drop them). 
- used to deal with **intermediate data** that isn’t needed to persist in the database forever.
### Syntax

```sql
CREATE TEMPORARY TABLE temp_users (
    id INT,
    name VARCHAR(50)
);

INSERT INTO temp_users VALUES (1, 'Alice'), (2, 'Bob');

SELECT * FROM temp_users;

--- Global Temporary Table ---

CREATE TABLE ##global_temp (
    id INT,
    data NVARCHAR(100)
);

--- Prefixed with `##`
--- Visible across all sessions until the last session using it ends

```

TEMPORARY tables vanish automatically when your session/connection ends. 
### When to Use

- When you're processing chunks of data in **multi-step operations**
- When working with **complex joins** or **aggregations**
- When storing results of heavy subqueries
- When avoiding table pollution in prod DB
## Table Variables

- Table Variables are variables that **act like tables**, but they exist only within the **scope of a batch, stored procedure, or function**.
### Syntax

```sql
DECLARE @tempTable TABLE (
    id INT,
    name VARCHAR(50)
);

INSERT INTO @tempTable VALUES (1, 'Charlie'), (2, 'Dylan');

SELECT * FROM @tempTable;

```
## Overview

| Feature | Temp Table (`#`) | Table Variable (`@`) |
| --- | --- | --- |
| Scope | Session | Batch/proc/function |
| Indexing Supported? | Yes | Limited |
| Transactions Supported? | Yes | No |
| Performance (small sets) | Slower | Faster |
| Performance (big data) | Faster | Slower |
| Can be altered after? | Yes | No |
| Visibility | Multiple queries | Single batch only |
## When to Use What?

- Use `@tableVariable` if:
    - You’re working with small datasets
    - Inside stored procedures/functions
    - You don’t need indexing or constraints
- Use `#tempTable` if:
    - You’re joining multiple tables
    - You need indexes or constraints
    - You’re working with large or unpredictable data
## Notes

- Table Variables **can’t be rolled back** in a transaction
- They **don’t update statistics**, so SQL Server might make bad query plans
- You **can’t add constraints or indexes** after declaring one