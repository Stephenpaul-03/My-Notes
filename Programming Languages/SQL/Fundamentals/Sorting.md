
## `ORDER BY` Clause

### Working
- It **orders result rows** based on one or more columns or expressions.

```sql
SELECT column1, column2
FROM table_name
ORDER BY column1 [ASC | DESC];
```

- By default, it sorts in **ascending** order (A → Z, 0 → 9).
- Use `DESC` if you want the biggest/last things first.

### Sorting Basics

| Keyword | Meaning | Default? |
| --- | --- | --- |
| `ASC` | Ascending order (low → high, A → Z) | Yes |
| `DESC` | Descending order (high → low, Z → A) | No |

```sql
SELECT * FROM employees
ORDER BY salary DESC;
```

### Multi-Column Sorting

```sql
SELECT * FROM employees
ORDER BY department ASC, salary DESC;
```

- Meaning: Sort by department A → Z.
- Within each department, sort salary high → low.

### Sort by Column Index (Not Advisable)

```sql
SELECT name, age FROM users
ORDER BY 2 DESC;
```

- This sorts by the **second selected column**, i.e., `age`.
- Use with caution. This breaks **hard** if SELECT order changes.

### Sorting with Expressions

Can sort by **calculated values**:

```sql
SELECT name, price, discount, (price - discount) AS final_price
FROM products
ORDER BY final_price ASC;
```

Or even directly without alias:

```sql
ORDER BY (price - discount);

```

### Sorting with NULLs

- Different databases treat NULLs differently.
- Some put them **first**, others put them **last**.
- Can be Controlled by

```sql
ORDER BY last_login ASC NULLS LAST;
ORDER BY rating DESC NULLS FIRST;
```

| Database   | `NULLS FIRST / LAST` supported? |
| ---------- | ------------------------------- |
| PostgreSQL | Yes                             |
| Oracle     | Yes                             |
| MySQL      | No (use `IS NULL` trick)        |
| SQL Server | No (no direct support)          |
In MySQL/SQL Server:

```sql
ORDER BY last_login IS NULL, last_login;
-- NULLs come last
```
### Pagination

```sql
SELECT * FROM blog_posts
ORDER BY published_date DESC
LIMIT 10 OFFSET 20;
```

-  3rd page of 10 posts (assuming page size = 10)