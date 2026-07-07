### Index

- Index - Database object that improves data retrieval performance.
- Similar to an index in a book.

---

### Clustered Index

- Stores table data physically in sorted order.
- Only one Clustered Index per table.
- Created automatically on Primary Key (by default in SQL Server).

---

### Non-Clustered Index

- Stores index separately from table data.
- Contains pointers to actual rows.
- Multiple Non-Clustered Indexes can exist.

---

### Composite Index

- Index created on multiple columns.
- Improves queries filtering on those columns.

---

### Unique Index

- Ensures indexed column values are unique.
- Prevents duplicate values.

---

### Covering Index

- Contains all columns required by a query.
- Reduces table lookups.

---

### Create Index

- Creates an index on one or more columns.
- Improves SELECT performance.

---

### Drop Index

- Removes an existing index.

---

### Rebuild Index

- Recreates the index.
- Removes fragmentation.

---

### Reorganize Index

- Defragments index without fully rebuilding it.
- Less resource-intensive than rebuild.

---

### Index Fragmentation

- Occurs when index pages become scattered.
- Can reduce query performance.

---

### Benefits

- Faster SELECT queries.
- Faster JOIN operations.
- Faster ORDER BY and GROUP BY.
- Improved query performance.
---
### When NOT to Use Indexes

- Tables with very few rows.
- Columns that change frequently.
- Columns with very low uniqueness (low selectivity).
- Too many indexes slow down INSERT, UPDATE and DELETE operations.
---
### Execution Plan

- Execution Plan - Shows how SQL Server executes a query.
- Helps identify performance bottlenecks.
- Commonly used for query optimization.
