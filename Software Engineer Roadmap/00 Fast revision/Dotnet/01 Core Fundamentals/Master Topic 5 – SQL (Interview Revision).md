## Database Basics
- Database → Collection of Data
- Table → Rows & Columns
- Row → Record
- Column → Attribute
- Primary Key (`PK`) → Unique Identifier
- Foreign Key (`FK`) → Relationship Between Tables

> [!tip]
> **Memory Tip:** PK = Identity | FK = Relationship

---

## CRUD Operations
- `SELECT` → Read
- `INSERT` → Create
- `UPDATE` → Modify
- `DELETE` → Remove

---

## SQL Clauses
- `WHERE` → Filter
- `ORDER BY` → Sort
- `GROUP BY` → Group Records
- `HAVING` → Filter Groups
- `DISTINCT` → Unique Values
- `TOP` → Limit Results

---

## Joins
- `INNER JOIN` → Matching Records
- `LEFT JOIN` → All Left + Matching Right
- `RIGHT JOIN` → All Right + Matching Left
- `FULL JOIN` → All Records
- `CROSS JOIN` → Cartesian Product
- `SELF JOIN` → Same Table Join

> [!tip]
> **Memory Tip:** INNER = Match | LEFT = Keep Left | RIGHT = Keep Right | FULL = Everything

---

## Aggregate Functions
- `COUNT()`
- `SUM()`
- `AVG()`
- `MIN()`
- `MAX()`

---

## Constraints
- `PRIMARY KEY`
- `FOREIGN KEY`
- `UNIQUE`
- `NOT NULL`
- `DEFAULT`
- `CHECK`

---

## Normalization
- 1NF → Atomic Values
- 2NF → Remove Partial Dependency
- 3NF → Remove Transitive Dependency
- Purpose → Reduce Data Redundancy

---

## Indexes
- Clustered Index → Stores Data Physically
- Non-Clustered Index → Separate Structure
- Improves Read Performance
- Too Many Indexes Slow Writes

> [!tip]
> **Memory Tip:** Index = Book Index (Fast Search)

---

## Views
- Virtual Table
- Simplifies Complex Queries
- Improves Security
- Stores Query, Not Data

---

## Stored Procedures
- Precompiled SQL
- Accept Parameters
- Better Performance
- Reusable Business Logic

---

## Functions
- Scalar Function → Returns Single Value
- Table-Valued Function (`TVF`) → Returns Table

---

## Transactions
- `BEGIN TRANSACTION`
- `COMMIT`
- `ROLLBACK`
- Ensures Data Integrity

---

## ACID Properties
- Atomicity
- Consistency
- Isolation
- Durability

> [!tip]
> **Memory Tip:** ACID = Reliable Transactions

---

## Isolation Levels
- Read Uncommitted
- Read Committed (Default)
- Repeatable Read
- Serializable

---

## Performance Optimization
- Use Indexes
- Avoid `SELECT *`
- Retrieve Required Columns
- Use Pagination
- Optimize Joins
- Analyze Execution Plan

---

## Common SQL Functions
- `ISNULL()`
- `COALESCE()`
- `CAST()`
- `CONVERT()`
- `CASE`
- `ROW_NUMBER()`

---

## Interview Traps
- `WHERE` vs `HAVING`
- `DELETE` vs `TRUNCATE` vs `DROP`
- Clustered vs Non-Clustered Index
- `INNER JOIN` vs `LEFT JOIN`
- `UNION` vs `UNION ALL`
- `CHAR` vs `VARCHAR`
- Primary Key vs Unique Key
- Stored Procedure vs Function
- `ISNULL()` vs `COALESCE()`
- Normalization vs Denormalization

---

## 30-Second Revision Formula

Database → CRUD → Clauses → Joins → Aggregate Functions → Constraints → Normalization → Indexes → Views → Stored Procedures → Functions → Transactions → ACID → Isolation Levels → Performance → Common Functions