## **Relational Models**

- The **Relational Model** is a fundamental concept in Database Management Systems (DBMS) that organizes data into tables, also known as relations by using rows and columns

## **# Terminologies**

- **Relational Database**
    - A database structured to recognize relations among stored items of information. It uses tables (relations), which consist of rows (tuples) and columns (attributes).
- **Table (Relation)**
    - A collection of rows (tuples) and columns (attributes), organized to represent data. Each table typically corresponds to an entity or concept in the database (e.g., Customers, Orders).
- **Row (Tuple)**
    - A single, data record in a table, typically representing one instance of the entity the table describes (e.g., one customer or one order).
- **Column (Attribute)**
    - A single field within a table that holds a specific type of data (e.g., Customer Name, Order Date). Each column has a specific data type, such as integer, varchar, date, etc.
- **Relation Schema**
    - The structure that defines the organization of a table, including the table's name and its attributes (columns).
- **Domain**
    - The set of permissible values for a given attribute. For example, the domain of a "Gender" attribute might be restricted to "Male" and "Female."
- **Tuple**
    - Another term for a row in a table. It is an ordered set of values, each corresponding to an attribute in a relation.
- **Cardinality**
    - The number of tuples (rows) in a relation (table). For example, if there are 100 rows in a table, the cardinality is 100.
- **Degree**
    - The number of attributes (columns) in a relation (table). For example, a table with five columns has a degree of five.
- **Normalization**
    - The process of organizing data to reduce redundancy and improve data integrity. It involves decomposing a table into smaller tables and defining relationships between them.
- **Denormalization**
    - The process of combining tables or adding redundancy for performance improvements, often at the cost of normalization principles.
- **Dependency**
    - A relationship between attributes in a table, where one attribute depends on another. For example, in a functional dependency, one attribute’s value is determined by another attribute.
- **Join**
    - An operation that combines data from two or more tables based on a related column, usually a foreign key to primary key relationship.
- **View**
    - A virtual table that results from a query. It does not store data physically but presents data from one or more tables.
- **Schema**
    - The structure that defines the organization of data within a database, including tables, relationships, views, and constraints.
- **Constraints**
    - Constraints are rules that enforce data integrity and consistency within a database
- **Relational Algebra**
    - A procedural query language that operates on relations (tables). It provides basic operations such as selection, projection, union, and join.
- **Relational Calculus**
    - A non-procedural query language that provides a way to specify queries based on mathematical logic. It is declarative, unlike relational algebra, which is procedural.
- **Transaction**
    - A sequence of operations performed on a database that must be completed successfully as a unit. A transaction is atomic, consistent, isolated, and durable (ACID properties).
- **ACID Properties**
    - The four properties of a transaction that guarantee database reliability: Atomicity (all or nothing), Consistency (valid state transitions), Isolation (independent transactions), and Durability (persistent results).

## # **Types of Keys**

- A key is an attribute or a set of attributes that uniquely identifies a record (row) in a table

1. **Primary Key**
    - A primary key is a unique identifier for a record in a table. It cannot contain NULL values and ensures each record can be uniquely identified.
2. **Alternative Key**
    - An alternative key is any candidate key that is not chosen as the primary key. It is still unique, but it is not the main way to identify records.
3. **Candidate Key**
    - A candidate key is a column (or a set of columns) that can uniquely identify a record in a table. Every table can have one or more candidate keys.
    - **A candidate key** could potentially be any key that uniquely identifies a record, but only one key can become the **primary key**.
4. **Composite Key**
    - A composite key is a primary key made up of two or more columns to uniquely identify a record in a table.
5. **Super Key**
    - A super key is any set of columns that can uniquely identify a record. A super key can contain extra attributes (compared to a candidate key), but it still guarantees uniqueness.
6. **Foreign Key**
    - A foreign key is a column (or set of columns) in a table that refers to the primary key in another table. It creates a link between two tables.

## # **Types of Anomalies**

- Anomalies refer to inconsistencies or errors that can arise when working with relational databases

- **Insertion Anomalies**
    - Insertion anomalies occur when there is difficulty adding new data due to the structure of the table. This often happens when certain attributes are dependent on others.
- **Deletion Anomalies**
    - Deletion anomalies occur when removing data causes unintended loss of other related data. For example, deleting a record could also unintentionally remove important information.
