## **Dependency Preserving Decomposition**

A dependency preserving decomposition ensures that all functional dependencies in the original relation can still be enforced in the decomposed relations without requiring a join of the tables.

### **# Reason**

- During normalization, it is crucial to retain all integrity constraints within the smaller tables.
- If a decomposition does not preserve dependencies, enforcing certain constraints may require recombining the decomposed tables.

### **# Formal Condition**

- Let the original relation be **R** with a set of functional dependencies **F**, and let **R₁, R₂, ..., Rₙ** be the decomposed relations with corresponding dependencies **F₁, F₂, ..., Fₙ**.
- The decomposition is **dependency preserving** if the closure of all dependencies in the decomposed relations is equal to the closure of the original set. That is:

  - (F₁ ∪ F₂ ∪ ... ∪ Fₙ)⁺ = F⁺

### **# Example**

- Original relation: `R(A, B, C)`
- Functional dependencies: `F = {A → B, B → C}`
- Decomposition: `R₁(A, B)` and `R₂(B, C)`

This decomposition is dependency preserving because all functional dependencies can be enforced without recombining the relations.

## **Lossless Decomposition (Lossless Join)**

### **# Definition**

A lossless decomposition ensures that no information is lost when a relation is split into two or more parts and then joined back.

It guarantees that the natural join of the decomposed tables will exactly recreate the original relation.

### **# Importance**

If a decomposition is not lossless, joining the decomposed relations may produce spurious tuples or omit valid ones, leading to data corruption.

### **# Formal Condition**

A decomposition of relation **R** into **R₁** and **R₂** is **lossless** with respect to a set of functional dependencies **F** if at least one of the following holds:

- `(R₁ ∩ R₂) → R₁` is in **F⁺**, or
- `(R₁ ∩ R₂) → R₂` is in **F⁺**

This means the common attributes between the relations must functionally determine all attributes in at least one of the decomposed relations.

### **# Example**

- Original relation: `R(StudentID, CourseID, Instructor)`
- Functional dependency: `{StudentID, CourseID} → Instructor`
- Decomposed into: `R₁(StudentID, CourseID)` and `R₂(StudentID, Instructor)`

This decomposition is **lossy** because joining **R₁** and **R₂** could produce invalid combinations of `CourseID` and `Instructor` unless `Instructor` is functionally dependent on `StudentID` alone, which it is not.

## **Lossless Join and Dependency Preserving Decomposition**

### **# Ideal Scenario**

The optimal decomposition is one that is **both lossless and dependency preserving**.

### **# Why Both Are Important**

- **Lossless join** ensures that the original relation can be accurately reconstructed from the decomposed tables.
- **Dependency preservation** ensures that all functional dependencies can be enforced without recombining the relations.

### **# Trade-Off**

- **Third Normal Form (3NF)** allows both **lossless join** and **dependency preservation**.
- **Boyce-Codd Normal Form (BCNF)** always guarantees a **lossless join**, but may not preserve all dependencies.

## **# Analogy**

- A **lossless join** is like breaking a document into pages and being able to perfectly reassemble the original.
- **Dependency preservation** is like keeping all the formatting and rules for how the content is structured.
- If the document cannot be reassembled exactly — the decomposition is **lossy**.
- If some formatting rules are lost — the decomposition is **not dependency preserving**.
