## **CAP**

The **CAP theorem** (also known as Brewer’s theorem) is a fundamental principle in distributed systems, stating that **a distributed data store can guarantee only two out of the following three properties at any given time**:

- **Consistency**:
    - Every read receives the most recent write or an error.
    - This means all nodes in the system reflect the same data at the same time.
- **Availability**:
    - Every request receives a response (success or failure), even if the response does not contain the most recent write.
    - The system remains operational for every request to a non-failing node.
- **Partition Tolerance**:
    - The system continues to operate even if network partitions (communication breakdowns between nodes) occur.
    - It tolerates dropped or delayed messages between nodes.

## **Key Insights**

- **No distributed system can guarantee all three properties (C, A, and P) simultaneously -** only any two can be guaranteed at once if there is a network partition.
- In the event of a network partition, a system designer must trade off either **consistency** or **availability**.
- In the absence of network partitions, it is possible to have both consistency and availability.

## **Practical Implications**

| System Type | Consistency | Availability | Partition Tolerance | Example Scenarios |
| --- | --- | --- | --- | --- |
| CP | Yes | No | Yes | Banking, ticket booking: correctness > always-on |
| AP | No | Yes | Yes | Social media, review sites: always-on > perfectly fresh data |
| CA | Yes | Yes | No | Possible only in reliable networks (rare in distributed systems) |
- **Partition tolerance** is usually assumed as essential in real-world distributed systems since network failures are inevitable.
- This means most systems are designed to be either **CP** (Consistency + Partition tolerance) or **AP** (Availability + Partition tolerance).

## **Real-World Examples**

- **CP Systems**:
    - Focus on strong consistency
    - e.g., traditional relational databases, some financial or inventory systems.
- **AP Systems**:
    - Prioritize uptime/availability
    - e.g., many NoSQL databases and social platforms, where seeing slightly outdated or inconsistent data temporarily is acceptable.