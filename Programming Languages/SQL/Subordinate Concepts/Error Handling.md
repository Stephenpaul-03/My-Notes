# SQL Error Handling

## Definition
Error handling in SQL is achieved using the **`TRY...CATCH`** construct, which controls how the program responds to runtime errors.  
Code that might fail is placed inside a `TRY` block, and if an error occurs, execution jumps to the `CATCH` block where you can log, recover, or re-throw the error.

## Key Points

- Use **`TRY...CATCH`** blocks to wrap error-prone SQL statements.  
  When an error occurs inside the `TRY` block, the flow automatically transfers to the `CATCH` block.
- The `CATCH` block can access detailed error information using these built-in functions:

| Function            | Description                                                                   |
| ------------------- | ----------------------------------------------------------------------------- |
| `ERROR_NUMBER()`    | Returns the internal number of the error                                      |
| `ERROR_STATE()`     | Returns information about the source of the error                             |
| `ERROR_SEVERITY()`  | Indicates the severity level (from informational to fatal errors)             |
| `ERROR_PROCEDURE()` | Returns the name of the stored procedure or function where the error occurred |
| `ERROR_LINE()`      | Returns the line number where the error occurred                              |
| `ERROR_MESSAGE()`   | Returns the text of the error message                                         |

- Use **`RAISERROR`** or **`THROW`** inside the `CATCH` block to re-raise the error or send custom messages to the client or logs.
- Manage transactions properly:
  - If a transaction is started in the `TRY` block, ensure you **`COMMIT`** if successful or **`ROLLBACK`** in the `CATCH` block.
- The `TRY...CATCH` construct does **not** handle:
  - Compile-time errors (like syntax errors)
  - Certain severe system-level errors
- User-defined exceptions can be generated with **`THROW`** or **`RAISERROR`** for custom logic and error propagation.

## Example

```sql
BEGIN TRY
    -- Code that might fail
    INSERT INTO Products VALUES ('A', 5, 20)
END TRY
BEGIN CATCH
    PRINT 'Error Number: ' + CAST(ERROR_NUMBER() AS VARCHAR)
    PRINT 'Message: ' + ERROR_MESSAGE()
    
    -- Optionally, log or re-raise the error
    -- ROLLBACK TRANSACTION if inside a transaction
END CATCH
