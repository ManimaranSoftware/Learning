### Query Optimization

- Query Optimization - Improving query execution to reduce execution time and resource usage.

---

### Execution Plan

- Execution Plan - Shows how SQL Server executes a query.
- Helps identify bottlenecks and expensive operations.

---

### Statistics

- Statistics - Metadata about data distribution.
- Used by SQL Server Query Optimizer.

---

### Index Optimization

- Create indexes on frequently searched columns.
- Remove unused indexes.
- Maintain indexes regularly.

---

### Avoid SELECT *

- Retrieve only required columns.
- Reduces network traffic and memory usage.

---

### Use WHERE Clause

- Filter data as early as possible.
- Reduces rows processed.

---

### Optimize JOINs

- Join indexed columns.
- Avoid unnecessary joins.
- Choose appropriate join type.

---

### Optimize Subqueries

- Replace complex subqueries with JOIN or CTE where appropriate.
- Improve readability and performance.

---

### Pagination

- Use `OFFSET-FETCH` or `TOP` for large datasets.
- Avoid loading unnecessary rows.

---

### EXISTS vs IN

- `EXISTS` - Better for large datasets.
- `IN` - Suitable for smaller datasets.

---

### Parameterized Queries

- Prevent SQL Injection.
- Allow execution plan reuse.

---

### Avoid Functions on Indexed Columns

- Functions on indexed columns may prevent index usage.
- Can lead to full table scans.

---

### Database Normalization

- Reduce data redundancy.
- Improve data consistency.

---

### Denormalization

- Introduce controlled redundancy.
- Improve read performance when required.

---
### SARGable Query

- SARGable (Search ARGument Able) - Query that allows SQL Server to efficiently use indexes.
- Avoid wrapping indexed columns with functions in the `WHERE` clause.
---
### Full Table Scan

- Occurs when SQL Server scans every row in a table.
- Usually slower than an Index Seek.

---

### Index Seek

- SQL Server directly navigates to matching rows using an index.
- More efficient than a Table Scan.

---

### Index Scan

- SQL Server scans the entire index.
- Better than a Table Scan in many cases but less efficient than an Index Seek.

---

### Benefits

- Faster queries.
- Reduced CPU and memory usage.
- Better scalability.
- Improved user experience.