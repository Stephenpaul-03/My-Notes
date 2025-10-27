## Definition

-A view is a stored SQL query that you can use like a table.
	- It **doesn't store actual data** (unless it's a materialized view)
	- It **pulls live data** from underlying tables whenever you query it
	- Makes SQL **clean, readable, and modular**

## Syntax

```sql
CREATE VIEW view_name AS
SELECT columns
FROM table
WHERE condition;

--- EXAMPLE -- 
CREATE VIEW active_customers AS
SELECT id, name, email
FROM customers
WHERE status = 'active';

SELECT * FROM active_customers;
----Instead of repeating the same filter in 5 different places.----
```

## Reasons to Use

| Benefit | Reason |
| --- | --- |
| Code Reuse | No repeating complex joins or filters |
| Security | Restrict what data users can access |
| Simplicity | Hide gross business logic behind a clean interface |
| Abstraction | Backend can change, view stays the same |
| Maintainability | Change view logic in one place instead of 10 queries |

## Manipulating a View

```sql
---Updating a View---
CREATE OR REPLACE VIEW view_name AS
SELECT ...

---Dropping a View---
DROP VIEW view_name;

---Updating a view (has Constraints)---
UPDATE view_name SET column = value WHERE ...;
```

## View Update Constraint

- **Updatable Views**:
	- Based on a single table
	- No aggregate functions (`SUM`, `AVG`, etc.)
	- No `DISTINCT`
	- No `GROUP BY` or `HAVING`
	- No `UNION`, `JOIN`, subqueries, or window functions
## Materialized Views

- A materialized view actually stores the data.
- It doesn’t auto-update unless you refresh it.


```sql
CREATE MATERIALIZED VIEW sales_summary AS
SELECT region, SUM(amount) AS total
FROM sales
GROUP BY region;

--- To Refresh ---
REFRESH MATERIALIZED VIEW sales_summary;

```

**Use this when:**
- Performance is key
- Data doesn't need to be real-time
- to avoid heavy recalculations

---