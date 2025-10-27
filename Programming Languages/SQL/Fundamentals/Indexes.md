## Definition

- An **index** is a data structure (usually a B-tree) that helps **speed up searches** on a table.
- Without indexes - SQL reads row-by-row, front to back.
- With indexes - SQL skips straight to the required data.
- It’s like a book’s table of contents, no need to read every word to find Chapter 8, jump to it.
## Basic Syntax

```sql
CREATE INDEX index_name
ON table_name (column1, column2, ...);
--- EXAMPLE ---
CREATE INDEX idx_lastname
ON employees (last_name);
```
## Types of Indexes
| Type                         | Use Case                                        |
| ---------------------------- | ----------------------------------------------- |
| **Single-column**            | Index on one column                             |
| **Composite / Multi-column** | Index on combo of columns                       |
| **Unique**                   | Prevents duplicates + speeds up search          |
| **Full-text**                | For wild search (like Google-style text search) |
| **Clustered (only one)**     | Sorts the **actual** table by that column       |
| **Non-clustered (default)**  | Just a pointer system; doesn’t affect row order |
| **Partial / Filtered**       | Index only rows matching a condition            |
| **Function-based**           | Index on an expression or function result       |
### Single-Column Index

```sql
CREATE INDEX idx_username
ON users (username);
```

- Use when filtering/searching **heavily** on a specific column.
### Composite Index

```sql
CREATE INDEX idx_user_email
ON users (last_name, first_name);
```

- Used when your queries filter or sort by **both** columns together.
- Order matters!
- Index on `(last_name, first_name)` ≠ `(first_name, last_name)` 
### Unique Index

```sql
CREATE UNIQUE INDEX idx_unique_email
ON users (email);
```

This not only speeds up search, but **enforces uniqueness** (like a constraint).
### Clustered Index (SQL Server, MySQL with InnoDB)

```sql
-- Usually auto-created on PRIMARY KEY
CREATE CLUSTERED INDEX idx_id
ON employees (id);
```
- Only **one** per table.
- Physically reorders table data based on indexed column.
### Filtered (Partial) Index

```sql
CREATE INDEX idx_active_users
ON users (status)
WHERE status = 'active';
```

- Only indexes rows that match the filter.
- **Efficient** for skewed data (e.g., 90% inactive, 10% active).
### Function-based Index (PostgreSQL, Oracle)

```sql
CREATE INDEX idx_lower_email
ON users (LOWER(email));
```

- Perfect when often run `WHERE LOWER(email) = 'x@y.com'`.
## Indexes Used at

- `WHERE` clauses
- `JOIN` conditions
- `ORDER BY`
- `GROUP BY`
- Searching partial text (full-text indexes)
- Aggregate filtering (`HAVING`) sometimes
## Indexes Ignored at

- On small tables (SQL just scans it)
- If the query uses functions *on the column* (unless a function-based index is used)
- If the condition is too broad (e.g., `WHERE 1=1`)
- When the wrong column order is used in composite index
## Managing Indexes

```sql
--- Drop an Index ---
DROP INDEX index_name;

--- Rename Index ---
--(PostgreSQL example)--
ALTER INDEX old_name RENAME TO new_name;
```
## Disadvantages
| Drawback                            | Explanation                                                |
| ----------------------------------- | ---------------------------------------------------------- |
| Slower `INSERT`, `UPDATE`, `DELETE` | Index has to be updated                                    |
| Takes up space                      | More indexes = more storage                                |
| Too many indexes = confusion        | SQL may pick a less optimal one                            |
| Misused composite indexes           | If you use only the **second column**, it might be useless |
