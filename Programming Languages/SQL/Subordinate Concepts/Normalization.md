## Definition

- Database normalization is the process of organizing the attributes of the database to reduce or eliminate data redundancy
- Data redundancy unnecessarily increases the size of the database as the same data is repeated in many places.
- Standard methods to quantify how efficient a databases is.
## First Normal Form (1NF)

- A Table is in 1NF if and only if
    - **Atomicity**: Each cell holds **only one value** (no arrays, lists, or nested tables).
    - **Homogeneity**: All values in a column are of the **same data type**.
    - **Uniqueness of Columns**: Each column has a **unique name**.
    - **Irrelevance of Row Order**: The sequence of rows and columns **does not affect** the table's meaning.

## Second Normal Form (2NF)

- A Table is in 2NF if and only if
    - It is already in **1NF**.
    - **Every non-prime attribute** is **fully functionally dependent** on the **entire primary key** (i.e., no partial dependency).
    - Occurs when a non-key attribute is functionally dependent on only a portion of a composite primary key, not the entire key.
## Third Normal Form (3NF)

- A table is in **3NF** if:
    - It is already in **2NF**.
    - There is **no transitive dependency** — non-prime attributes do not depend on **other non-prime attributes**.    
    - occurs when a non-key attribute's value depends on another non-key attribute, which in turn depends on the primary key    
## Boyce-Codd Normal Form (3.5NF)

- A table is in **BCNF** if:
    - It is in **3NF**.
    - **Every determinant is a candidate key**.
    - A determinant is any attribute or group of attributes on which some other attribute is fully functionally dependent.
## Forth Normal Form (4NF)

- A table is in **4NF** if:
    - It is in **BCNF**.
    - It has **no multivalued dependencies**.
    - A multivalued dependency exists when two or more independent sets of attributes apply to the same key.
### Fifth Normal Form (5NF)

- A table is in **5NF** if:
    - It is in **4NF**.
    - It cannot be further **decomposed into smaller relations** without **losing data** or **introducing redundancy**.
    - Every join dependency is implied by candidate keys.
    - Deals with reconstructing information using **lossless joins** from complex decompositions.
