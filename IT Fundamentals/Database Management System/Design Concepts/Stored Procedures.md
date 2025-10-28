## **Definition**

- A **Stored Procedure** is a precompiled collection of one or more SQL statements that perform a specific task and are stored in the database for repeated use.
- They are invoked explicitly by applications or users and execute within the database engine, optimizing performance and promoting reusability.

A **stored procedure** is a database object that encapsulates logic to be executed under a defined name.

```sql
CREATE PROCEDURE procedure_name
    [ (parameter1 datatype, parameter2 datatype, ...) ]
AS
BEGIN
    -- SQL statements
END;

EXEC procedure_name @param1 = value1, @param2 = value2;
````

|Feature|Description|
|---|---|
|**Precompiled**|Compiled once and stored in the database, improving execution speed.|
|**Reusable**|Called multiple times without rewriting SQL logic.|
|**Modular**|Encapsulates business logic in the database layer.|
|**Secure**|Controls data access via controlled interfaces.|
|**Transactional**|Can include explicit transaction control (BEGIN, COMMIT, ROLLBACK).|

## **Parameters**

|Type|Purpose|
|---|---|
|**IN**|Default. Used to pass input values.|
|**OUT**|Used to return values to the caller.|
|**INOUT**|Can pass initial value and return modified value.|

## **Advantages**

- **Performance**: Reduced parsing and planning overhead on each execution.
- **Maintainability**: Centralized logic simplifies change management and debugging.
- **Security**: Permissions can be granted on procedures rather than tables.
- **Atomic Operations**: Use of transactions ensures data integrity.
    
## **Limitations and Risks**

- **Portability**: Procedure syntax is vendor-specific (Oracle PL/SQL vs T-SQL vs MySQL).
- **Overuse**: Excessive logic in stored procedures can create a "logic trap" within the DB layer.
- **Debugging Complexity**: Harder to debug compared to application-layer code.
- **Version Control Challenges**: Procedures aren’t always managed in traditional CI/CD pipelines unless explicitly scripted.