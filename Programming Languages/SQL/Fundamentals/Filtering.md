## `WHERE` CLAUSE

Used to filter **rows before** any grouping, aggregation, or selection goes down.

```sql
SELECT * FROM table_name
WHERE condition;
```
## Overview Table

| **Condition Type**       | **Operator / Keyword**   | **Example**                                               |
| ------------------------ | ------------------------ | --------------------------------------------------------- |
| **Equality**             | `=`, `<>`, `!=`          | `WHERE age = 25`                                          |
| **Comparison**           | `>`, `<`, `>=`, `<=`     | `WHERE salary >= 50000`                                   |
| **Range check**          | `BETWEEN` ... `AND`      | `WHERE age BETWEEN 18 AND 25`                             |
| **Set membership**       | `IN (...)`               | `WHERE dept IN ('HR', 'IT')`                              |
| **Pattern matching**     | `LIKE`, `ILIKE`          | `WHERE name LIKE 'A%'`                                    |
| **Null check**           | `IS NULL`, `IS NOT NULL` | `WHERE address IS NOT NULL`                               |
| **Logical combinations** | `AND`, `OR`, `NOT`       | `WHERE age > 25 AND dept = 'IT'`                          |
| **Existence**            | `EXISTS (subquery)`      | `WHERE EXISTS (SELECT 1 FROM managers WHERE id = emp_id)` |
| **Subquery check**       | `= (subquery)`           | `WHERE salary > (SELECT AVG(salary) FROM employees)`      |
| **Multiple options**     | `ANY`, `ALL`, `SOME`     | `WHERE salary > ANY (SELECT salary FROM interns)`         |
## Syntax Combos

### Basic Equality

```sql
SELECT * FROM users WHERE username = 'neo';
```

### Inequality

```sql
SELECT * FROM orders WHERE status <> 'shipped';
```

### Using `AND` and `OR`

```sql
SELECT * FROM employees
WHERE age > 30 AND department = 'Finance';

SELECT * FROM users
WHERE country = 'India' OR country = 'USA';

```

### `BETWEEN`

```sql
SELECT * FROM products
WHERE price BETWEEN 100 AND 500;
```

### `IN` & `NOT IN`

```sql
SELECT * FROM students
WHERE grade IN ('A', 'B');

SELECT * FROM students
WHERE id NOT IN (SELECT student_id FROM dropout_list);
```

### `LIKE` for pattern match

```sql
SELECT * FROM books
WHERE title LIKE 'The%';  -- starts with 'The'

SELECT * FROM users
WHERE email LIKE '%@gmail.com';  -- ends with '@gmail.com'

SELECT * FROM files
WHERE name LIKE '__a%';  -- third character is 'a'
```

_ matches one character 
`%` matches any number of characters
### `IS NULL` & `IS NOT NULL`

```sql
SELECT * FROM users WHERE last_login IS NULL;
```

### `EXISTS`

```sql
SELECT name FROM departments d
WHERE EXISTS (
    SELECT 1 FROM employees e WHERE e.dept_id = d.id
);
```

### Subquery filter

```sql
SELECT name FROM employees
WHERE salary > (
    SELECT AVG(salary) FROM employees
);
```

## `HAVING` Clause

### Simplified Working

- `HAVING` filters the **results of `GROUP BY`**.
-  You use it when you wanna say:
- “Okay, I grouped everything. Now get rid of the weak ones.” 
### Basic Syntax

```sql
SELECT column1, AGG_FUNC(column2)
FROM table
GROUP BY column1
HAVING condition;
```

### Example:

```sql
SELECT department, COUNT(*) AS emp_count
FROM employees
GROUP BY department
HAVING COUNT(*) > 10;
```

## Syntax Combos

### Count Groups

```sql
SELECT course_id, COUNT(*) AS student_count
FROM enrollments
GROUP BY course_id
HAVING COUNT(*) >= 5;
```
### Filter with Aggregate Condition

```sql
SELECT customer_id, SUM(amount) AS total_spent
FROM orders
GROUP BY customer_id
HAVING SUM(amount) > 1000;
```
### Mix with `WHERE`

```sql
SELECT category, AVG(price)
FROM products
WHERE stock > 0
GROUP BY category
HAVING AVG(price) < 50;
```
### Multiple Conditions

```sql
SELECT dept, COUNT(*) AS emp_count, AVG(salary) AS avg_salary
FROM employees
GROUP BY dept
HAVING COUNT(*) > 5 AND AVG(salary) > 70000;
```

### `WHERE` vs `HAVING`

| Feature                                      | `WHERE` | `HAVING` |
| -------------------------------------------- | ------- | -------- |
| Filters **before** grouping                  | Y       | N        |
| Filters **after** grouping                   | N       | Y        |
| Works with aggregates (`COUNT`, `SUM`, etc.) | N       | Y        |
| Applies to **rows**                          | Y       | N        |
| Applies to **groups**                        | N       | Y        |
