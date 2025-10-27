## Definition

- Query Execution Order is the order in which a SQL Query is executed under the hood.
## Clauses Precedence

| Execution Step | Clause                 | Description                               |
| -------------- | ---------------------- | ----------------------------------------- |
| 1              | `FROM`                 | Identifies the source table(s)            |
| 2              | `JOIN` + `ON`          | Merges tables and applies join conditions |
| 3              | `WHERE`                | Filters rows **before grouping**          |
| 4              | `GROUP BY`             | Groups filtered rows                      |
| 5              | `WITH ROLLUP` / `CUBE` | Performs advanced grouping (optional)     |
| 6              | `HAVING`               | Filters **after grouping/aggregation**    |
| 7              | `SELECT`               | Chooses columns/expressions to return     |
| 8              | `DISTINCT`             | Removes duplicate rows (after SELECT)     |
| 9              | `ORDER BY`             | Sorts the result set                      |
| 10             | `LIMIT` / `OFFSET`     | Trims down the final result set           |
## Commands Precedence

| Precedence Rank | Command            | Category          | What It Does                                          |
| --------------- | ------------------ | ----------------- | ----------------------------------------------------- |
| 1               | `SELECT`           | DQL (Query)       | Retrieve data from tables (the most used ever)        |
| 2               | `INSERT`           | DML (Manipulate)  | Add new rows to a table                               |
| 3               | `UPDATE`           | DML               | Modify existing data                                  |
| 4               | `DELETE`           | DML               | Remove rows from a table                              |
| 5               | `CREATE`           | DDL (Define)      | Make new tables, views, procedures, indexes, etc.     |
| 6               | `ALTER`            | DDL               | Change structure of existing tables, columns, etc.    |
| 7               | `DROP`             | DDL               | Delete entire table, view, index, or procedure        |
| 8               | `TRUNCATE`         | DDL               | Wipe all rows from a table (faster than `DELETE`)     |
| 9               | `RENAME`           | DDL               | Rename tables, columns, etc.                          |
| 10              | `GRANT` / `REVOKE` | DCL (Control)     | Manage user permissions                               |
| 11              | `COMMIT`           | TCL (Transaction) | Save transaction permanently                          |
| 12              | `ROLLBACK`         | TCL               | Undo transaction if something goes wrong              |
| 13              | `SAVEPOINT`        | TCL               | Set a checkpoint inside a transaction                 |
| 14              | `CALL`             | Procedural        | Execute a stored procedure                            |
| 15              | `EXPLAIN`          | Diagnostic        | Show how a query will execute (performance/debugging) |
## Connection

| Command  | Valid Clauses It Supports                                                                         |
| -------- | ------------------------------------------------------------------------------------------------- |
| `SELECT` | `FROM`, `WHERE`, `GROUP BY`, `HAVING`, `ORDER BY`, `LIMIT`, `JOIN`, `DISTINCT`, `UNION`, `OFFSET` |
| `INSERT` | `VALUES`, `SELECT`, `ON DUPLICATE KEY`                                                            |
| `UPDATE` | `SET`, `WHERE`, `ORDER BY`, `LIMIT`, `JOIN`                                                       |
| `DELETE` | `WHERE`, `ORDER BY`, `LIMIT`, `USING`                                                             |
