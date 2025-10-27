## Definition

- File handling in SQL refers to working with files for **reading, writing, importing, and exporting** data between the database and external sources.  
- While SQL isn’t designed for general file manipulation, most modern SQL databases provide built-in features and tools for **data import/export** and **BLOB (Binary Large Object)** operations.
## Common File Handling Operations

### 1. Reading Files in SQL
- **Text Files:**
  - In **SQL Server**, the `OPENROWSET(BULK ...)` function can read text file contents directly.
  - The file data is retrieved as a single column (using `SINGLE_CLOB` or `SINGLE_BLOB`).

  ```sql
  SELECT * FROM OPENROWSET(BULK 'E:\file.txt', SINGLE_CLOB) AS Contents;
```

- This returns the entire file as a single value.
- **Row-by-Row Import:**
    - For importing text line-by-line, first create a target table, then insert each line using `BULK INSERT` or database-specific import utilities.
### 2. Importing and Exporting Data

- **Importing Data:**
    - Used to load external file data (like CSV, JSON, or Excel) into database tables.
    - Examples:
```sql
--MySQL
LOAD DATA INFILE 'file.csv' 
INTO TABLE tablename 
FIELDS TERMINATED BY ',';

-- SQL Server: BULK INSERT or Import Wizard

-- PostgreSQL
COPY tablename FROM 'file.csv' WITH CSV;
```

- **Exporting Data:**
    - Used to write data from the database into external files.
    - Examples:
```sql
-- MySQL
SELECT * FROM tablename INTO OUTFILE 'output.csv' FIELDS TERMINATED BY ',';

-- PostgreSQL
COPY tablename TO 'output.csv' WITH CSV;

-- SQL Server: bcp tool or SSMS Export Wizard
```
### 3. Working with BLOBs and Unstructured Data

- **FILESTREAM (SQL Server):**
    - Allows storing large files (e.g., images, documents) in the **file system**, while maintaining database transactional control.
    - Data can be accessed via T-SQL or Win32 APIs.
    - Example use case: media storage where files are too large for direct database storage.
- **FileTables (SQL Server):**
    - Builds on FILESTREAM, allowing **direct file system access** to database-stored files.
    - Supports standard operations (read, write, move, delete) with synchronization between the filesystem and database.

### 4. Scripting and Batch Processing with SQL Files

- **SQL Files:**
    - Contain sequences of SQL statements (DDL/DML/queries) saved with a `.sql` extension.
    - Can be executed directly via command line or GUI tools.
    - Or loaded and executed in environments like **MySQL Workbench**, **SQL Server Management Studio (SSMS)**, etc.
    
```bash
mysql db_name < script.sql
```

### 5. Advanced File Operations

- **PL/SQL (Oracle):**
    - Use the `UTL_FILE` package to read/write files in authorized directories.
- **CLR Integration (SQL Server):**
    - Utilize .NET’s `System.IO` namespace in managed code to perform advanced file operations (copy, move, delete) that go beyond native T-SQL capabilities.

## Summary

File handling in SQL focuses on bridging **database storage** and **external file systems**, enabling:
- Data migration
- BLOB management
- Automation via SQL scripts  
    It’s not meant for full-fledged file system control, but for **data integration, persistence, and import/export efficiency**.
