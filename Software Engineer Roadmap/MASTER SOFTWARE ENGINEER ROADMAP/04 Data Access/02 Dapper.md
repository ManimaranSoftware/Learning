### Dapper

- Dapper - Lightweight Micro ORM for .NET.
- Developed By - Stack Overflow.
- Extension library built on ADO.NET.
- Focus - High performance and simple object mapping.

---

### ORM

- ORM (Object Relational Mapper) - Maps database tables to C# objects.

---

### Micro ORM

- Micro ORM - Lightweight ORM with minimal abstraction.
- Provides manual SQL control with object mapping.

---

### Query()

- Executes SELECT queries.
- Returns multiple records.

---

### QuerySingle()

- Returns exactly one record.
- Throws exception if zero or multiple records exist.

---

### QuerySingleOrDefault()

- Returns one record or default value.
- Throws exception if multiple records exist.

---

### QueryFirst()

- Returns first matching record.
- Throws exception if no records exist.

---

### QueryFirstOrDefault()

- Returns first record or default value.

---

### Execute()

- Executes INSERT, UPDATE and DELETE.
- Returns affected row count.

---

### ExecuteScalar()

- Returns a single value.
- Commonly used for COUNT(), SUM(), MAX().

---

### Parameterized Query

- Uses parameters instead of string concatenation.
- Prevents SQL Injection.

---

### Stored Procedure

- Supports executing stored procedures.
- Specify `CommandType.StoredProcedure`.

---

### Multi Mapping

- Maps data from multiple tables into related objects.
- Useful for JOIN queries.

---

### Buffered Query

- Loads entire result into memory.
- Default behavior.

---

### Unbuffered Query

- Streams records one by one.
- Lower memory usage.
- Better for large datasets.

---

### Transaction

- Supports database transactions.
- Uses `IDbTransaction`.

---

### Benefits

- Very high performance.
- Simple API.
- Full SQL control.
- Lightweight.
- Easy integration with ADO.NET.