## Aggregate Functions

| Function                                        | Description                              |
| ----------------------------------------------- | ---------------------------------------- |
| `COUNT()`                                       | Total number of rows or non-null entries |
| `SUM()`                                         | Total sum of numeric values              |
| `AVG()`                                         | Average value                            |
| `MIN()`                                         | Minimum value                            |
| `MAX()`                                         | Maximum value                            |
| `GROUP_CONCAT()` *(MySQL)*                      | Concatenates values into a single string |
| `STRING_AGG()` *(SQL Server/Postgres)*          | Same as above for other DBs              |
| `VARIANCE()` / `VAR_POP()`                      | Variance                                 |
| `STDDEV()` / `STDDEV_POP()`                     | Standard deviation                       |
| `BIT_AND()` / `BIT_OR()` *(Postgres)*           | Bitwise aggregation                      |
| `JSON_AGG()` / `JSON_OBJECT_AGG()` *(Postgres)* | Aggregate into JSON object               |