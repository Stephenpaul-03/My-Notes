## **Definition**

- **Data modelling** is the process of creating a structured, visual representation of data and its organizational rules within a system.
- It outlines how data is stored, interconnected, and accessed, providing a foundational blueprint for database and application development.
- This structured approach ensures the consistency, accuracy, and efficiency of data-driven systems.

## **Purposes and Importance**

- **Clarifies requirements:**
    - Translates business rules into precise specifications.
- **Improves data quality:**
    - Identifies inconsistencies and redundancies, leading to better integrity and reliability.
- **Optimizes performance:**
    - Enables efficient data retrieval and storage mechanisms.
- **Reduces redundancy:**
    - Ensures a single version of data, minimizing unnecessary duplication.
- **Supports scalability:**
    - Lays groundwork for future growth in data size or complexity.
- **Enhances communication:**
    - Serves as a shared reference for developers, analysts, and stakeholders.

## **Levels of Data Modelling**

| Level | Focus | Purpose | Example Artifacts |
| --- | --- | --- | --- |
| Conceptual | High-level structure, key entities | Business understanding | Entity-Relationship diagrams |
| Logical | Detailed structure, attributes, rules | Data organization (system-agnostic) | Logical ER diagrams |
| Physical | Implementation specifics (storage, indexes) | Actual DBMS schema | Relational tables, keys |

- **Conceptual Model:**
    - Outlines core entities and their relationships, abstracted from technical details.
- **Logical Model:**
    - Adds attributes, data types, and detailed relationships
    - Platform independent.
- **Physical Model:**
    - Specifies how data is physically stored in a specific database system (e.g., tables, indexes, constraints).

## **Common Types of Data Models**

| Model Type | Description | Best For |
| --- | --- | --- |
| Hierarchical Model | Tree structure with parent-child relationships | Organization charts, file systems |
| Network Model | Flexible graph with record sets and many-to-many relationships | Telecom, complex networks |
| Relational Model | Tables with rows and columns and strict relationships (keys) | OLTP systems, transactional data |
| Entity-Relationship | Visualizes entities, attributes, and relationships | Logical database design |
| Object-Oriented | Structures and behaviors encapsulated as objects | Applications using complex objects |
| Document/NoSQL | Stores data as JSON/XML documents, schema-less | Flexible, scalable applications |
| Star/Snowflake Schema | Fact and dimension tables for analytics | Data warehouses, OLAP reporting |
| Graph Model | Nodes and edges to capture highly connected data | Social networks, recommendation engines |
| Time Series/Columnar | Optimized for time-stamped or column-based analytics | Sensor data, financial data |
| Multi-Model | Supports various models within one system (e.g., graph + document) | Modern, flexible systems |

## **Data Modelling Techniques**

- **Normalization:**
    - Eliminates redundancy by structuring data into related tables, supporting OLTP systems.
- **Denormalization:**
    - Adds redundancy strategically for fast queries, common in data warehousing.
- **Entity-Relationship (ER) diagrams:**
    - Visual tools for mapping entities, attributes, and relationships.
- **Dimensional Modelling:**
    - Organizes data into facts and dimensions, suited for analytics and BI.

## **Process**

1. **Requirements Gathering:** 
    1. Understand stakeholder needs.
2. **Conceptual Modelling:** 
    1. Identify key entities and relationships.
3. **Logical Modelling:** 
    1. Define attributes, relationships, and business rules.
4. **Physical Modelling:** 
    1. Translate logical model into tables and indexes.
5. **Implementation & Testing:** 
    1. Build and validate the actual database, making adjustments as needed.