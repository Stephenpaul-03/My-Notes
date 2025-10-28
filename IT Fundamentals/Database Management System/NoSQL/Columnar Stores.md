## **Columnar Stores**

- - A **columnar store**, or **column-oriented database**, is a type of database management system that stores data by columns rather than traditional rows.
- - This structure is especially optimized for analytical workloads, where operations often access only a subset of columns across a large number of rows.
- - In a columnar store, all the values of a particular column are stored together, enabling efficient access, compression, and processing of data

## **Working**

- **Storage Format:**
    - Each column’s data is grouped and stored together on disk.
    - For example, storing customer data like ages, names, and locations: all ages are stored together, all names together, all locations together, etc.
- **Reading Data:**
    - When running queries that only need some columns, the system reads only those columns, avoiding unnecessary data retrieval and speeding up queries.
- **Writing Data:**
    - New records are written by appending their values to each corresponding column segment, not as a full row.

## **Advantages**

- **Faster Analytical Queries:**
    - Aggregations (e.g., averages, sums) and filtering are much faster because only relevant columns are accessed.
- **Better Compression:**
    - Columns usually store data of the same type, allowing for advanced compression techniques. This reduces storage needs and further boosts speed
- **Efficient Use of Memory and I/O:**
    - Only required columns are loaded into memory or read from disk, saving resources.
- **Optimized for Big Data/Analytics:**
    - Particularly effective for data warehouse, business intelligence, and big data analytics workloads, where queries often focus on a limited set of columns across massive datasets.
- **Scalability:**
    - Many columnar stores distribute data across clusters to handle petabytes of data
## **Limitations**

- **Not Ideal for Transactional Workloads:**
    - For workloads needing frequent inserts, updates, or accesses to complete records (rows), traditional row-based databases are more efficient.
- **Bulk Writes Preferred:**
    - Incremental or transactional inserts can be less efficient compared to row-oriented systems.
- **Complex Updates:**
    - Updating many fields at once (across columns) can be slower due to separate storage.

## **Typical Use Cases**

- Data warehousing
- Business intelligence dashboards
- Big data analytics
- Real-time reporting
- Machine learning data preparation

## **Examples**

| Database | Notes |
| --- | --- |
| Amazon Redshift | Managed cloud data warehouse |
| Google BigQuery | Serverless analysis, scalable analytics |
| Snowflake | Multi-cloud, data sharing, and warehousing |
| ClickHouse | Open source OLAP, ultra-fast analytics |
| Apache Druid | Real-time data analytica |
| Vertica | Enterprise analytics, high concurrency |
| DuckDB | Fast, local analytics, embedded SQL |
| MariaDB ColumnStore | Open-source, MySQL-compatible columnar storage |
| Apache Kudu | Designed for fast analytics on Hadoop |