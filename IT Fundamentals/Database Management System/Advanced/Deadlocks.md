## **Deadlocks**

- A **deadlock** is a situation in a multi-user database environment where two or more transactions are unable to proceed because each is waiting for a resource held by the other(s).
- This leads to a **circular wait** condition where no transaction can complete, effectively halting system progress unless external intervention occurs.

## **Core Characteristics**

A deadlock arises when the following **four Coffman conditions** are present simultaneously:

1. **Mutual Exclusion**
    - At least one resource must be held in a non-shareable mode; only one transaction can access the resource at a time.
    
2. **Hold and Wait**
    - A transaction holding at least one resource is waiting to acquire additional resources that are currently being held by other transactions.
    
3. **No Preemption**
    - Resources cannot be forcibly removed from the transactions holding them; they must be released voluntarily.
    
4. **Circular Wait**
    - A closed chain of transactions exists, where each transaction is waiting for a resource held by the next transaction in the chain.
    

## **Deadlock Handling Strategies**

There are three primary approaches to managing deadlocks:

### # **1. Deadlock Prevention**

**Objective**: Avoid one or more of the necessary conditions for deadlock.
**Best for**: Large-scale, high-throughput systems where predictability and control are critical.

**Techniques**:

- **Wait-Die Scheme**
    - Based on transaction timestamps. Older transactions wait; younger ones are aborted (die).
    
- **Wound-Wait Scheme**
    - Older transactions preempt (wound) younger ones by forcing them to roll back. Younger transactions must wait for older ones to release the resource.
    
- **Resource Ordering**
    - Impose a global order on resource acquisition to avoid circular waits.
## # **2. Deadlock Avoidance**

**Objective**: Dynamically ensure that the system will not enter a deadlock state.
**Best for**: Smaller systems where tracking transaction states is computationally feasible.

**Techniques**:

- **Application Consistent Logic**
    - Developers enforce logic to acquire and release resources in a fixed order to avoid cycles.
    
- **Row-Level Locking + READ COMMITTED Isolation**
    - Reduces lock duration and contention, thus minimizing the chance of deadlocks.
    
- **Wait-For Graph (WFG)** Simulation (in some avoidance approaches)
    - Predict the consequences of resource allocation and only allow it if no deadlock will result.
    
## # **3. Deadlock Detection and Resolution**

**Objective**: Allow deadlocks to occur but detect and resolve them afterward.
**Best for**: Systems where avoiding or preventing deadlocks is too restrictive or expensive.

**Technique**:

- **Wait-For Graph (WFG)**
   - A directed graph where transactions are nodes and edges represent waiting for resources. A cycle in the graph indicates a deadlock.
    
**Resolution Strategy**:

- **Transaction Rollback**

    - Once a deadlock is detected, one or more transactions in the cycle are rolled back to break the cycle. Victim selection can be based on:
	    - Least cost of rollback
	    - Priority or age of the transaction
	    - Resource usage