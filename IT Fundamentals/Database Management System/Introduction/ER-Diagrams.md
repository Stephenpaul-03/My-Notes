## **Definition**

- The Entity Relationship Model is a model for identifying entities to be represented in the database and representation of how those entities are related.

## **# Components Basics**

- Entity
    - An entity is an object that exists and is distinguishable from other objects.
    - It can be **tangible** (e.g., a person, car) or **intangible** (e.g., job, course).
- Entity Type
    - A collection or class of entities that share the same attributes.
    - Defines a set of entities with common structure.
- Entity Set
    - Collection of all entities of a particular type is called an entity set
- Attribute
    - A property or characteristic of an entity (e.g., name, age).
    - Attributes define the entity type.
- Relationship
    - An association among two or more entities.
- Participation
    - Describes whether **all** or **only some** entities participate in a relationship.
        - **Total Participation:** Every entity in the set must be involved in at least one relationship.
        - **Partial Participation:** Some entities may not be involved in any relationship.

## **# Symbols**

| Symbol | Meaning |
| --- | --- |
| **Rectangle** | Entity |
| **Double Rectangle** | Weak Entity |
| **Ellipse** | Attribute |
| **Double Ellipse** | Multivalued Attribute |
| **Dashed Ellipse** | Derived Attribute |
| **Diamond** | Relationship |
| **Double Diamond** | Identifying Relationship (for weak entities) |
| **Line** | Connects attributes to entities or entities to relationships |

## **Components Explained**

![image.png](IT%20Fundamentals/Database%20Management%20System/Introduction/Images/image.png)

### # **Entity**

- an object with a physical existence or conceptual existence
    - **Strong Entity**
        - Has a **primary key** (unique identifier).
        - Does **not** depend on another entity for its existence.
        - Represented by a **single rectangle**.
    - **Weak Entity**
        - **Lacks a primary key**.
        - Depends on a **strong entity** for identification.
        - Has **total participation** in an **identifying relationship**.
        - Represented by a **double rectangle**.
        - Identifying relationship is shown by a **double diamond**.

### # **Attribute**

- properties that define the entity type
    - **Key Attribute**
        - uniquely identifies each entity
        - represented by an oval with underlying lines
        
        ![image 2.png](./images/Image1.png)
        
    - **Composite Attribute**
        - composed of many other attributes
        - represented by an oval comprising of ovals
        
        ![image.png](image2.png)
        
    - **Multivalued Attribute**
        - more than one value for a given entity
        - represented by a double oval
        
        ![image.png](image3.png)
        
    - **Derived Attribute**
        - can be derived from other attributes of the entity type
        - represented by a dashed oval
        
        ![image.png](image4.png)
        

### # **Relationship**

- One to One
    - One entity in A is related to only one entity in B and vice versa.
- One to Many
    - One entity in A can be related to **many** in B, but each B is related to only **one** in A.
- Many to One
    - Many entities in A are related to **one** in B.
- Many to Many
    - Many entities in A can be related to many in B.

### # **Cardinality**

- The **number of instances of one entity** that can or must be associated with each instance of another entity.
- **Types:**
    - **One-to-One (1:1)**
    - **One-to-Many (1:N)**
    - **Many-to-One (N:1)**
    - **Many-to-Many (M:N)**
- **Notation:** Often shown using crow’s foot notation or simply numbers (1, N) on the lines connecting entities.

## **# Degree of Relationship**

- The **number of entity types** involved in a relationship.
- Types
    - **Unary (Degree 1):** Relationship between instances of the **same entity set.**
    - **Binary (Degree 2):** Most common; involves **two entity sets**.
    - **Ternary (Degree 3):** Involves **three different entity sets.**

## **Other Concepts**

### **# Generalization (Bottom Up Approach)**

- Combines **multiple entity sets** with common features into a **single higher-level entity set**.
- Common attributes are promoted to the generalized entity.
- **Attribute inheritance** applies.

![image.png](image5.png)

### **# Specialization (Top Down Approach)**

- A **single entity set** is divided into **subsets** based on distinct attributes.
- Subsets inherit attributes of the parent entity.
- Has **participation inheritance**.

![image.png](image6.png)

## **# Aggregation**

- A relationship can itself be treated as a **higher-level entity**.
- Used when a **relationship** needs to be involved in another relationship.

![image.png](image7.png)

## **# Recursive/Repeated Relationship**

- A **recursive relationship** occurs when an entity set participates more than once in the **same relationship**, often with **different roles**

## **# Cardinality Ratio**

- Often used **in combination with participation** to define the constraints of relationships.

## **# Identifying vs. Non-identifying Relationships**

- **Identifying Relationship**
    - Used when a **weak entity** is related to its **owner entity**.
    - The relationship contributes to the weak entity’s primary key.
- **Non-identifying:**
    - Regular relationships where entities are **independent**.

## **# **Disjointness Constraint****

- Specifies whether an entity instance can belong to **more than one** subclass.
    - **Disjoint**: An instance **belongs to only one** subclass (default).
    - **Overlapping**: An instance **may belong to multiple** subclasses.

## **# **Completeness Constraint****

- Specifies whether all instances of a superclass **must** be part of some subclass.
    - **Total**: Every entity **must** be a member of at least one subclass.
    - **Partial**: Some entities **may not** belong to any subclass.