## **Basic Operators**

### # **Selection (σ)**

- Filters rows from a relation based on a specified condition.
- Syntax: `σ<condition>(Relation)`
- Example: `σ age > 30 (Employee)`

### **# Projection (π)**

- Extracts specific columns (attributes) from a relation.
- Removes duplicate rows by default.
- Syntax: `π<attribute list>(Relation)`
- Example: `π name, age (Employee)`

### **# Union (U)**

- Combines rows from two relations and removes duplicates.
- Conditions:
    - Both relations must have the **same number of attributes**.
    - Corresponding attributes must be of **compatible data types**.
- Syntax: `Relation1 ∪ Relation2`

### **# Set Difference (-)**

- Retrieves rows present in the first relation but not in the second.
- Syntax: `Relation1 − Relation2`

### **# Rename (ρ)

- Renames the relation or its attributes.
- Syntax:
    - `ρ newName(Relation)`
    - `ρ newName(attribute1, attribute2, ...)(Relation)`

### **# Cross Product (X)**

- Produces the Cartesian product of two relations.
- Every row in the first relation is paired with every row in the second.
- Syntax: `Relation1 × Relation2`

## **Derived Operator**

### **# Join**

- Combines related rows from two relations based on a condition.
- Types
    - **Inner Join**
        - Returns rows where a match exists in both relations.
        - Syntax: `Relation1 ⨝<condition> Relation2`
        - Types
            - **Equi Join**: Condition uses only equality (`=`).
            - **Natural Join**: Automatically joins on all attributes with the same name; removes duplicate columns.
            - **Theta Join (Conditional Join)**: Uses general comparison operators (`=`, `>`, `<`, `≠`, etc.).
    - **Outer Join**
        - Returns matching rows plus unmatched rows with `NULL`s from one or both relations.
        - Types
            - **Left Outer Join (⟕)**: All rows from left + matched from right.
            - **Right Outer Join (⟖)**: All rows from right + matched from left.
            - **Full Outer Join (⟗)**: All rows from both; unmatched parts padded with `NULL`.

### **# Set Intersection (∩)**

- Returns rows that exist in both relations.
- Syntax: `Relation1 ∩ Relation2`

### **# Division (÷)**

- Returns tuples from one relation that are associated with **all** tuples in another.
- Useful for queries like “find students enrolled in all courses”.
- Example:
    - `R(A, B)` ÷ `S(B)` returns all `A` such that for **every** `B` in `S`, the pair `(A, B)` is in `R`.
