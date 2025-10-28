## **Definition**

- Consistency models define the rules for visibility and ordering of read and write operations on shared data in distributed systems.
- They establish what guarantees a system provides about the value returned by reads, especially under concurrent updates and network partitions.
- Choosing the right consistency model impacts performance, availability, and correctness of applications.

## **Major Consistency Models**

## # 1. **Strong Consistency**

- **Definition:** After a write, all reads (by any client, on any node) will always return the most recent value.
- **Guarantee:** Operations appear as if they happened in a strict, single, total order.
- **Use Case:** Financial systems, inventory management.
- **Common Protocols:** Distributed transactions, two-phase commit.

## # 2. **Sequential Consistency**

- **Definition:** The result of execution is the same as if all operations were executed in some sequential order, with each process's operations appearing in its program order.
- **Guarantee:** Per-process order is preserved, but real-time order across processes is not guaranteed.
- **Use Case:** Distributed shared memory, some multiprocessor systems

## # 3. **Linearizability (Strict Consistency)**

- **Definition:** A type of strong consistency ensuring each operation appears to take effect instantaneously at some point between its start and finish.
- **Guarantee:** Combines real-time constraints with sequential consistency.
- **Use Case:** Critical system registers, leader election

## # 4. **Causal Consistency**

- **Definition:** Operations that are causally related (one affects the other) are seen by all nodes in the same order. Unrelated operations may be seen in different orders.
- **Guarantee:** Maintains logical relationships and causality.
- **Use Case:** Collaborative editing, messaging platforms

## # 5. **Eventual Consistency**

- **Definition:** In the absence of new updates, all replicas will eventually converge to the same state. Reads might return stale data until replicas synchronize.
- **Guarantee:** No strict order; temporary inconsistency is acceptable for higher availability and performance.
- **Use Case:** Social networks, large-scale web services

## # 6. **Session Consistency**

- **Definition:** Guarantees that within a session, reads and writes by a single client are always consistent.
- **Guarantee:** Repeated reads within a session reflect the last write from that session.
- **Use Case:** Shopping carts, personalized user sessions

## # 7. **Weak Consistency**

- **Definition:** No strict guarantees about ordering or visibility of updates; only provides eventual convergence under certain synchronization points.
- **Guarantee:** Minimal, focused on extreme scalability and availability.
- **Use Case:** Caching layers, scenarios tolerating stale data.

## **Comparison Table**

| Consistency Model | Guarantees | Use Cases | Trade-Offs |
| --- | --- | --- | --- |
| Strong | Reads always return most recent write | Finance, inventory, databases | High latency, low availability |
| Sequential | All ops appear in some sequential order, per-process order held | Multiprocessors, shared memory | Lower overhead than strict, not real-time |
| Linearizability | Real-time total order (like single global timeline) | Critical control, leader systems | Performance hit; strictest |
| Causal | Preserves causal relationship ordering | Collaboration tools, chat apps | Lower availability than eventual |
| Eventual | All replicas conform after some time | Web, social feeds, NoSQL databases | May read stale data |
| Session | Consistent within user session | E-commerce, personal apps | No global guarantee |
| Weak | Only converges at sync points, possible stale reads | Caches, logs | Maximum scalability, lowest guarantees |