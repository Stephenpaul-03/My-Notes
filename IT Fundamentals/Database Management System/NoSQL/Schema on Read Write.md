## **Schema on Read / Write**

## **Schema on Write**

- Schema on Write means the data's structure (schema) is enforced **at the time the data is written (ingested)** into the storage system. You must define how the data should look (fields, types, constraints, etc.) before you store any data.

### # **How it works**

- **Example:** Traditional SQL databases (like MySQL, PostgreSQL, etc.)
- When creating a table, you define the columns and their types (e.g., `id INT, name VARCHAR(50)`).
- Any data inserted into the table must conform to this schema, or the database will reject it.

### # **Pros**

- Data is consistent and conforms to expectations.
- Easier for downstream applications and analytics because all data follows the same structure.
- Prevents "dirty" or inconsistent data from entering the system.

### # **Cons**

- Rigid: harder to evolve the schema without running complex migrations.
- Initial schema design must be well-planned.
- Less flexibility for unknown or unstructured data.

## **Schema on Read**

- Schema on Read means data is stored **without enforcing a schema**. The schema is applied **when the data is read (queried/accessed)**.

### # **How it works**

- **Example:** Data lakes using Hadoop, AWS S3, Apache Parquet/ORC, or NoSQL databases (like MongoDB).
- You can store raw, semi-structured, or unstructured data (like JSON, CSV, logs, events).
- When querying the data (for analysis or reporting), you specify the schema that should be applied, interpreting the raw bytes at that moment.

### # **Pros**

- Flexible: easily store any kind of data, including unknown or evolving structures.
- Good for exploratory analysis and data science.
- Schema can be evolved or changed on demand, for each use case/query.

### # **Cons**

- Data quality and consistency are not guaranteed until read time.
- Queries may fail or behave unexpectedly if the assumed schema doesn't match the actual data.
- Can be more difficult for operational or transactional workloads.

## **Summary Table**

| Feature | Schema on Write | Schema on Read |
| --- | --- | --- |
| **When applied** | When data is written | When data is read |
| **Data Validation** | Enforced before storage | Enforced when accessed |
| **Flexibility** | Less flexible | Very flexible |
| **Common Use** | OLTP, Data Warehouses | Data Lakes, Big Data |
| **Examples** | SQL databases | S3 Data Lakes, Hadoop, NoSQL |

## **Quick Analogy**

- **Schema on Write:** Like filling out a strict government form at the entrance—if you don't fit the requirements, you can't enter.
- **Schema on Read:** Like storing all received documents in a box, and deciding which ones you care about and how to interpret them only when you actually need to use them.