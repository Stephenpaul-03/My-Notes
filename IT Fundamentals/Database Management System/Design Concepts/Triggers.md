## **Definition**

- A **trigger** is a stored procedural logic (block of code) that is automatically executed by the DBMS **in response to DML (Data Manipulation Language) or DDL (Data Definition Language) events** such as `INSERT`, `UPDATE`, or `DELETE`.

## **# Purpose**

- Enforce complex integrity constraints.
- Maintain audit trails.
- Automate cascading updates or deletions.
- Perform validation beyond standard constraints.

## **Working**

Triggers are event-condition-action rules. When a defined **event** occurs on a specified **table or view**, and the **condition** (optional) is met, the associated **action** is automatically executed.

**General Syntax:**

```sql
CREATE TRIGGER trigger_name
[BEFORE | AFTER | INSTEAD OF] event
ON table_name
[FOR EACH ROW | STATEMENT]
WHEN (condition)
BEGIN
   -- action logic
END;
````

## **Types**

### **# A. Based on Triggering Event**

- **INSERT Trigger**
    - Activated when a new row is inserted into the table.
        
- **UPDATE Trigger**
    - Activated when an existing row is updated.
        
- **DELETE Trigger**
    - Activated when a row is deleted.

### **# B. Based on Execution Time**

- **BEFORE Trigger**
    - Executes **before** the triggering DML operation.
    - Used for validation, default assignments, or logic to **abort** the operation by raising an error.
        
- **AFTER Trigger**
    - Executes **after** the triggering operation.
    - Ideal for logging, auditing, and related business rule enforcement.
        
- **INSTEAD OF Trigger**
    - Used primarily on **views**, not tables.
    - Overrides the default DML operation.
    - Enables `INSERT`, `UPDATE`, or `DELETE` on complex views.
        
### **# C. Based on Row or Statement Level**

- **Row-Level Trigger**
    - Executes once **for each affected row**.
    - Access to `NEW` and `OLD` pseudo-records.
    
    ```sql
    NEW.column_name -- Value after DML
    OLD.column_name -- Value before DML
    ```
    
- **Statement-Level Trigger**
    - Executes once **for the whole DML operation**, regardless of the number of affected rows.
    - Cannot access individual row data.

## **Practical Use Cases**

|Use Case|Trigger Type|
|---|---|
|Automatically update timestamps|`BEFORE UPDATE`|
|Maintain audit logs|`AFTER INSERT/UPDATE/DELETE`|
|Prevent invalid data insertion|`BEFORE INSERT`|
|Implement soft deletes|`BEFORE DELETE`|
|Denormalized summary table update|`AFTER INSERT/UPDATE`|
|Cascade changes to child tables|`AFTER UPDATE`|
|Support DML operations on views|`INSTEAD OF`|

## **Limitations**

- **No direct user interaction** (e.g., no `PRINT` statements or GUI prompts).
- **Complex logic** in triggers can degrade performance and cause **cascading triggers** (hard to debug).
- **Mutating Table Error** in systems like Oracle: can’t read a table that is being modified by the trigger.
- Can **impact scalability** due to increased resource usage.
- **Not portable**: trigger syntax and behavior vary across DBMS platforms.