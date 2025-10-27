## Definition

- Ranking functions are **window functions** that assign a rank or number to rows based on a specific order.
- They work with the `OVER()` clause - which defines how the "window" is sliced.
## Core Ranking Functions

| Function       | What It Does                                               |
| -------------- | ---------------------------------------------------------- |
| `RANK()`       | Gives same rank to ties, skips next ranks                  |
| `DENSE_RANK()` | Like `RANK()`, but **no gaps** after ties                  |
| `ROW_NUMBER()` | Gives a **unique number** to every row, no matter what     |
| `NTILE(n)`     | Divides ordered rows into `n` roughly equal groups (tiles) |
## Syntax

```sql
SELECT column1, RANK() OVER (PARTITION BY colX ORDER BY colY DESC) AS rank
FROM table_name;
```

## Real-World Examples

### `RANK()` - Skips Ranks for Ties

```sql
SELECT name, score,
  RANK() OVER (ORDER BY score DESC) AS rank
FROM students;
```

| name                  | score | rank |
| --------------------- | ----- | ---- |
| One Piece             | 100   | 1    |
| Bleach                | 100   | 1    |
| Koe No Katachi        | 98    | 3    |
| Cyberpunk Edgerunners | 95    | 4    |
-  Both One Piece and Bleach tied, so rank 2 is skipped.
## `DENSE_RANK()` - No Skips

```sql
SELECT name, score,
  DENSE_RANK() OVER (ORDER BY score DESC) AS dense_rank
FROM students;
```

| name                  | score | dense_rank |
| --------------------- | ----- | ---------- |
| One Piece             | 100   | 1          |
| Bleach                | 100   | 1          |
| Koe No Katachi        | 98    | 2          |
| Cyberpunk Edgerunners | 95    | 3          |
-  Same tie, but ranks are tightly packed.
## `ROW_NUMBER()` -  Just Numbers, No Ties

```sql
SELECT name, score,
  ROW_NUMBER() OVER (ORDER BY score DESC) AS row_num
FROM students;

```

| name           | score | row_num |
| -------------- | ----- | ------- |
| One Piece      | 100   | 1       |
| Bleach         | 100   | 2       |
| Koe No Katachi | 98    | 3       |
- Even if scores are tied, each row is uniquely numbered.
## `NTILE(n)` - Break into Percentiles/Buckets

```sql
SELECT name, score,
  NTILE(4) OVER (ORDER BY score DESC) AS quartile
FROM students;

```

- Divides rows into 4 buckets based on rank order.
## Using `PARTITION BY`

**restarts the ranking** per group.

```sql
SELECT department, employee, salary,
  RANK() OVER (PARTITION BY department ORDER BY salary DESC) AS dept_rank
FROM employees;
--"Give me top earners in each department."
```
## Common Mistakes

| Mistake                              | Fix                              |
| ------------------------------------ | -------------------------------- |
| Forgetting `ORDER BY` in `OVER()`    | Ranks will all be 1              |
| Using `WHERE` to get top 1           | Use `ROW_NUMBER()` + CTE instead |
| Not using `PARTITION BY` when needed | All data gets ranked globally    |
