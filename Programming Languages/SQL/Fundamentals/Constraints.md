## Definition

Constraints are **rules** enforced on table columns to maintain **data integrity** and **avoid garbage** in your DB.
## Types of Constraints

| Constraint    | Purpose                                              |
| ------------- | ---------------------------------------------------- |
| `NOT NULL`    | Prevents null (empty) values                         |
| `UNIQUE`      | Ensures all values in a column are different         |
| `PRIMARY KEY` | Uniquely identifies a row and cannot be null         |
| `FOREIGN KEY` | Connects two tables — enforces referential integrity |
| `CHECK`       | Validates values against a condition                 |
| `DEFAULT`     | Sets a default value if none is provided             |
### `NOT NULL`

Guarantees a column must have a value
```sql
CREATE TABLE users (
  id INT NOT NULL,
  name VARCHAR(100) NOT NULL
);
```
### `UNIQUE`

Ensures all values in a column are unique (no duplicates).
```sql
CREATE TABLE users (
  email VARCHAR(255) UNIQUE
);
-- `NULL` values are allowed unless also `NOT NULL`.
```
### `PRIMARY KEY`

A combo of NOT NULL + UNIQUE for identifying each row. 
```sql
CREATE TABLE users (
  user_id INT PRIMARY KEY,
  username VARCHAR(100)
);
-- can also use **composite keys**:

PRIMARY KEY (order_id, product_id)
```
Useful in many-to-many junction tables. 
### `FOREIGN KEY`

 Links one table to another — enforces referential integrity.
 ```sql
CREATE TABLE orders (
  order_id INT PRIMARY KEY,
  user_id INT,
  FOREIGN KEY (user_id) REFERENCES users(user_id)
);

```
### `CHECK`

 Ensures a value meets some custom condition.
```sql
CREATE TABLE employees (
  id INT,
  salary DECIMAL(10, 2),
  CHECK (salary > 0)
);
--- or ---
CHECK (age BETWEEN 18 AND 65)

```
### `DEFAULT`

 Sets a value when nothing is passed. 
```sql
CREATE TABLE users (
  is_active BOOLEAN DEFAULT TRUE
);
```

If you INSERT without is_active, it’ll be TRUE by default.
## Naming Constraints

```sql
CREATE TABLE users (
  id INT CONSTRAINT pk_users PRIMARY KEY,
  email VARCHAR(255) CONSTRAINT uq_email UNIQUE,
  age INT CONSTRAINT check_age CHECK (age >= 13)
);

```

Clean, readable, and easier to manage.
## Manipulation Constraints AFTER Table Creation

```sql
-- Add NOT NULL
ALTER TABLE users
MODIFY name VARCHAR(100) NOT NULL;

-- Add UNIQUE
ALTER TABLE users
ADD CONSTRAINT unique_email UNIQUE(email);

-- Add CHECK
ALTER TABLE employees
ADD CONSTRAINT check_salary CHECK (salary > 0);

-- Add FOREIGN KEY
ALTER TABLE orders
ADD CONSTRAINT fk_user FOREIGN KEY (user_id) REFERENCES users(user_id);

-- Dropping Constraints
ALTER TABLE table_name
DROP CONSTRAINT constraint_name;

-- for dropping , need to know the name of the constraint — often auto-generated unless  named it.
```

## Common Mistakes

| Errors                                       | Fix                                      |
| -------------------------------------------- | ---------------------------------------- |
| Adding duplicate values to UNIQUE/PK columns | Remove or change dupes                   |
| Inserting `NULL` into `NOT NULL` fields      | Provide a value                          |
| Violating a `FOREIGN KEY`                    | Make sure the referenced data exists     |
| Wrong data type for `CHECK`                  | Validate logic — can't `CHECK(name > 0)` |
