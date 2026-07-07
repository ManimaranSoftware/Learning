# 05A Advanced SQL

### Window Function

- Window Function - Performs calculations across a set of rows without grouping them.
- Uses `OVER()` clause.

---

### OVER()

- Defines the window (partition and ordering) for Window Functions.

---

### ROW_NUMBER()

- Assigns a unique sequential number to each row.

---

### RANK()

- Assigns rank with gaps for duplicate values.

---

### DENSE_RANK()

- Assigns rank without gaps for duplicate values.

---

### NTILE()

- Divides rows into a specified number of groups.

---

### LEAD()

- Returns the value from the next row.

---

### LAG()

- Returns the value from the previous row.

---

### FIRST_VALUE()

- Returns the first value within the window.

---

### LAST_VALUE()

- Returns the last value within the window.

---

### PIVOT

- Converts row values into columns.

---

### UNPIVOT

- Converts columns into rows.

---

### MERGE

- Combines INSERT, UPDATE and DELETE in a single statement.
- Commonly used for data synchronization.

---

### Temporary Table

- Temporary table stored in `tempdb`.
- Exists only during the current session.
- Types - Local (`#`) and Global (`##`).

---

### Table Variable

- Stores temporary data within a batch or procedure.
- Declared using `DECLARE`.

---

### Dynamic SQL

- SQL statement constructed and executed at runtime.
- Commonly executed using `sp_executesql`.

---

### Recursive CTE

- CTE that references itself.
- Used for hierarchical data (Employee-Manager, Category Tree).

---

### Query Hint

- Provides instructions to SQL Server Query Optimizer.
- Used only when necessary.

---

### Execution Plan Analysis

- Analyze Index Seek, Index Scan and Table Scan.
- Identify expensive query operations.

---
### PARTITION BY

- Divides result set into logical groups.
- Used with Window Functions.

---

### ORDER BY (Window Function)

- Defines row order within each partition.
- Used inside the `OVER()` clause.
---

### Benefits

- Advanced data analysis.
- Ranking and reporting.
- Complex transformations.
- Efficient hierarchical queries.
- Better query optimization.