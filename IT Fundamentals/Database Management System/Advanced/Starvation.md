## **Definition**

- **Starvation** occurs in a DBMS when certain transactions are indefinitely denied access to required resources because other transactions consistently receive higher priority. This often results from issues in locking, scheduling, or resource allocation strategies.
- Imagine waiting at a restaurant, but the waiter continually serves later-arriving VIP customers. You wait indefinitely - this mirrors starvation in databases.

## **Causes of Starvation**

1. **Unfair Prioritization**: Constant preference for high-priority tasks.
2. **Inappropriate Locking Policies**: Use of static priority queues can lock out lower-priority processes.
3. **Repeated Victimization**: Same transaction frequently selected for rollback.
4. **Queue Mismanagement**: Improper queue handling can defer older transactions indefinitely.
5. **Random Allocation**: Non-deterministic resource assignment leads to unpredictability.
6. **Resource Contention**: High demand versus limited availability.
7. **Denial-of-Service Attacks**: Malicious overloading causes legitimate transactions to starve.

## **Prevention & Mitigation Techniques**

1. **Aging (Priority Promotion)**  
   Gradually increase a transaction’s priority the longer it waits, ensuring eventual service.

2. **Fair Scheduling (FCFS)**  
   Adopt a **First-Come, First-Served** policy to avoid indefinite postponement.

3. **Wait-Die & Wound-Wait Schemes**  
   Timestamp-based protocols give older transactions higher priority, reducing starvation risk.

4. **Timeout Mechanism**  
   Terminate or restart transactions after a predefined wait period to avoid indefinite blocking.

5. **Victim Selection Logic**  
   Enhance algorithms to avoid repeatedly selecting the same transaction as a rollback victim.

6. **Resource Reservation**  
   Pre-allocate required resources to transactions before execution begins.

7. **Dynamic Lock Allocation**  
   Assign locks adaptively based on current system state to minimize resource contention.

8. **Preemption**  
   Allow critical transactions to forcibly acquire resources held by less critical ones.

9. **Parallel Execution**  
   Enable concurrent transaction processing to alleviate bottlenecks and reduce delays.

## **Techniques to Minimize Starvation**

- **Resource Allocation Policies**  
   Use policies like **round-robin** or **proportional sharing** to ensure balanced distribution.

- **Priority-Based Scheduling with Aging**  
   Prioritize urgent transactions while using aging to eventually serve lower-priority ones.

- **Timeout Enforcement**  
   Abort or restart transactions exceeding wait thresholds to maintain system flow.

- **Resource Management Controls**  
   Implement quotas and limits to prevent any single transaction from monopolizing resources.
