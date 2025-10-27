## Definition

- A Recursive CTE is a CTE that **references itself**.
- It’s made up of:
	1. **Anchor member** → base query that starts the recursion.
	2. **Recursive member** → the query that references the CTE and keeps looping until a stop condition.
	3. A **termination condition** → built into the recursive member’s `WHERE` clause.
## Syntax

```sql
WITH RECURSIVE cte_name AS (
    -- Anchor member
    SELECT ...
    FROM ...
    WHERE ...

    UNION ALL

    -- Recursive member
    SELECT ...
    FROM cte_name
    JOIN ...
    WHERE ...
)
SELECT * FROM cte_name;

--- UNION ALL is required (not just UNION), because duplicates are required since 
--- de-duped will slow it down. ----
```
## Real-World Example

#### Consider an `employees` table like this:

| id  | name  | manager_id |
| --- | ----- | ---------- |
| 1   | Alice | NULL       |
| 2   | Bob   | 1          |
| 3   | Carol | 2          |
| 4   | Dave  | 2          |
| 5   | Erin  | 3          |

```sql
--- to get the entire **reporting hierarchy** under Alice (id = 1). ---

WITH RECURSIVE employee_hierarchy AS (
    -- Anchor: Alice is the top boss
    SELECT id, name, manager_id, 1 AS level
    FROM employees
    WHERE id = 1

    UNION ALL

    -- Recursive: find who reports to who
    SELECT e.id, e.name, e.manager_id, eh.level + 1
    FROM employees e
    JOIN employee_hierarchy eh ON e.manager_id = eh.id
)
SELECT * FROM employee_hierarchy;

```
#### **Result:**

| id  | name  | manager_id | level |
| --- | ----- | ---------- | ----- |
| 1   | Alice | NULL       | 1     |
| 2   | Bob   | 1          | 2     |
| 3   | Carol | 2          | 3     |
| 4   | Dave  | 2          | 3     |
| 5   | Erin  | 3          | 4     |
## Use Cases

- Org charts
- Folder hierarchies
- Parent-child trees
- Category/sub-category systems
- Traversing linked lists or graphs
- Calculating running totals with conditions
- Puzzle-solving
## Cautions

- **Infinite loops** → Always make sure your recursion has a proper `WHERE` condition to break.
- **Performance** → recursive joins will affect performance
- **Not all DBs support it** → `MySQL 8+`, `Postgres`, `SQL Server (2012+)`, and `Oracle` all do.