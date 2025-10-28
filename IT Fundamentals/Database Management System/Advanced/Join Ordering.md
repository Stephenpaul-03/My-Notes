## **Definition**

- **Join ordering** is a critical aspect of query optimization in DBMS. When a SQL query involves multiple joins, the **order in which those joins are executed** can have a **significant impact on performance** due to the intermediate result sizes and associated resource costs (I/O, CPU, memory).

## **Reason**

Consider a query with multiple tables:

```sql
SELECT *
FROM A JOIN B ON A.id = B.a_id
       JOIN C ON B.id = C.b_id;
````

- There are **multiple ways** to execute this query: `(A ⋈ B) ⋈ C` or `A ⋈ (B ⋈ C)`, and possibly more, depending on available indexes and constraints.
- The **intermediate results** from early joins can be large or small depending on **cardinality**, **selectivity**, and **predicate filters**.
- A **poor join order** can result in massive unnecessary computations and slow response time.
## **Types**

### **Exhaustive Search (Dynamic Programming)**

- Used in cost-based optimizers (e.g., Selinger-style).
- Enumerates **all possible join orders** and evaluates the cost.
- Guarantees **optimal** plan but is computationally expensive (`O(n!)` for `n` tables).
- Practical only for small numbers of joins (typically `n ≤ 6-8`).
    
### **Heuristic-Based Join Ordering**

- Applies rules of thumb to limit search space:
    - Join **smaller tables first**.
    - Apply **highly selective predicates early**.
    - Join **indexed columns** preferentially.
- Fast and scalable but **non-optimal** in some cases.

### **Greedy Algorithms**

- Builds the join plan incrementally by always choosing the **lowest cost** join at each step.
- Doesn't guarantee global optimality but performs well in practice.

## **Join Ordering Heuristics**

| Heuristic                      | Description                               |
| ------------------------------ | ----------------------------------------- |
| **Perform selections early**   | Reduces the size of the input to joins.   |
| **Join smaller tables first**  | Smaller intermediate results reduce cost. |
| **Use indexes when available** | Especially for nested loop joins.         |
| **Push join predicates down**  | Avoids cross-product or Cartesian joins.  |
| **Avoid Cartesian products**   | Unless absolutely necessary.              |

## **Role in Cost-Based Optimization**

In a **cost-based optimizer**, join ordering is integrated with:
- **Cardinality estimation** – How many rows a join will produce.
- **Selectivity estimation** – Probability that a row satisfies a condition.
- **Join algorithm selection** – Nested loop, hash join, merge join, etc.
    
## **Example**

Assume:
- `Employee (1M rows)`
- `Department (10 rows)`
- `Location (1K rows)`

```sql
SELECT *
FROM Employee E
JOIN Department D ON E.dept_id = D.id
JOIN Location L ON D.loc_id = L.id;
```

**Bad Join Order**: `Employee ⋈ (Department ⋈ Location)`

- The inner join produces a small result, but Employee is joined last, leading to massive intermediate results.

**Good Join Order**: `(Employee ⋈ Department) ⋈ Location`

- Employee is immediately filtered by Department, reducing rows before further joins.