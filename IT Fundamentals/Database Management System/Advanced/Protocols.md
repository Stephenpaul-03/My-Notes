## **Two-Phase Commit Protocol (2PC)**

- 2PC is a **blocking atomic commitment protocol** designed to ensure all nodes in a distributed system either all commit or all abort a transaction. It’s a **strong consistency mechanism**, but it sacrifices availability in the presence of failures.

**Phases:**

- **Phase 1: Prepare (Voting Phase)**
    - The **coordinator** sends a `prepare` request to all **participants**.
    - Each participant executes the transaction up to the commit point and writes to a **temporary log**.
    - Participants respond with `vote-commit` or `vote-abort`.
- **Phase 2: Commit/Abort (Decision Phase)**
    - If **all** vote `commit`, the coordinator sends a `global-commit` request.
    - If **any** vote `abort`, the coordinator sends a `global-abort`.
    - All participants then complete the commit or abort operation accordingly.

**Drawbacks:**

- **Blocking:** If the coordinator crashes after Phase 1, participants that voted `commit` are in a **blocked state**, awaiting decision.
- **No timeout safety:** Requires manual recovery or timeout-based failure handling, making it unsuitable for large-scale, real-time systems.

## **Three-Phase Commit Protocol (3PC)**

- 3PC is a **non-blocking atomic commitment protocol**, designed to overcome the blocking limitation of 2PC. It introduces an additional phase to ensure that no participant remains in an uncertain state indefinitely.

**Phases:**

- **Phase 1: CanCommit (Preparation)**
    - Similar to 2PC’s prepare phase. Coordinator asks if participants can commit.
    - Participants respond with `yes` or `no`.
- **Phase 2: PreCommit**
    - If all vote `yes`, coordinator sends `pre-commit` and logs this.
    - Participants acknowledge and prepare to commit, but don’t actually commit yet.
    - This ensures that they are ready, and no failure will prevent eventual commit.
- **Phase 3: DoCommit**
    - Coordinator sends `do-commit` to complete the transaction.

**Improvements Over 2PC:**

- **Non-blocking:** Participants can use timeout and state knowledge to autonomously decide whether to commit or abort if the coordinator crashes.
- **Safer failure recovery:** Each state is designed to be safe for recovery decisions.

**Drawbacks:**

- **Higher overhead:** Additional communication and logging.
- **More complex implementation.**

## **Distributed Transactions**

- A **distributed transaction** is a transaction that spans across multiple networked nodes or databases, ensuring **ACID (Atomicity, Consistency, Isolation, Durability)** properties across systems.

**Key Characteristics:**

- **Atomicity:** All sub-transactions must commit or abort as one logical unit.
- **Consistency:** Ensures integrity constraints are preserved across distributed systems.
- **Isolation:** Transactions appear to execute in isolation.
- **Durability:** Once committed, the outcome persists even in failure.

**Implementation Technologies:**

- XA (eXtended Architecture)
- JTA (Java Transaction API)
- gRPC with Saga patterns or event-driven choreography for microservices

**Challenges:**

- Network partitions, latency, coordination complexity
- Risk of distributed deadlocks
- Needs consensus protocols (e.g., Paxos, Raft) in leaderless environments

**Real-World Relevance:**

- Essential for financial services, inventory systems, distributed DBMS (e.g., CockroachDB, Spanner)

## **Nested Transactions**

- Nested transactions allow a **hierarchical transaction model**, where a parent transaction can spawn multiple sub-transactions. If a sub-transaction fails, the parent can decide to retry, abort it selectively, or abort the entire transaction.

**Execution Semantics:**

- **Sub-transactions** are fully isolated and atomic within the scope of the parent.
- Commit of sub-transactions is **tentative** until the parent commits.
- Rollback of parent causes rollback of all sub-transactions.

**Types:**

- **Closed Nested Transactions:** Sub-transactions' effects are visible only after parent commits.
- **Open Nested Transactions:** Sub-transactions can expose effects early; used for long-lived transactions (common in workflow systems).

**Use Cases:**

- Complex operations in database systems (e.g., savepoints)
- Long-running business processes
- Fault-tolerant retries within distributed systems

**Advantages:**

- Improved modularity and fault tolerance
- Supports partial rollback and local recovery

**Limitations:**

- Higher system complexity
- Coordination overhead increases with depth
