## Definition

Denormalization is the process of deliberately introducing redundancy into a relational database by combining data from multiple related tables into a single table. 
- While normalization aims to reduce redundancy and improve data integrity by decomposing tables into smaller ones, denormalization combines some of these tables back together to improve performance and simplify queries.
- Note that denormalization does not mean ‘reversing normalization’ or ‘not to normalize’. It is an optimization technique that is applied after normalization.
## Reason

1. **Performance Optimization**
    - Normalized databases often require multiple joins to retrieve related data. These joins can be resource-intensive, especially on large datasets. Denormalization reduces the number of joins required by storing data together.
2. **Simpler Queries**
    - With denormalized tables, queries become easier to write and understand since all the necessary data may be in a single table.
3. **Faster Read Operations**
    - Denormalization is especially useful in read-heavy applications like reporting, dashboards, and data warehouses where quick access to pre-aggregated or related data is needed.
4. **Reduced Join Overhead**
    - Joins can slow down performance and increase query complexity. Denormalized structures reduce this dependency.
## **Techniques**

1. **Adding Redundant Columns**
    - Copy data from one table into another to avoid joins.
    - *Example*: Storing `DepartmentName` in the `Employee` table even if it's already present in a `Department` table.
2. **Precomputed Aggregates**
    - Store totals, averages, or other calculated values in a table.
    - *Example*: Saving `TotalPurchaseAmount` in a `Customer` table instead of calculating it from all purchases each time.
3. **Table Merging (Flattening)**
    - Combine related tables into one larger table.
    - *Example*: Merging `Orders`, `Customers`, and `Products` into one wide `OrderSummary` table.
4. **Storing Derived Data**
    - Save calculated fields like `Age` instead of calculating it from `DateOfBirth` repeatedly.
5. **Duplicating Tables or Data Sets**
    - Create copies of tables in different formats or with additional fields for specific use cases.
## **Advantages**

- Improved read performance.
- Simplified queries with fewer joins.
- Better suited for analytical and reporting workloads.
- Reduced need for complex database views or intermediate processing.
## **Disadvantages**

- **Data Redundancy**: Increases storage requirements.
- **Update Anomalies**: Redundant data must be updated in multiple places, increasing the chance of inconsistency.
- **Slower Write Operations**: Inserts, updates, and deletes become more complex.
- **Potential Integrity Issues**: More effort is required to maintain accurate and consistent data.
## **When to Use**

- In **read-heavy** environments (e.g., OLAP systems, data marts, reporting databases).
- When performance testing indicates that joins are significantly slowing down queries.
- In situations where maintaining real-time consistency is less critical than performance.
## **Analogy**

Denormalization is like preparing ready-to-eat meals instead of storing raw ingredients. While raw ingredients (normalized data) allow for flexibility and efficient storage, ready meals (denormalized data) provide quick access and faster serving at the cost of increased preparation effort and storage space.
