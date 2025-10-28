## **Keys**

- Keys define how rows (tuples) are uniquely identified and how tables relate to one another.

![image.png](Keys.png)

## **# 1. Super Key**

- A set of one or more attributes that can uniquely identify a record.
- May include redundant attributes not necessary for uniqueness.

## **# 2. Candidate Key**

- A minimal super key with no redundant attributes.
- Uniquely identifies tuples in a table.
- A table can have multiple candidate keys.

## **# 3. Primary Key**

- A selected candidate key used to uniquely identify records.
- Cannot have NULL or duplicate values.
- Only one primary key per table.

## **# 4. Alternate Key**

- Candidate keys not selected as the primary key.
- Also ensures uniqueness but serves as a backup identifier.

## **# 5. Foreign Key**

- An attribute in one table that references the primary key of another table.
- Establishes relationships between tables.
- Can have NULLs and duplicate values.

## **# 6. Composite Key**

- A combination of two or more attributes that together uniquely identify a record.
- Used when no single attribute is sufficient for unique identification.