- **Update Anomalies**
    - Update anomalies happen when there is inconsistency in the data. This can occur when a change needs to be made in multiple places, but one or more are missed, causing inconsistency.

## **# Types of Constraints**

- Constraints define limitations and requirements that data must meet, preventing the entry of invalid or inconsistent data.

- Domain Constraints
    - Define the valid values that an attribute (column) can hold.
    - Specify the data type (e.g., integer, string, date) and any additional restrictions (e.g., range of values, allowed patterns).
    - Types
        - **Check Constraint:** A check constraint is a way to enforce certain conditions on the values that are stored in a database as It is a rule or condition that is specified at the time of table creation or alteration to restrict the values that can be inserted or updated in a column.
            
            ```sql
            CREATE TABLE TableName (
                Column1 DataType,
                Column2 DataType,
                -- Other columns
                CONSTRAINT ConstraintName CHECK (condition)
            );
            ```
            
        - **Not Null Constraint:** The NOT NULL constraint is used to ensure that a column in a table cannot contain any NULL values ensuring that a column always has a value, and it cannot be left empty.
            
            ```sql
            CREATE TABLE TableName (
                Column1 DataType NOT NULL,
                Column2 DataType,
                -- Other columns
            );
            ```
            
- Key Constraints
    - A key constraint refers to a set of rules applied to one or more columns in a database table to ensure the uniqueness and integrity of data
    - Types
        - **Primary Key Constraint:** The primary key constraint ensures that the values in the specified columns are unique and not NULL.
            
            ```sql
            CREATE TABLE Students (
                StudentID INT PRIMARY KEY,
                FirstName VARCHAR(50),
                LastName VARCHAR(50),
                Age INT,
                -- Other columns
            );
            ```
            
        - **Unique Constraint:**
            - A unique constraint ensures that all values in a column or a set of columns are unique and also allows NULL which does not need to be Unique.
            
            ```sql
            CREATE TABLE Products (
                ProductID INT PRIMARY KEY,
                ProductCode VARCHAR(20) UNIQUE,
                ProductName VARCHAR(100),
                Price DECIMAL(10, 2),
                -- Other columns
            );
            ```
            
- **Foreign Key Constraint**
    - A **foreign key constraint** ensures that values in a foreign key column (or set of columns) match the values in the primary key or a unique key of another table.
        
        ```sql
        CREATE TABLE Orders (
            OrderID INT PRIMARY KEY,
            CustomerID INT,
            OrderDate DATE,
            FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
        );
        ```
        
- Entity Integrity Constraints
    - **Entity integrity** ensures that each row (or tuple) in a table can be uniquely identified by a **primary key**.
    - This means no row in a table can have a NULL value in its **primary key** fields, and every table must have a primary key.
        
        ```sql
        CREATE TABLE Customers (
            CustomerID INT PRIMARY KEY,
            CustomerName VARCHAR(100)
        );
        ```
        
- **Referential Integrity Constraints**
    - **Referential integrity** ensures that relationships between tables are consistent. It guarantees that a foreign key value in the child table must either be null or match a valid primary key value in the parent table.
    - This prevents invalid or orphaned data from being entered into a related table
        
        ```sql
        CREATE TABLE Orders (
            OrderID INT PRIMARY KEY,
            CustomerID INT,
            OrderDate DATE,
            FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID) ON DELETE CASCADE
        );
        ```
        
- **Tuple Uniqueness Constraints**
    - **Tuple uniqueness** refers to the concept that each row (tuple) in a table must be unique, meaning that no two rows can be identical.
    - The **primary key** enforces this uniqueness, but it is also ensured by any candidate key, which can uniquely identify a row.

## # **Types of Dependencies**

- A relationship between attributes in a table, where one attribute depends on another.

- **Functional Dependency**
    - A functional dependency occurs when one attribute uniquely determines another attribute. For example, if A → B, then for each value of A, there will be exactly one corresponding value of B.
- **Transitive Dependency**
    - A transitive dependency happens when one non-prime attribute is dependent on another non-prime attribute through a third attribute. If A → B and B → C, then A → C (transitive dependency).
- **Multivalued Dependency**
    - A multivalued dependency occurs when one attribute determines a set of attributes independently of other attributes in a table.
