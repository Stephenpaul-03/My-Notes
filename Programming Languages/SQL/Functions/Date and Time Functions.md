## Date and Time Functions

| Function                                      | Description                        |
| --------------------------------------------- | ---------------------------------- |
| `NOW()` / `CURRENT_TIMESTAMP`                 | Current date and time              |
| `CURDATE()` / `CURRENT_DATE`                  | Current date only                  |
| `CURTIME()` / `CURRENT_TIME`                  | Current time only                  |
| `DATE()`                                      | Extracts date part                 |
| `TIME()`                                      | Extracts time part                 |
| `DAY()` / `MONTH()` / `YEAR()`                | Extract specific parts             |
| `HOUR()` / `MINUTE()` / `SECOND()`            | Extract time parts                 |
| `WEEK()` / `DAYNAME()` / `MONTHNAME()`        | More granular info                 |
| `DATEDIFF()`                                  | Difference in days                 |
| `TIMESTAMPDIFF()` *(MySQL)*                   | Difference in custom units         |
| `DATE_ADD()` / `DATE_SUB()`                   | Add/subtract intervals             |
| `EXTRACT()`                                   | Pull specific component from date  |
| `STR_TO_DATE()`                               | Convert string to date             |
| `FORMAT()`                                    | Format dates into readable strings |
| `TO_CHAR()` / `TO_DATE()` *(Postgres/Oracle)* | Convert & format dates             |