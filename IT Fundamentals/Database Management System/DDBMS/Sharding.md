## **Sharding**

- **Sharding** is a database architecture pattern that involves breaking a large dataset into smaller, more manageable pieces called *shards*.
- Each shard contains a unique subset of the total data and is stored on a separate database server.
- Together, all shards represent the complete dataset and allow the system to handle more traffic, larger data volumes, and increased transaction rates by distributing the load across multiple machines.

## **How Sharding Works**

- **Horizontal Partitioning:**
    - Sharding splits a table’s rows across multiple databases rather than splitting columns, so each shard holds a portion of the rows.
- **Shard Key:**
    - A specific column value (e.g., user ID, region) is designated as the *shard key* to determine which shard a piece of data belongs to.
    - The choice of shard key is crucial for balanced data distribution.
- **Shared-Nothing Architecture:**
    - Each shard is autonomous and operates independently, which means that a failure in one shard does not directly compromise others.

## **Common Sharding Methods**

| Sharding Method | Description | Pros | Cons | Example Use Case |
| --- | --- | --- | --- | --- |
| **Range-based** | Divides data into shards based on value ranges of the shard key | Simple to implement; logical grouping | Risk of uneven data ("hot spots") | E-commerce by date ranges |
| **Hash-based** | Uses a hash function on the shard key to assign data to shards | Uniform distribution; avoids hot spots | Harder to support range queries | Social networks, user-based services |
| **Directory-based** | Maintains a lookup table to map keys to shards | Flexible; supports dynamic rebalancing | Complexity in management and potential single point | Enterprise apps with unpredictable patterns |

## **Benefits of Sharding**

- **Scalability:**
    - Enables horizontal scaling
    - adding more servers as data grows.
- **Performance:**
    - Queries operate on smaller datasets, yielding faster response times.
- **Fault Isolation:**
    - A failure impacts only the affected shard;
    - the whole system does not go down.
- **Improved Resource Utilization:**
    - Load is more evenly distributed, lowering the chance of overloading a single server.
- **Efficient Maintenance:**
    - Tasks like backups and schema changes can often be performed on shards independently, speeding up operations.

## **Sharding vs. Replication**

|  | Sharding | Replication |
| --- | --- | --- |
| **Goal** | Scalability and performance (write scaling) | High availability and redundancy (read scaling) |
| **Data** | Each shard holds a unique subset of the data | Each replica holds a full copy of the data |
| **Strength** | Distributes write and storage load | Distributes read load, improves failover |
| **Complexity** | Management and query routing are more complex | Simpler, but synchronization required |

## **Drawbacks and Challenges**

- **Increased Complexity:**
    - Managing and operating a sharded system involves complex routing and potential cross-shard queries.
- **Difficult Rebalancing:**
    - If a shard becomes overloaded, redistributing data can be challenging
- **Shard Key Selection:**
    - A poor shard key can cause uneven distribution, hurting performance and scalability.
- **Cross-Shard Operations:**
    - Queries involving multiple shards are harder to execute efficiently.