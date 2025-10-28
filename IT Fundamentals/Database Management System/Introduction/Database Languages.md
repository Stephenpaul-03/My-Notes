## # **Data Definition Language (DDL)**

- Deals with database schemas and descriptions, of how the data should reside in the database.
- Commands:
    - **CREATE:** to create a database and its objects like table, index, views, store procedure, function, and triggers.
    - **ALTER:** alters the structure of the existing database
    - **DROP:** delete objects from the database
    - **TRUNCATE:** remove all records from a table, including all spaces allocated for the records are removed
    - **COMMENT:** add comments to the data dictionary
    - **RENAME:** rename an object

## # **Data Manipulation Language (DML)**

- Focuses on manipulating the data stored in the database
- Commands:
    - **SELECT:** retrieve data from a database
    - **INSERT:** insert data into a table
    - **UPDATE:** updates existing data within a table
    - **DELETE:** Delete all records from a database table
    - **MERGE:** UPSERT operation (insert or update)
    - **CALL:** call a PL/SQL or Java subprogram
    - **EXPLAIN PLAN:** interpretation of the data access path
    - **LOCK TABLE:** concurrency Control

## # **Data Control Language (DCL)**

- Manage access permissions
- Commands:
    - **GRANT**: Provides specific privileges to a user (e.g., SELECT, INSERT).
    - **REVOKE**: Removes previously granted permissions from a user.

## # **Transaction Control Language (TCL)**

- Oversee transactional data
- Commands
    - **ROLLBACK**: Undoes changes made during a transaction.
    - **COMMIT**: Saves all changes made during a transaction.
    - **SAVEPOINT**: Sets a point within a transaction to which one can later roll back.

## # **Data Query Language (DQL)**

- Subset of DML, specifically focused on data retrieval
- Command:
    - **SELECT**: used to query data from the database without altering its structure or contents.