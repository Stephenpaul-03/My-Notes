## **Numeric Data Types**

### **Exact Numbers**

| Data Type                       | Description                                                                                              |
| ------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `INT` / `INTEGER`               | Whole numbers. 4 bytes. Usually −2B to +2B                                                               |
| `SMALLINT`                      | Smaller range. 2 bytes.                                                                                  |
| `TINYINT`                       | 1 byte. Usually 0 to 255.                                                                                |
| `BIGINT`                        | Huge range. 8 bytes.                                                                                     |
| `DECIMAL(p,s)` / `NUMERIC(p,s)` | Fixed precision. Great for currency. `p` = total digits, `s` = digits after decimal. No rounding issues. |
| `BIT(n)`                        | Bit field (1s and 0s). `n` = bits. Often used for flags.                                                 |
### **Approximate Numbers**

| Data Type          | Description                                    |
| ------------------ | ---------------------------------------------- |
| `FLOAT(p)`         | Approx floating-point. Precision based on `p`. |
| `REAL`             | Less precise float (platform-dependent).       |
| `DOUBLE PRECISION` | High-precision float.                          |
## **Character / String Data Types**

| Data Type | Description |
| --- | --- |
| `CHAR(n)` | Fixed-length string (pads with spaces). Efficient for consistent-length values like codes. |
| `VARCHAR(n)` | Variable-length string. Most commonly used. |
| `TEXT` | Large string data (length varies by DB). Not indexable in some DBs. |
## **Date and Time Data Types**

| Data Type   | Description                                 |
| ----------- | ------------------------------------------- |
| `DATE`      | Only date: `YYYY-MM-DD`                     |
| `TIME`      | Only time: `HH:MM:SS[.fractional]`          |
| `DATETIME`  | Date + time (no timezone).                  |
| `TIMESTAMP` | Date + time WITH timezone (in some DBs).    |
| `YEAR`      | Only year (some DBs like MySQL).            |
| `INTERVAL`  | Time duration (PostgreSQL/Oracle specific). |
## **Boolean Type**

| Data Type | Description         |
| --------- | ------------------- |
| `BOOLEAN` | True/False (or 1/0) |
## **Binary / Blob Types**

| Data Type      | Description                               |
| -------------- | ----------------------------------------- |
| `BINARY(n)`    | Fixed-length binary.                      |
| `VARBINARY(n)` | Variable-length binary.                   |
| `BLOB`         | Large Binary Object (images, files, etc). |
## **Spatial and JSON (Modern Types)**

### **JSON**

- `JSON` or `JSONB` (PostgreSQL)
    - Store structured JSON objects.
    - Indexable (esp. JSONB).
    - Ideal for semi-structured data.
### **Geospatial**

- Types like `GEOMETRY`, `POINT`, `LINESTRING`, `POLYGON` (PostGIS, MySQL)
- Used for **maps**, **locations**, etc.
## **Nullability & Defaults**

 NULL ⇒ a missing, unknown, or inapplicable value in a database column 
- Columns can be:
    - `NULL` (accepts NULL values)
    - `NOT NULL` (rejects NULL)
- Can have `DEFAULT` values
```sql
age INT NOT NULL DEFAULT 18
```
## Type Affinities Across DBs

| Type Concept | MySQL         | PostgreSQL    | SQL Server    |
| ------------ | ------------- | ------------- | ------------- |
| Integer      | INT           | INTEGER       | INT           |
| Decimal      | DECIMAL       | NUMERIC       | DECIMAL       |
| Float        | FLOAT, DOUBLE | REAL, DOUBLE  | FLOAT, REAL   |
| String       | VARCHAR, TEXT | VARCHAR, TEXT | VARCHAR, TEXT |
| DateTime     | DATETIME      | TIMESTAMP     | DATETIME2     |
| Boolean      | TINYINT(1)    | BOOLEAN       | BIT           |
