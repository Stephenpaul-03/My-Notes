## Definition
- A trigger is a stored block of code that automatically executes in response to certain events on a table or view.
- Triggers = automatic event listeners + logic executors.
## Basic Syntax (MySQL Example)

```sql
CREATE TRIGGER trigger_name
{BEFORE | AFTER} {INSERT | UPDATE | DELETE}
ON table_name
FOR EACH ROW
BEGIN
    -- your logic
END;
```
## Types of Triggers

| Trigger Type | What It Does |
| --- | --- |
| BEFORE INSERT | Validate or manipulate data **before it’s inserted** |
| AFTER INSERT | Perform action **after row is inserted** |
| BEFORE UPDATE | Modify/update data **before changes get saved** |
| AFTER UPDATE | Log or act **after row is updated** |
| BEFORE DELETE | Prevent or check conditions **before deletion** |
| AFTER DELETE | Archive or log **after a row is deleted** |
## Examples

```sql
-- BEFORE INSERT
CREATE TRIGGER before_employee_insert
BEFORE INSERT ON employees
FOR EACH ROW
BEGIN
    IF NEW.salary < 0 THEN
        SIGNAL SQLSTATE '45000'
        SET MESSAGE_TEXT = 'Salary cannot be negative!';
    END IF;
END;

-- AFTER INSERT
CREATE TRIGGER after_user_signup
AFTER INSERT ON users
FOR EACH ROW
BEGIN
    INSERT INTO signup_logs (user_id, signup_time)
    VALUES (NEW.id, NOW());
END;

-- BEFORE UPDATE
CREATE TRIGGER normalize_username
BEFORE UPDATE ON users
FOR EACH ROW
BEGIN
    SET NEW.username = LOWER(NEW.username);
END;

-- AFTER UPDATE
CREATE TRIGGER log_salary_change
AFTER UPDATE ON employees
FOR EACH ROW
BEGIN
    IF OLD.salary <> NEW.salary THEN
        INSERT INTO salary_changes (emp_id, old_salary, new_salary, change_time)
        VALUES (OLD.id, OLD.salary, NEW.salary, NOW());
    END IF;
END;

-- BEFORE DELETE
CREATE TRIGGER prevent_vip_delete
BEFORE DELETE ON customers
FOR EACH ROW
BEGIN
    IF OLD.status = 'VIP' THEN
        SIGNAL SQLSTATE '45000'
        SET MESSAGE_TEXT = 'VIP customers cannot be deleted.';
    END IF;
END;

-- AFTER DELETE
CREATE TRIGGER archive_on_delete
AFTER DELETE ON customers
FOR EACH ROW
BEGIN
    INSERT INTO customers_archive (id, name, email)
    VALUES (OLD.id, OLD.name, OLD.email);
END;
```
## Accessing Row Data

| Keyword | Meaning                                    |
| ------- | ------------------------------------------ |
| `NEW`   | The row being **inserted/updated**         |
| `OLD`   | The row being **deleted or before update** |
## Manipulation Triggers

```sql
-- Dropping a Trigger ---

DROP TRIGGER IF EXISTS trigger_name;
```
## Advantages
- Automation - No manual effort needed
- Auditing - Automatically log changes
- Validation - Block bad data before it enters
- Business Rules - Enforce company policies at DB level
- Chaining - Trigger something else to happen
## Disadvantages
- Hidden Logic - Can be hard to trace
- Performance - Too Many = Too Slow
- Complexity - Easy to go south
- Recursive Triggers - Infinite loop if mishandled