## Definition

- A **subquery** is a query that's nested inside another query.
- Similar to asking a question inside a question
## Types of Subqueries

| Subquery Type           | Where It Lives          | Use Case                             |
| ----------------------- | ----------------------- | ------------------------------------ |
| **Scalar**              | `SELECT` or `WHERE`     | Returns one value                    |
| **Column**              | `IN` clause             | Returns single column, multiple rows |
| **Row**                 | `= (SELECT col1, col2)` | Returns a full row                   |
| **Table / Inline View** | `FROM (...)`            | Acts like a temporary table          |
| **Correlated**          | Depends on outer query  | Re-evaluated per row                 |
## **Scalar Subquery
- *Returns a single value (one row, one column)*
- **Used in `SELECT`, `WHERE`, or `HAVING`**

```sql
-- Show all employees + the company-wide max salary
SELECT name, salary,
  (SELECT MAX(salary) FROM employees) AS max_salary
FROM employees;

```

- That subquery returns **one number** (the max salary). That’s scalar.
## **Column Subquery**
- *Returns one column, multiple rows*
- **Usually goes inside `IN`, `ANY`, or `ALL`**

```sql
-- Show customers who have placed at least one order
SELECT name
FROM customers
WHERE id IN (
  SELECT customer_id FROM orders
);

```

- Subquery gives you a **list of IDs** → main query checks if each customer is in that list.
## **Row Subquery**
-  *Returns one row, multiple columns*
 - **Used in `=`, `<>`, `IN` (multi-column)**

```sql
-- Compare one specific employee’s info to another employee
SELECT name, department_id, salary
FROM employees
WHERE (department_id, salary) = (
  SELECT department_id, salary
  FROM employees
  WHERE name = 'Alice'
);
```

- Returns a **row** like (3, 80000) → and checks who else has that combo.
## **Table/Inline View Subquery**
- *Acts like a virtual table inside `FROM`*
- **Used for further querying/aggregates**

```sql
-- Find departments with an average salary > 50000
SELECT dept, avg_salary
FROM (
  SELECT department_id AS dept, AVG(salary) AS avg_salary
  FROM employees
  GROUP BY department_id
) AS department_summary
WHERE avg_salary > 50000;
```

- That inner subquery is basically a **mini summarized table**.
- Outer query filters it.
## **Correlated Subquery**
-  *Depends on the outer query’s row - re-evaluated per row*
- **Used when you need per-row context**

```sql
-- Show employees who earn more than the average in their own department
SELECT name, salary, department_id
FROM employees e
WHERE salary > (
  SELECT AVG(salary)
  FROM employees
  WHERE department_id = e.department_id
);
```

- That subquery re-runs **for every employee**, using their `department_id`.
## **EXISTS / NOT EXISTS Subquery**
- *Checks for the **existence** of rows* — doesn’t care what the actual data is
 
```sql
-- Customers who have placed at least one order
SELECT name
FROM customers c
WHERE EXISTS (
  SELECT 1
  FROM orders o
  WHERE o.customer_id = c.id
);

# Or flip it:

-- Customers who have NEVER placed an order
SELECT name
FROM customers c
WHERE NOT EXISTS (
  SELECT 1
  FROM orders o
  WHERE o.customer_id = c.id
);
```
-  Only returns the `name` if the subquery **finds (or doesn’t find)** a match.
