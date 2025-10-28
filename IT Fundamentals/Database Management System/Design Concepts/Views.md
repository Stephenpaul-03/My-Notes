## **Definition**

- **Views** represent a virtual table or logical representation of data derived from one or more base tables.
- They do not store data themselves; instead, they dynamically present data as defined by a SQL query.

A **view** is a named SQL query stored in the database schema. When queried, the DBMS dynamically computes the result set based on the view definition.

```sql
CREATE VIEW view_name AS
SELECT column1, column2
FROM table_name
WHERE condition;
````

**Key Characteristics:**

- **Virtuality**: No data is stored; data is fetched from the underlying base tables.
- **Schema-level object**: Managed similarly to tables but without physical storage.
- **Updatable (with restrictions)**: Some views can be updated, but others, especially those involving joins, aggregations, or set operations, are read-only.
    
## **Types of Views**

| Type                  | Description                                                                                            |
| --------------------- | ------------------------------------------------------------------------------------------------------ |
| **Simple View**       | Derived from a single table; no functions or group operations.                                         |
| **Complex View**      | Derived from multiple tables, may include joins, aggregations, and grouping.                           |
| **Materialized View** | A special case that stores the result physically, improving read performance at the cost of freshness. |
| **Inline View**       | A subquery in the FROM clause, used temporarily within a larger query.                                 |

## **Use Cases & Benefits**

- a. **Data Abstraction**
- b. **Security Enforcement**
- c. **Reusability & Maintainability**
- d. **Simplification of Complex Queries**
    
## **Updatability of Views**

Views **can be updated** if:

- Based on a single table.
- No aggregate functions or group by/having clauses.
- No DISTINCT, set operators (UNION, INTERSECT), or subqueries in SELECT.

Views **cannot be updated** (or require INSTEAD OF triggers) if:

- They involve joins, groupings, aggregations, or set operations.
    
To manage updatability:

```sql
CREATE TRIGGER instead_of_trigger
INSTEAD OF INSERT ON view_name
FOR EACH ROW
BEGIN
  -- logic to update base table
END;
```

## **Materialized Views (Optional Extension)**

Materialized views are physically stored query results and periodically refreshed.

- **Use case**: Optimizing query performance in large-scale data warehouses.
- **Trade-off**: Sacrifices real-time accuracy for faster reads.
    

```sql
CREATE MATERIALIZED VIEW sales_summary
BUILD IMMEDIATE
REFRESH FAST ON COMMIT
AS
SELECT region, SUM(amount) FROM sales GROUP BY region;
```

## **View Performance Considerations**

- **Performance Overhead**
    - For complex views, especially nested ones, performance may degrade if the underlying query is expensive.
        
- **Optimization**
    - Modern DBMS engines optimize view queries using query rewrites, pushing predicates down into base queries.
        
- **Indexing**
    - Since views themselves cannot be indexed, performance tuning must occur at the base table level, unless using indexed materialized views.

## **Limitations and Risks**

- **Staleness (Materialized views)**: Data may become outdated without frequent refresh.
- **Dependency management**: Changes in base table schemas (e.g., column renaming) can break views.
- **Debugging complexity**: Nested views can obfuscate performance bottlenecks.