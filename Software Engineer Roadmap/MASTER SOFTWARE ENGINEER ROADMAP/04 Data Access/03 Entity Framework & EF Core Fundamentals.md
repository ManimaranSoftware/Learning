### Entity Framework (EF)

- Entity Framework - Microsoft's ORM for .NET.
- Maps database tables to C# objects.
- Reduces manual SQL writing.

---

### Entity Framework Core (EF Core)

- EF Core - Lightweight, cross-platform version of Entity Framework.
- Open-source and high-performance.
- Recommended for modern .NET applications.

---

### ORM (Object Relational Mapper)

- ORM - Maps database tables to objects and vice versa.
- Eliminates most manual CRUD operations.

---

### DbContext

- DbContext - Primary class for interacting with the database.
- Manages database connections, queries and changes.

---

### DbSet</TEntity>

- Represents a database table.
- Used to perform CRUD operations.

---

### Entity

- Entity - C# class representing a database table.

---

### CRUD Operations

- Create - Add new records.
- Read - Retrieve records.
- Update - Modify existing records.
- Delete - Remove records.

---

### Change Tracker

- Tracks changes made to entities.
- Used during `SaveChanges()`.

---

### SaveChanges()

- Persists pending changes to the database.
- Executes INSERT, UPDATE and DELETE operations.

---

### SaveChangesAsync()

- Asynchronous version of `SaveChanges()`.
- Recommended for Web APIs.

---

### LINQ to Entities

- Uses LINQ to query the database.
- EF Core translates LINQ into SQL.

---

### Navigation Property

- Represents relationships between entities.
- Supports one-to-one, one-to-many and many-to-many relationships.

---

### Benefits

- Faster development.
- Less boilerplate code.
- Automatic object mapping.
- Strong LINQ support.
- Cross-platform with EF Core.