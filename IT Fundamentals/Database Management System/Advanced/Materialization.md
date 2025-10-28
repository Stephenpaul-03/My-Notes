## **Definition**

- A **Materialized View** is:
  - A **physical database object** that stores the results of a query.
  - Created via `CREATE MATERIALIZED VIEW` using queries with **joins, aggregations, filtering**, etc.
  - Used to **optimize performance** by avoiding repeated computation of expensive queries.

## **Working**

### **Creation**

```sql
CREATE MATERIALIZED VIEW sales_summary AS
SELECT region, SUM(amount) AS total_sales
FROM sales
GROUP BY region;
````

- The result is stored as an actual table in the database.

### **Storage**

- Data is stored **persistently** on disk.
- Requires **disk space proportional to the result set size**.
- Indexed like normal tables if needed.
    

### **Refresh Mechanism**

Materialized views **do not auto-update** like virtual views. Refresh strategies include:

- **Manual**: Explicitly triggered by admin or application.
- **Scheduled**: Periodic refresh (e.g., every hour).
- **On-commit**: Automatically refreshed on changes to base tables (costly).

```sql
REFRESH MATERIALIZED VIEW sales_summary;
```

## **Advantages**

|Benefit|Description|
|---|---|
|**Improved Performance**|Eliminates the need to recompute expensive queries on every access.|
|**Reduced Load**|Offloads heavy query computation from base tables.|
|**Denormalization Support**|Pre-joins or aggregates data for ease of querying.|
|**Offline Access**|Useful when base tables are unavailable (e.g., maintenance, network delay).|

## **Challenges**

|Issue|Description|
|---|---|
|**Storage Overhead**|Takes up physical space equal to the size of the query result.|
|**Data Staleness**|Refresh delay causes outdated data if not properly managed.|
|**Refresh Performance**|Refreshing large or complex views consumes resources.|
|**Concurrency Control**|Refreshing during active transactions can cause consistency issues.|
|**Maintenance Overhead**|Requires administrative oversight to balance freshness and performance.|

## **Use Cases**

|Use Case|Explanation|
|---|---|
|**Data Warehousing**|For aggregations, cubes, and drill-down reports.|
|**Reporting**|Precomputed data for high-performance BI dashboards.|
|**Aggregation**|Roll-ups or summaries of transactional data.|
|**Caching**|Acts as a cache layer for frequently queried data.|

## **Materialized View Refresh Types**

|Refresh Mode|Description|
|---|---|
|**Complete Refresh**|Re-executes the underlying query from scratch.|
|**Fast Refresh**|Uses logs or incremental changes (requires special setup).|
|**Force Refresh**|Tries fast refresh first; falls back to complete refresh if needed.|