- **Join Dependency**
    - A join dependency occurs when a table can be reconstructed from the join of two or more other tables.
- **Partial Dependency**
    - A partial dependency occurs when a non-prime attribute is functionally dependent on part of a candidate key (not the whole key). This typically arises in tables with composite primary keys.
- **Trivial Dependency**
    - A trivial dependency occurs when an attribute is functionally dependent on itself or on a subset of its attributes. For example, A → A or {A, B} → A are trivial dependencies.

- Attributes which are parts of any candidate key of relation are called as prime attribute, others are non-prime attributes.

## **Codd’s Rule**

- Codd's twelve rules are a set of thirteen rules (numbered zero to twelve) proposed by Edgar F. Codd that are designed to define what is required from a database management system in order for it to be considered RDBMS

- **Rule 0: The Foundation Rule**
    - **Definition**: A system can be considered relational only if it manages databases **exclusively** through its **relational capabilities**.
        
        - If a car is advertised as electric, it must run entirely on electricity—not partly on gasoline.
        
- **Rule 1: The Information Rule**
    - **Definition**: All data in a relational database must be represented **only as values in tables**.
        
        - Like storing all financial records only in spreadsheets—no handwritten notes, sticky notes, or external ledgers.
        
- **Rule 2: Guaranteed Access Rule**
    - **Definition**: Every piece of data must be accessible using a **table name, primary key, and column name**—no hidden or inaccessible data.
        
        - Like a library where every book can be found using a combination of section (table), shelf number (key), and book title (column).
        
- **Rule 3: Systematic Treatment of Null Values**
    - **Definition**: Nulls must be handled **consistently and uniformly**, regardless of data type, and must represent **missing or inapplicable** information.
        
        - Like using a clearly defined symbol (e.g., N/A) across all forms when a value doesn’t apply, instead of leaving it blank or using random substitutes.
        
- **Rule 4: Dynamic Online Catalog Based on the Relational Model**
    - **Definition**: Metadata (data about data) must be stored in the database **as tables**, accessible using the same tools and languages as user data.
        
        - Like a self-indexing book where the index is part of the content and you can search it using the same method you use to read the book.
        
- **Rule 5: Comprehensive Data Sublanguage Rule**
    - **Definition**: There must be **one comprehensive language** (like SQL) for all database operations—data definition, manipulation, constraints, authorization, and transactions.
        
        - Like using one universal remote to control the TV, sound system, and lights—instead of needing a different remote for each.
        
- **Rule 6: View Updating Rule**
    - **Definition**: Any **view** that can theoretically be updated must be **updatable by the DBMS**.
        
        - Like being able to edit a filtered Excel view and have the original sheet reflect those changes, as long as it logically makes sense.
        
- **Rule 7: High-Level Insert, Update, and Delete**
    - **Definition**: The DBMS must allow **set-level operations** for insert, update, and delete—not just one record at a time.
        
        - Like editing multiple rows in a spreadsheet at once instead of modifying each cell individually.
        
- **Rule 8: Physical Data Independence**
    - **Definition**: Changes in the physical storage (e.g., indexing, file organization) must **not affect application programs**.
        
        - Like moving books to a new shelf in the library without changing how visitors find them in the catalog.
        
- **Rule 9: Logical Data Independence**
    - **Definition**: Changes in the logical structure (e.g., adding columns) should **not break application programs**, as long as the existing data remains usable.
        
        - Like renovating a room (adding new furniture) without needing the occupants to relearn how to use the space.
        
- **Rule 10: Integrity Independence**
    - **Definition**: Integrity constraints must be stored **within the database**, not in external programs, and should be definable using the data sublanguage.
        
        - Like traffic rules written into law and enforced everywhere, not left to each driver’s judgment or personal rulebook.
        
- **Rule 11: Distribution Independence**
    - **Definition**: Users should not need to know whether the data is stored in one place or across multiple locations.
        
        - Like using a cloud service where you don’t know (or need to know) which server your files are on—you just access them seamlessly.
        
- **Rule 12: Nonsubversion Rule**
    - **Definition**: If the system offers low-level access (record-by-record), it must **not allow bypassing integrity constraints** defined at the higher level.
        
        - Like a building where even the maintenance staff must follow fire safety rules, regardless of whether they use special service doors.