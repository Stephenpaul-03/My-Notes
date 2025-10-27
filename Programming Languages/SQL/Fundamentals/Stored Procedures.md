## Definition

- A stored procedure is a precompiled block of SQL code that you can call whenever needed.
	- Saves from writing the same SQL again
	- Can take inputs & return outputs
	- Can contain **logic**, **loops**, **conditions**, **transactions**, etc.

## Basic Syntax (MySQL Example)

```sql
DELIMITER //

CREATE PROCEDURE procedure_name (IN param1 INT, OUT param2 VARCHAR(100))
BEGIN
    -- SQL logic here
    SELECT column INTO param2 FROM table WHERE id = param1;
END //

DELIMITER ;

```
## Types of Parameters

| Type | Meaning |
| --- | --- |
| `IN` | Input-only |
| `OUT` | Output-only |
| `INOUT` | Can be used as both input and output |

```sql
-- Example with IN only
CREATE PROCEDURE get_user (IN uid INT)
BEGIN
    SELECT * FROM users WHERE user_id = uid;
END;

-- Calling a Procedure -- 

CALL get_user(5); -- That’s it — no need to rewrite that SELECT again. -- 

-- For OUT params --

CALL procedure_name(5, @output_param);
SELECT @output_param;

------------------------------------ EXAMPLE ------------------------------------------

-- Procedure -- 
CREATE PROCEDURE get_total_sales(IN customer_id INT, OUT total_sales DECIMAL(10,2))
BEGIN
    SELECT SUM(amount)
    INTO total_sales
    FROM orders
    WHERE customer_id = customer_id;
END;
-- Call -- 
CALL get_total_sales(7, @total);
SELECT @total;

```
## Intermediate Procedures

```sql
--- CONDITIONAL STATEMENTS ---
CREATE PROCEDURE check_stock(IN prod_id INT, OUT stock_status VARCHAR(20))
BEGIN
    DECLARE stock_count INT;

    SELECT quantity INTO stock_count FROM inventory WHERE product_id = prod_id;

    IF stock_count > 0 THEN
        SET stock_status = 'In Stock';
    ELSE
        SET stock_status = 'Out of Stock';
    END IF;
END;

--- TRANSACTIONS ---
CREATE PROCEDURE transfer_funds(IN from_id INT, IN to_id INT, IN amount DECIMAL(10,2))
BEGIN
    START TRANSACTION;

    UPDATE accounts SET balance = balance - amount WHERE id = from_id;
    UPDATE accounts SET balance = balance + amount WHERE id = to_id;

    COMMIT;
END;

--- add Rollback just to be safe

--- DROPPING PROCEDURE ---

DROP PROCEDURE IF EXISTS procedure_name;

```
## Advantages
- Performance — compiled & cached
- Reusability — write once, use forever
- Security — grant EXECUTE, not table access
- Abstraction — hide complex logic from users
- Maintainability — update logic in one place
## Disadvantages
- Harder to debug than app code
- Version control is trickier
- DB portability issues (syntax differs across DBs)
- Logic trapped in DB can slow frontend agility
## Best Practices
- **Prefix procedures** with `sp_` or similar
- Keep them **short and single-purpose**
- Use **parameters**, don’t hardcode values
- Comment your logic like you’re explaining to a tired 3am dev