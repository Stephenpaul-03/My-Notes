## **Definition**

- **Constraints** are rules enforced on data in tables to ensure data integrity, consistency, and accuracy and are applied at the column or table level such that it also dictates permitted data values

## **Types of Constraints**

### **# Domain Constraint**

- **Definition**: Limits the possible values for a column.
- **Example**: `AGE INT CHECK (AGE >= 18)`
- **Purpose**: Ensures data falls within a specific range or type.

### **# Entity Integrity Constraint**

- **Definition**: Ensures that each entity (row) is uniquely identifiable.
- **Implementation**: Use of **PRIMARY KEY**
- **Rule**: Primary Key column(s) must be **NOT NULL** and **UNIQUE**.

### **# Referential Integrity Constraint**

- **Definition**: Maintains consistency among rows in different tables.
- **Implementation**: Use of **FOREIGN KEY**
- **Rule**: Foreign Key value must exist in the referenced primary key column or be NULL.

### **# Key Constraints**

- **Primary Key**:
    - Uniquely identifies each row.
    - Cannot contain NULLs.
- **Unique Key**:
    - Ensures all values in a column are different.
    - Allows one NULL (per standard SQL).
- **Candidate Key**:
    - A set of fields that qualify as Primary Key candidates.
    - One is selected as Primary; others become Alternate Keys.
- **Alternate Key**:
    - Candidate Keys not chosen as the Primary Key.

### **# NOT NULL Constraint**

- **Definition**: Ensures a column cannot have NULL values.
- **Use-case**: Enforces mandatory data fields.

### **# CHECK Constraint**

- **Definition**: Validates data based on a logical expression.
- **Example**: `SALARY CHECK (SALARY > 0)`
- **Limitation**: Not all DBMSs enforce complex conditions across rows or tables.

### **# DEFAULT Constraint**

- **Definition**: Assigns a default value when no value is provided during insertion.
- **Example**: `CREATED_AT DATE DEFAULT SYSDATE`
