
## **PIVOT**

Rotate rows into columns. 
### Syntax :

```sql
SELECT *
FROM (
    SELECT Product, Year, Sales
    FROM SalesData
) AS SourceTable
PIVOT (
    SUM(Sales)
    FOR Year IN ([2022], [2023], [2024])
) AS PivotTable;

```

### Example:

#### Original Table (`SalesData`)

| Product | Year | Sales |
| ------- | ---- | ----- |
| Laptop  | 2022 | 2000  |
| Laptop  | 2023 | 2200  |
| Phone   | 2022 | 1500  |
| Phone   | 2023 | 1800  |

#### Pivoted Output

| Product | 2022 | 2023 |
| ------- | ---- | ---- |
| Laptop  | 2000 | 2200 |
| Phone   | 1500 | 1800 |

## **UNPIVOT**

Rotate columns into rows. 

### Syntax

```sql
SELECT Product, Year, Sales
FROM (
    SELECT Product, [2022], [2023]
    FROM PivotedSales
) AS SourceTable
UNPIVOT (
    Sales FOR Year IN ([2022], [2023])
) AS UnpivotedTable;
```

### Example:

#### Input Table (`PivotedSales`)

| Product | 2022 | 2023 |
| ------- | ---- | ---- |
| Laptop  | 2000 | 2200 |
| Phone   | 1500 | 1800 |

#### Unpivoted Output

| Product | Year | Sales |
| ------- | ---- | ----- |
| Laptop  | 2022 | 2000  |
| Laptop  | 2023 | 2200  |
| Phone   | 2022 | 1500  |
| Phone   | 2023 | 1800  |

## Comparison

| Feature    | PIVOT                                                                    | UNPIVOT                                                          |
| ---------- | ------------------------------------------------------------------------ | ---------------------------------------------------------------- |
| Transforms | Rows ⇒ Columns                                                           | Columns ⇒ Rows                                                   |
| Use Case   | Reporting, summaries                                                     | Normalization, ETL pipelines                                     |
| Looks Like | Flattened reports                                                        | Tall skinny tables                                               |
| SQL Flavor | Not available in MySQL natively (needs hacks with `CASE` and `GROUP BY`) | Same - SQL Server has native support, others require workarounds |