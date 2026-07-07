### View

- View - Virtual table created from one or more tables.
- Stores SQL query, not actual data.

---

### Simple View

- Based on a single table.
- Usually supports INSERT, UPDATE and DELETE.

---

### Complex View

- Based on multiple tables or aggregate functions.
- Often read-only.

---

### Benefits of View

- Simplifies complex queries.
- Improves security by hiding underlying tables.
- Promotes query reusability.

---

### Stored Procedure

- Stored Procedure - Precompiled SQL statements stored in the database.
- Executes business logic on the database server.

---

### Parameters

- Stored Procedures support Input and Output parameters.

---

### Execute Stored Procedure

- Executes using the `EXEC` or `EXECUTE` command.

---

### Return Value

- Stored Procedure can return a status or result value.

---

### Advantages of Stored Procedure

- Better performance.
- Reduced network traffic.
- Improved security.
- Reusable business logic.
- Easier maintenance.

---

### User Defined Function (UDF)

- Returns a value or table.
- Can be used inside SQL queries.
- Cannot modify database data.

---

### Stored Procedure vs Function

- Stored Procedure - Can perform CRUD operations and return multiple result sets.
- Function - Must return a value or table and cannot modify database state.

---
### Trigger

- Trigger - Special stored procedure that executes automatically when INSERT, UPDATE or DELETE occurs.
- Common Usage - Auditing, Logging, Data Validation.
---

### Benefits

- Reusable SQL logic.
- Improved security.
- Better maintainability.
- Optimized execution.