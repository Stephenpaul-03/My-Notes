## Definition 

A CTE is a temporary result set you define using the WITH clause, which exists only during the execution of the query.

Think of it like creating a **named subquery** that’s easier to read, reuse, and stack.
## Syntax

```sql
WITH cte_name AS (
    SELECT column1, column2
    FROM table_name
    WHERE condition
)
SELECT *
FROM cte_name
WHERE another_condition;
```
## Reasons

- Makes complex queries readable
- Breaks down logic into parts
- Can reference the CTE multiple times
- Allows **recursive querying** (more on that later)
- Replaces messy subqueries and derived tables
- Can be nested or chained (`WITH ... , ...`)

## Examples

```sql
--- Simple CTE ---
WITH avg_salary AS (
    SELECT AVG(salary) AS avg_sal FROM employees
)
SELECT e.name, e.salary
FROM employees e, avg_salary a
WHERE e.salary > a.avg_sal;

--- Multiple CTEs ---

WITH dept_salaries AS (
    SELECT department_id, SUM(salary) AS total_salary
    FROM employees
    GROUP BY department_id
),
high_salary_depts AS (
    SELECT department_id
    FROM dept_salaries
    WHERE total_salary > 500000
)
SELECT *
FROM employees
WHERE department_id IN (SELECT department_id FROM high_salary_depts);
```

## Limitations

- Can’t reuse a CTE **across multiple queries** , it dies with the query.
- Some databases don’t support CTEs (especially older ones).
- If nested too deep, readability dies again.

## Difference between Inline View ,Subquery and CTE

| Feature     | Inline View | Subquery | CTE  |
| ----------- | ----------- | -------- | ---- |
| Reusable    | No          | No       | Yes  |
| Readability | Low         | Mid      | High |
| Recursive?  | No          | No       | Yes  |
| Temporary   | Yes         | Yes      | Yes  |
