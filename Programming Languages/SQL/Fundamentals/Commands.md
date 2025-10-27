## **SQL Command Types**

| Type | Full Form                    | What It Does                                 |
| ---- | ---------------------------- | -------------------------------------------- |
| DDL  | Data Definition Language     | Create or modify structure (tables, schemas) |
| DML  | Data Manipulation Language   | Change actual data (rows) inside tables      |
| DCL  | Data Control Language        | Manage access, privileges                    |
| TCL  | Transaction Control Language | Handle commits, rollbacks, and transactions  |
| DQL  | Data Query Language          | Fetch the data                               |
## **DDL - Data Definition Language**

| Command    | Description                                                           |
| ---------- | --------------------------------------------------------------------- |
| `CREATE`   | Make a new table, view, DB, index, etc.                               |
| `ALTER`    | Modify existing table (add/drop/rename columns, constraints)          |
| `DROP`     | Delete a table, view, DB, index permanently                           |
| `TRUNCATE` | Wipe all rows in a table ; Cannot be rolled back ; Resets table state |
| `RENAME`   | Change the name of a table or column                                  |
| `COMMENT`  | Add a comment to a table or column (DB-specific)                      |
### Examples

```sql
CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(255) UNIQUE
);

ALTER TABLE users ADD COLUMN age INT;
DROP TABLE users;
TRUNCATE TABLE users;
RENAME TABLE orders TO customer_orders;

-- TRUNCATE is non-reversible.
```
## **DML - Data Manipulation Language**

These commands **change the data** inside tables, not the structure.

| Command  | Description                                                                   |
| -------- | ----------------------------------------------------------------------------- |
| `INSERT` | Add new rows into a table                                                     |
| `UPDATE` | Change values in existing rows                                                |
| `DELETE` | Remove rows (can use `WHERE`); Can be Rolled Back; Does not Reset table state |
### Examples

```sql
INSERT INTO users (id, name) VALUES (1, 'Ava');

UPDATE users SET name = 'Avani' WHERE id = 1;

DELETE FROM users WHERE id = 1;

```
## **DCL -  Data Control Language**

This is the **permissions** department. Who can do what?

| Command  | Description                         |
| -------- | ----------------------------------- |
| `GRANT`  | Give privileges (read, write, etc.) |
| `REVOKE` | Take away privileges                |
### Examples

```sql
GRANT SELECT, INSERT ON employees TO hr_user;

REVOKE INSERT ON employees FROM hr_user;

```
## **TCL - Transaction Control Language**

| Command           | Description                                           |
| ----------------- | ----------------------------------------------------- |
| `COMMIT`          | Save all changes made in transaction                  |
| `ROLLBACK`        | Undo changes made in the current transaction          |
| `SAVEPOINT`       | Set a checkpoint to rollback to later                 |
| `SET TRANSACTION` | Define transaction properties (isolation level, etc.) |
### Examples

```sql
BEGIN;

UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;

COMMIT; -- or ROLLBACK if something breaks

```
## **DQL - Data Query Language**

| Command  | Description                    |
| -------- | ------------------------------ |
| `SELECT` | Pull data from a table or view |
### Examples

```sql
SELECT * FROM users;
SELECT name, age FROM employees WHERE age > 30;

```
## Honorable Mentions (DB-specific / Admin level stuff)

| Command              | Description                           |
| -------------------- | ------------------------------------- |
| `USE dbname`         | Switch current database               |
| `SHOW`               | View schemas, tables, columns (MySQL) |
| `DESCRIBE tablename` | Show structure of a table             |
| `EXPLAIN`            | See query execution plan              |
| `LOCK/UNLOCK TABLES` | Control read/write access manually    |
