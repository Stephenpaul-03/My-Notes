## **Definition**

- An **SQL Execution Plan** (also referred to as a *Query Plan*) is the step-by-step strategy that the DBMS engine follows to execute a SQL query.
- This plan involves the use of various operators that define how data will be accessed and processed.

**Key Functions:**

- Determine **access paths** (e.g., index vs. table scan).
- Estimate **cost** and **cardinality** (number of rows processed).
- Select the **most efficient plan** among multiple candidates.

Plans are cached in the **plan cache** for reuse to avoid re-compilation.

## **Types of Execution Plans**

### # **Estimated Execution Plan**

- **Generated before execution.**
- Based solely on query structure and database statistics.
- No actual runtime data is available.
- Useful for **forecasting performance** and analyzing query logic.

### # **Actual Execution Plan**

- **Generated after the query has been executed.**
- Includes **runtime metrics** like:
    - Actual number of rows returned
    - Execution warnings (e.g., missing indexes, implicit conversions)
    - Actual resource usage
- Best suited for **deep performance analysis** and troubleshooting.

## **Execution Plan Formats**

| Format | Description |
| --- | --- |
| **Graphical** | Visual flowchart of operators and flow. |
| **Text** | Plain-text representation (SET SHOWPLAN_TEXT). |
| **XML** | Structured format for automated parsing or export. |