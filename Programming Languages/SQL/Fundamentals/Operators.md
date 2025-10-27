## **Arithmetic Operators**
Used for basic math.

| Operator | Description        |
| -------- | ------------------ |
| `+`      | Add                |
| `-`      | Subtract           |
| `*`      | Multiply           |
| `/`      | Divide             |
| `%`      | Modulo (remainder) |
## **Bitwise Operators**
Used for binary manipulation (mainly in SQL Server, PostgreSQL).

| Operator | Description            |
| -------- | ---------------------- |
| `&`      | Bitwise AND            |
| \|       | Bitwise OR             |
| `^`      | Bitwise XOR            |
| `~`      | Bitwise NOT (negation) |
| `<<`     | Bitwise left shift     |
| `>>`     | Bitwise right shift    |
Not available in MySQL.
## **Comparison Operators**
Used in `WHERE`, `HAVING`, and everywhere for checking stuff.

| Operator           | Description                          |
| ------------------ | ------------------------------------ |
| `=`                | Equal to                             |
| `>`                | Greater than                         |
| `<`                | Less than                            |
| `>=`               | Greater than or equal to             |
| `<=`               | Less than or equal to                |
| `<>`               | Not equal to                         |
| `!=`               | Not equal to (alt syntax)            |
| `IS NULL`          | Check for NULL                       |
| `IS NOT NULL`      | Not NULL                             |
| `IS DISTINCT FROM` | Null-safe compare (PostgreSQL, etc.) |
## **Compound Assignment Operators**

| Operator | Description            |
| -------- | ---------------------- |
| `+=`     | Add and assign         |
| `-=`     | Subtract and assign    |
| `*=`     | Multiply and assign    |
| `/=`     | Divide and assign      |
| `%=`     | Modulo and assign      |
| `&=`     | Bitwise AND and assign |
| `=`      | Bitwise OR and assign  |
| `^=`     | Bitwise XOR and assign |
## **Logical Operators**
Controls flow of logic in `WHERE`, `HAVING`, etc.

| Operator  | Description                       |
| --------- | --------------------------------- |
| `AND`     | All conditions must be TRUE       |
| `OR`      | At least one condition is TRUE    |
| `NOT`     | Reverses the truth value          |
| `ALL`     | TRUE if all returned values match |
| `ANY`     | TRUE if any one matches           |
| `SOME`    | Same as `ANY`                     |
| `BETWEEN` | Value within a range              |
| `IN`      | Value in a list                   |
| `EXISTS`  | Subquery returns rows? TRUE/FALSE |
| `LIKE`    | Pattern match using `%` or `_`    |
## **Set Operators**
Used to combine multiple `SELECT` results.

| Operator    | Description                               | Notes                     |
| ----------- | ----------------------------------------- | ------------------------- |
| `UNION`     | Combine results & remove duplicates       | Requires matching columns |
| `UNION ALL` | Combine results & keep duplicates         | Faster than `UNION`       |
| `INTERSECT` | Return only common rows                   | Not in MySQL              |
| `EXCEPT`    | Return rows in first query but not second | Aka `MINUS` in Oracle     |
## **Null Handling / Conditional Functions**

| Function     | Description                              | Example                                    |
| ------------ | ---------------------------------------- | ------------------------------------------ |
| `COALESCE()` | Returns first non-null value             | `COALESCE(nickname, 'Anonymous')`          |
| `NULLIF()`   | Returns NULL if both arguments are equal | `NULLIF(a, b)` → NULL if a = b, else a     |
| `ISNULL()`   | Replaces NULL with a value (SQL Server)  | `ISNULL(name, 'NoName')`                   |
| `IFNULL()`   | Same as `ISNULL()` but for MySQL         | `IFNULL(city, 'Unknown')`                  |
| `CASE`       | SQL's IF/ELSE                            | `CASE WHEN x > 0 THEN 'yes' ELSE 'no' END` |
## **Pattern Matching Wildcards (for LIKE)**

| Symbol | Description                 | Example                      |
| ------ | --------------------------- | ---------------------------- |
| `%`    | Matches any # of characters | `LIKE 'A%' → 'Amit', 'Arya'` |
| `_`    | Matches single character    | `LIKE '_at' → 'Cat', 'Bat'`  |
