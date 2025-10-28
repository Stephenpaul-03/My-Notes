## # **Database Engine**

- **Core function** of the DBMS.
- Responsible for storing data, processing queries, and enforcing rules.
- Handles CRUD operations (Create, Read, Update, Delete) on the database.
- Ensures **ACID** compliance (more on this in later topics).
- Interacts directly with the **storage system** to retrieve or persist data.

## # **Query Processor**

- Translates high-level SQL queries into a series of low-level instructions that the database engine can execute.
- Performs:
    - **Parsing**: Checks syntax and validates SQL commands.
    - **Optimization**: Determines the most efficient execution plan.
    - **Execution**: Passes optimized instructions to the engine.
- Enables data retrieval and manipulation through **SQL**, ensuring efficient performance.

## # **Storage Manager**

- Manages how data is stored on physical storage (e.g., hard disks, SSDs).
- Responsible for:
    - **File organization**
    - **Page and buffer management**
    - **Data blocks and record format**
    - **Indexing mechanisms** for quick data access
- Works closely with the database engine to read/write data.

## # **Transaction Manager**

- Ensures that database transactions are processed reliably and follow the **ACID properties**:
    - **Atomicity**: A transaction is all-or-nothing.
    - **Consistency**: Transitions the database from one valid state to another.
    - **Isolation**: Transactions do not interfere with each other.
    - **Durability**: Once committed, data is permanent.
- Manages **concurrent transactions**, resolves **deadlocks**, and uses techniques like **locking** and **logging**.

## # **Metadata Catalog**

- Stores **schema-related information**: definitions of tables, views, indexes, users, and constraints.
- also known as **Data Dictionary**
- Acts as a **reference** for the DBMS to understand how data is structured.
- Automatically updated when objects are created, altered, or deleted.
- Crucial for query planning and validation.

## # **Authorization and Integrity Manager**

- **Authorization**: Manages user access and privileges (who can read/write/modify what).
- **Integrity constraints**: Enforces data rules such as:
    - **NOT NULL**
    - **UNIQUE**
    - **PRIMARY KEY**
    - **FOREIGN KEY**
    - **CHECK constraints**
- Prevents unauthorized access and ensures that data remains correct and consistent.