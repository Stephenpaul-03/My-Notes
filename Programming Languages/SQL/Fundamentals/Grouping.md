## Definition

- `GROUP BY` is SQL instead of dealing with every row individually, squish rows into groups based on one or more columns, then does queries on those groups.
## Basic Syntax:

```sql
SELECT column1, AGG_FUNC(column2)
FROM table_name
GROUP BY column1;
```

**must** include all non-aggregated columns from `SELECT` in your `GROUP BY` 
## Common Aggregation Functions

| Function  | What It Does    | Example                     |
| --------- | --------------- | --------------------------- |
| `COUNT()` | Counts rows     | `COUNT(*)`, `COUNT(column)` |
| `SUM()`   | Adds stuff up   | `SUM(salary)`               |
| `AVG()`   | Averages values | `AVG(price)`                |
| `MIN()`   | Finds smallest  | `MIN(age)`                  |
| `MAX()`   | Finds biggest   | `MAX(score)`                |
## Grouping Example

```sql
#Simple Grouping

SELECT department, COUNT(*) AS employee_count
FROM employees
GROUP BY department;

#Tell me how many employees are in each department.

#----------------------------------------------------------------------------------

#Multiple Column Grouping

SELECT department, job_title, COUNT(*) AS people
FROM employees
GROUP BY department, job_title;

#Groups rows like:
#All the engineers in IT = one group
#All the managers in HR = another group
#And so on.
```

## Unspoken Rules

| Rule                                                                    | Why It Matters                    |
| ----------------------------------------------------------------------- | --------------------------------- |
| Every column in SELECT must be in `GROUP BY` or wrapped in an aggregate | SQL hates ambiguity               |
| Aggregates go outside `GROUP BY`, not in it                             | `GROUP BY` just defines the split |
| `GROUP BY` comes **after** `WHERE`, but **before** `HAVING`             | Order matters                     |
| `GROUP BY` can be used without aggregates — weird but allowed           | Kinda like `DISTINCT` behavior    |
### GROUP BY vs DISTINCT

```sql
-- Same output
SELECT DISTINCT category FROM products;
SELECT category FROM products GROUP BY category;
```

- But `GROUP BY` is built for aggregation.
- `DISTINCT` is just a duplicate bouncer.