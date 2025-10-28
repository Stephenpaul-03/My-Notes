## **Definition**

- SQL Joins are essential operations in relational databases used to retrieve and merge data from multiple tables based on logical relationships between them.

## **# INNER JOIN**

**Definition:**

`INNER JOIN` returns only those rows that have matching values in both tables.

![image.png](joins1.png)

**Syntax:**

```sql
SELECT table1.column1, table2.column2
FROM table1
INNER JOIN table2
ON table1.common_column = table2.common_column;
````

**Key Points:**

- Only rows with matching values are returned.
- `INNER JOIN` and `JOIN` are functionally equivalent.

## **# LEFT JOIN (LEFT OUTER JOIN)**

**Definition:**

Returns all records from the left table and matched records from the right table. Unmatched records from the right return `NULL`.

![image.png](Joins1.png)

**Syntax:**

```sql
SELECT table1.column1, table2.column2
FROM table1
LEFT JOIN table2
ON table1.common_column = table2.common_column;
```

**Use Case:**
Preserve all entries from the left table regardless of matching status.

## **# RIGHT JOIN (RIGHT OUTER JOIN)**

**Definition:**

Returns all records from the right table and matched records from the left table. Unmatched records from the left return `NULL`.

![image.png](Joins2.png)

**Syntax:**

```sql
SELECT table1.column1, table2.column2
FROM table1
RIGHT JOIN table2
ON table1.common_column = table2.common_column;
```

**Use Case:**
Preserve all entries from the right table while capturing matching records from the left.

## **# FULL JOIN (FULL OUTER JOIN)**

**Definition:**

Combines the results of both LEFT and RIGHT JOINs. Returns all records when there is a match in either left or right table. Missing matches return `NULL`.

![joins3.png](Joins3.png)

**Syntax:**

```sql
SELECT table1.column1, table2.column2
FROM table1
FULL JOIN table2
ON table1.common_column = table2.common_column;
```

**Key Point:**
Captures unmatched data from both tables - comprehensive but potentially sparse in join columns.

## **# NATURAL JOIN**

**Definition:**

A type of `INNER JOIN` that automatically joins tables on all columns with the same name and compatible data types.

**Syntax:**

```sql
SELECT * FROM table1
NATURAL JOIN table2;
```

**Key Characteristics:**

- No explicit `ON` clause is needed.
- Columns with the same names appear only once in the result.    
- Useful for simplifying queries when schema alignment is known and controlled.
