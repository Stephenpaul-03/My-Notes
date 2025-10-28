## **Indexing**

- Indexing is a data structure technique used to efficiently retrieve records from a database file based on some attributes (columns).
- It significantly improves the speed of query execution but may slightly reduce write performance due to overhead during insertions, deletions, and updates.
- **Goal :** Reduce the number of disk I/O operations required to locate data.

## **Working Principle**

When a query is executed, instead of performing a **full table scan**, the DBMS consults the index to locate the data more efficiently. The index maintains a mapping from a **key** (usually a column value) to a **record pointer** or address.

Internally, this may be implemented using **tree-based** or **hash-based** structures.

## **Types of Indexes in DBMS**

### **# A. Based on Structure**

- **B-Tree Index**
    - Most common index structure.
    - Balanced tree structure that maintains sorted data.
    - Supports range queries (e.g., `BETWEEN`, `>`, `<`).
    - Commonly used in PostgreSQL, MySQL (InnoDB), Oracle.
    - **Advantages:**
        - Balanced height ensures `O(log n)` search time.
        - Efficient for insert, delete, and update operations.
- **Hash Index**
    - Uses a hash function to map keys to buckets.
    - Efficient for equality comparisons (e.g., `=`, `IN`).
    - Poor performance for range queries.
    - **Used in:** Memory-optimized tables, Redis-like key-value stores.
    - **Disadvantage:** Not order-preserving.
- **Bitmap Index**
    - Uses bit arrays for each distinct value.
    - Optimal for columns with **low cardinality** (few unique values).
    - Efficient for analytical and decision-support systems.
    - **Example:** Gender, Boolean fields, Country codes.
    - **Note:** Not suitable for high-frequency updates.
- **GiST (Generalized Search Tree) and SP-GiST**
    - Supports indexing of complex data types (e.g., geometric, full-text).
    - Used in PostgreSQL.

### **# B. Based on Logical Design**

- **Primary Index**
    - Built on the primary key.
    - Automatically created by DBMS.
    - Usually **clustered**.
- **Secondary Index**
    - Built on non-primary key columns.
    - May or may not be unique.
    - Often **non-clustered**.
- **Unique Index**
    - Enforces uniqueness constraint on column values.
    - Often used for candidate keys.

### **# C. Based on Physical Storage**

- **Clustered Index**
    - Alters the physical order of data in the table to match the index.
    - One per table.
    - Faster for range-based queries.
    - **Example:** SQL Server, MySQL (InnoDB primary key is clustered by default).
- **Non-Clustered Index**
    - Index structure is separate from the actual data.
    - Contains pointers to the actual data row.
    - Multiple per table.

### **# D. Specialized Indexes**

- **Full-Text Index**
    - Enables efficient searching within textual data.
    - Supports ranking, proximity, and boolean logic.
    - Used in search engines, document stores.
- **Spatial Index**
    - Optimized for spatial data types like geometry, geography.
    - Supports spatial operations: containment, intersection, etc.
- **Expression-Based Index**
    - Built on the result of an expression or function.
    - Example: `CREATE INDEX ON orders (LOWER(customer_name));`
- **Composite Index (Concatenated Index)**
    - Index built on multiple columns.
    - Effective for multi-column search predicates.
