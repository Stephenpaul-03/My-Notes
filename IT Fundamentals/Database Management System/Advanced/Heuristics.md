## **Definition**

- **Heuristic Optimization** applies predefined **rules of thumb** or **empirical strategies** to rapidly generate a "good enough" execution plan.

## **Purpose**

Heuristic optimization accelerates the query planning phase by simplifying the decision space through general heuristics derived from prior knowledge or observed patterns. It’s particularly useful in:

- Reducing the **search space** of possible execution plans.
- Providing **real-time responsiveness** for complex or ad hoc queries.
- Serving as a **pre-optimization phase** before cost-based optimization.
    
## **Key Components of Heuristic Optimization**

### **Cost-Based Heuristics**

While not full cost-based optimization, heuristics often include basic **cost estimations** to guide decisions:
- Utilizes statistical metadata (e.g., row counts, index selectivity).
- Applies simplified models to estimate **I/O**, **CPU**, and **memory usage**.
- Avoids high-cost operations like full table scans when indexed access is viable.
- Example: Avoid nested-loop joins for large datasets; prefer hash joins or merge joins when cardinalities are high.
    
### **Join Order Heuristics**

Join order significantly impacts query performance, especially in multi-table joins.
- **Greedy heuristics** select the next join based on local optimization (e.g., smallest intermediate result).
- Prioritize joining **small** or **highly selective** tables early.
- Minimize intermediate result sizes to reduce memory and I/O costs.
- Example Rule: "Perform selection operations before joins; perform projection operations early to reduce tuple size."
### **Index Selection Heuristics**

Heuristics guide the optimizer to leverage existing indexes effectively:
- Evaluate **index availability**, **selectivity**, and **column coverage**.
- Prefer access paths using **clustered indexes** or **covering indexes**.
- Avoid indexes on low-selectivity columns for large tables.
- Example: "Use indexes for equality and range predicates; avoid indexes if a table scan would be cheaper."
    
### **Query Rewriting Heuristics**

Rewriting a query into a logically equivalent but more efficient form is a key strategy:

- **Predicate pushdown:** Move filters closer to the data source. 
- **Subquery flattening:** Convert correlated subqueries into joins.
- **Redundant join elimination:** Remove joins that do not affect the result.
- Example Rule: "Push selections down the expression tree to reduce data volume early."
    

## **Advantages**

- **Fast compilation time** – avoids exhaustive plan enumeration.
- **Reduced complexity** – applies simple, well-defined transformation rules.
- **Good baseline performance** – yields near-optimal plans in many practical scenarios.
- **Scalable for large queries** – avoids combinatorial explosion in join enumeration.

## **Limitations**

- May **miss the optimal plan**, especially in edge cases.
- Not adaptive – doesn't consider actual runtime data unless hybridized with cost-based methods.
- Rule conflicts – heuristics may lead to suboptimal decisions if misapplied.