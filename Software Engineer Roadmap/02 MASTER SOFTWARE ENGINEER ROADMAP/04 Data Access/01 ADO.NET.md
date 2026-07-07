### ADO.NET

- ADO.NET - .NET data access framework for interacting with relational databases.
- Supports - SQL Server, Oracle, MySQL and other databases.

---

### Connection

- SqlConnection - Establishes connection to SQL Server.
- Connection String - Contains server, database and authentication details.

---

### Command

- SqlCommand - Executes SQL queries and stored procedures.

---

### DataReader

- SqlDataReader - Fast, Forward-only, Read-only data retrieval.

---

### DataAdapter

- SqlDataAdapter - Bridges database and DataSet.
- Supports filling and updating data.

---

### DataSet

- DataSet - In-memory collection of tables.
- Can hold multiple DataTables and relationships.

---

### DataTable

- DataTable - Represents a single in-memory table.

---

### Execute Methods

- ExecuteReader() - Returns `SqlDataReader`.
- ExecuteScalar() - Returns single value.
- ExecuteNonQuery() - Executes INSERT, UPDATE, DELETE.

---

### Parameterized Query

- Prevents SQL Injection.
- Uses SQL parameters instead of string concatenation.

---

### Stored Procedure

- Precompiled SQL code stored in database.
- Improves security and reusability.

---

### Connection Pooling

- Reuses database connections.
- Improves application performance.
- Enabled by default in ADO.NET.

with Connection pooling (Pooling = true)
```
using System.Data.SqlClient;

string connString = "Server=myServer;Database=myDB;User Id=myUser;Password=myPassword;Pooling=true;";

using (SqlConnection conn = new SqlConnection(connString))
{
    conn.Open();
    // Perform database operations
    conn.Close(); // Returns the connection to the pool instead of closing it physically
} // The using block calls Dispose(), ensuring no memory leaks

```

---

### Benefits

- High performance.
- Direct database access.
- Fine-grained control.
- Suitable for complex SQL operations.