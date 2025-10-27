## Window Functions

| Function | Description |
| --- | --- |
| `ROW_NUMBER()` | Unique row number per partition |
| `RANK()` | Rank with gaps |
| `DENSE_RANK()` | Rank without gaps |
| `NTILE(n)` | Splits rows into `n` buckets |
| `LAG()` / `LEAD()` | Value from previous/next row |
| `FIRST_VALUE()` / `LAST_VALUE()` | First/last value in partition |
| `NTH_VALUE()` | Get the Nth value in partition |
| `CUME_DIST()` | Cumulative distribution |
| `PERCENT_RANK()` | Percentile rank |
| `SUM()` / `AVG()` / `COUNT()` / `MIN()` / `MAX()` **with `OVER()`** | Aggregates without collapsing rows |