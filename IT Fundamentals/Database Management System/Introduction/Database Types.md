## **Definition**

- **Database models** are frameworks or architectures that define how data is **logically structured**, **stored**, **organized**, and **accessed** in a database.
- Each model represents data, relationships, constraints, and operations in a unique way, tailored to specific types of applications or data requirements.

## # 1. **Hierarchical Model**

- **Structure:** Data is organized into a tree-like structure with **parent-child** relationships.
- **Access:** One-to-many relationships (each parent has many children, but each child has only one parent).
- **Example:** IBM's IMS (Information Management System).

- Like a company org chart — CEO → Manager → Employee.

## # 2. **Network Model**

- **Structure:** Similar to hierarchical, but allows **many-to-many** relationships via graph structures.
- **Access:** More flexible with complex relationships; data is connected through **pointers**.
- **Example:** CODASYL model.

- Like a transportation map where cities (nodes) are connected by many routes (edges).

## # 3. **Relational Model**

- **Structure:** Data is stored in **tables (relations)** with rows and columns.
- **Access:** Uses SQL for querying; supports operations like SELECT, INSERT, UPDATE, DELETE.
- **Example:** MySQL, PostgreSQL, Oracle DB.

- Like an Excel sheet where each sheet is a table, and rows are records.

## # 4. **Object-Oriented Model**

- **Structure:** Data is stored as **objects**, similar to object-oriented programming.
- **Access:** Supports inheritance, encapsulation, and polymorphism.
- **Example:** db4o, ObjectDB.

- Like programming classes — a “Vehicle” object may have subclasses “Car” or “Bike”.

## # 5. **Document Model (NoSQL)**

- **Structure:** Stores data as **documents**, typically in JSON or XML format.
- **Access:** Schema-free; flexible structure.
- **Example:** MongoDB, CouchDB.

- Like a digital filing cabinet of self-contained documents.

## # 6. **Key-Value Model (NoSQL)**

- **Structure:** Data is stored as a **collection of key-value pairs**.
- **Access:** Extremely fast lookup using the key.
- **Example:** Redis, DynamoDB.

- Like a dictionary where you look up a word (key) to find its meaning (value).

## # 7. **Column-Family Model (NoSQL)**

- **Structure:** Stores data in **column families** instead of rows, optimizing read/write for specific columns.
- **Example:** Apache Cassandra, HBase.

- Like organizing a spreadsheet by columns instead of rows.

## # 8. **Graph Model**

- **Structure:** Data is represented as **nodes (entities)** and **edges (relationships)**.
- **Access:** Best for highly interconnected data; supports graph traversal queries.
- **Example:** Neo4j, ArangoDB.

- Like a social network — people are nodes, relationships are edges.