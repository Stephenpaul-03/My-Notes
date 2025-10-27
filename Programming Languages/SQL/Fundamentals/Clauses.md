
| **Clause**                | **Purpose**                                                          | **Notes**                                                                      |
| ------------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| `SELECT`                  | Specifies which columns to return                                    | Core of every query                                                            |
| `FROM`                    | Specifies the source table(s)                                        | Can include `JOIN`, aliases                                                    |
| `WHERE`                   | Filters rows before grouping/aggregation                             | Uses comparison/logical operators                                              |
| `GROUP BY`                | Groups rows to apply aggregate functions                             | Always comes **before** `HAVING`                                               |
| `HAVING`                  | Filters grouped data (aggregates)                                    | Think: `WHERE` but for groups                                                  |
| `ORDER BY`                | Sorts result set in ascending (`ASC`) or descending (`DESC`) order   | Can sort by column index too                                                   |
| `LIMIT` / `TOP` / `FETCH` | Limits number of rows returned                                       | DB-specific: `LIMIT` (MySQL/PG), `TOP` (SQL Server), `FETCH` (Oracle/Standard) |
| `JOIN` (and types)        | Combines rows from multiple tables based on related columns          | Includes `INNER`, `LEFT`, `RIGHT`, `FULL`, `CROSS`                             |
| `ON`                      | Specifies join condition for `JOIN`                                  | Required for all joins except `CROSS`                                          |
| `USING`                   | Alternative to `ON` if both tables share a column with the same name | Cleaner syntax, less flexible                                                  |
| `DISTINCT`                | Removes duplicate rows from results                                  | Applies to all selected columns                                                |
| `AS`                      | Renames columns or tables temporarily (aliasing)                     | Optional keyword — `SELECT name employee_name` works too                       |
| `WITH` (CTE)              | Defines temporary result sets to be reused in the main query         | Makes complex queries readable                                                 |
| `UNION` / `UNION ALL`     | Combines results of two `SELECT` queries                             | `UNION` removes duplicates; `UNION ALL` keeps 'em                              |
| `INTERSECT`               | Returns common rows from two `SELECT` queries                        | Not supported in MySQL                                                         |
| `EXCEPT` / `MINUS`        | Returns rows from first query not in second                          | `EXCEPT` (SQL Server, PG), `MINUS` (Oracle)                                    |
| `INTO`                    | Exports query result into new table                                  | `SELECT INTO new_table FROM old_table`                                         |
| `OFFSET`                  | Skips rows before returning results (used with `LIMIT`)              | For pagination                                                                 |
| `ALL`                     | Default when not using `DISTINCT`                                    | Rarely written explicitly                                                      |
| `EXISTS`                  | Checks if a subquery returns results                                 | Returns true/false                                                             |
| `IN`                      | Matches value in a list or subquery                                  | Like `= ANY(...)`                                                              |
| `BETWEEN`                 | Checks if value lies within a range                                  | Inclusive boundaries                                                           |
| `LIKE` / `ILIKE`          | Pattern matching (ILIKE is case-insensitive, PG only)                | `%` = wildcard                                                                 |
| `IS NULL` / `IS NOT NULL` | Checks for null values                                               | `= NULL` doesn't work — use `IS NULL`                                          |
| `CASE`                    | Conditional logic (if/else) inside queries                           | Acts like a switch statement                                                   |
