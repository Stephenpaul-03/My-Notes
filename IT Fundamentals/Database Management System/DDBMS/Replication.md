## **Definition**

- **Replication** in distributed databases refers to the process of maintaining multiple copies of the same data across several servers or nodes within a network.
- This practice is crucial for ensuring high availability, durability, performance, and reliability, especially in environments where downtime and data loss are unacceptable.

## **Key Benefits**

- **Fault Tolerance:**
    - If one replica fails, others can continue to serve requests, minimizing the risk of downtime and data loss.
- **High Availability:**
    - Data remains accessible as long as at least one replica is operational, critical for mission-critical applications.
- **Improved Performance:**
    - Queries can be served from the nearest or least-loaded replica, reducing read latency and balancing system load.
- **Disaster Recovery:**
    - Replication facilitates recovery from catastrophic failures, such as hardware malfunctions or data breaches.

## **Common Replication Strategies**

| Replication Type                     | Description                                                                                   | Trade-Offs / Use Cases                                    |
| ------------------------------------ | --------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| **Leader-Follower (Primary-Backup)** | A single leader node handles all writes, followers replicate its state and serve reads.       | Simple, strong consistency. Used when consistency is key  |
| **Multi-Leader (Multi-Primary)**     | Multiple nodes can accept writes; changes are propagated and resolved for conflicts.          | Higher write availability but complex conflict resolution |
| **Peer-to-Peer**                     | All nodes are equals; each can process reads and writes, with data synchronized across nodes. | Good for decentralized systems. Ensures robustness        |
| **Chain Replication**                | Updates are sent down a chain of nodes; strong consistency along the chain.                   | Used for strong consistency, but may incur latency        |

## **Replication Schemes**

| Scheme                  | Description                                                   | Pros                                 | Cons                                                      |
| ----------------------- | ------------------------------------------------------------- | ------------------------------------ | --------------------------------------------------------- |
| **Full Replication**    | All nodes maintain a complete copy of the database.           | Maximizes availability & performance | Complex concurrency, heavy storage, slow updates          |
| **Partial Replication** | Only selected fragments/data are replicated at certain nodes. | Efficient resource use, scalable     | May hinder global query performance for unreplicated data |
| **No Replication**      | Each data fragment is at just one node; no duplicates.        | Simplifies concurrency               | Low availability, vulnerable to data loss                 |

## **Synchronous & Asynchronous Replication**

- **Synchronous Replication:**
    - Updates propagate to all replicas instantly before confirming to clients. Guarantees strong consistency but can cause latency.
- **Asynchronous Replication:**
    - Updates are first applied to the primary and later propagated to replicas. Lower latency, but temporary inconsistencies may appear.
- Systems must balance performance (favoring asynchronous) with consistency (favoring synchronous), depending on application needs.

## **Types of Data Replication**

## **# By Database Technology**

- **Transactional Replication:**
    - Real-time updates sent as they occur;
    - ensures consistency for transactional workloads.
- **Snapshot Replication:**
    - Periodically copies data "as is" at a point in time;
    - best for infrequently changing data.
- **Merge Replication:**
    - Allows independent changes at multiple sites, later merged together
    - useful for mobile or branch environments.

## **Common Challenges**

- **Consistency Maintenance:**
    - Ensuring all replicas reflect the latest updates, especially across wide geographic regions.
- **Conflict Resolution:**
    - Particularly in multi-leader or merge scenarios, concurrent modifications may conflict and require reconciliation.
- **Resource Overhead:**
    - More copies mean higher storage, network, and compute costs.
- **Update Propagation Delay:**
    - Asynchronous models may have a lag between when data updates are made and when all replicas are synchronized.