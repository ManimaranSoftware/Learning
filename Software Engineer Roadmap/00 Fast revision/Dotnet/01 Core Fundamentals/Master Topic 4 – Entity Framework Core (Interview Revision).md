
## ORM
- ORM → Object Relational Mapper
- Converts C# Objects ↔ Database Tables
- Reduces SQL Writing
- Improves Productivity

> [!tip]
> **Memory Tip:** EF Core = C# Objects ↔ SQL Tables

---

## `DbContext`
- Main EF Core Class
- Database Session
- Tracks Entity Changes
- Executes `SaveChanges()`

---

## `DbSet<T>`
- Represents a Database Table
- CRUD Operations
- LINQ Queries
- Entity Collection

---

## Code First vs Database First
- Code First → Classes → Database
- Database First → Database → Classes
- Code First preferred in modern projects

---

## LINQ to EF
- `Where()` → Filter
- `Select()` → Projection
- `OrderBy()` → Sorting
- `GroupBy()` → Grouping
- `Join()` → Join Tables

---

## Loading Strategies
- Eager Loading → `Include()`
- Lazy Loading → Loads when accessed
- Explicit Loading → `Load()`

> [!tip]
> **Memory Tip:** Eager = Immediately | Lazy = Later | Explicit = Manually

---

## Tracking
- Tracking → Change Detection
- `AsNoTracking()` → Read Only
- Improves Read Performance

---

## `IQueryable<T>` vs `IEnumerable<T>`
- `IQueryable<T>` → Query executes in Database
- `IEnumerable<T>` → Query executes in Memory

> [!tip]
> **Memory Tip:** IQueryable = SQL | IEnumerable = RAM

---

## Migrations
- `Add-Migration`
- `Update-Database`
- Version Control for Database
- Schema Changes

---

## Relationships
- One-to-One
- One-to-Many
- Many-to-Many
- Navigation Properties
- Foreign Key

---

## Transactions
- `BeginTransaction()`
- `Commit()`
- `Rollback()`
- Ensures Data Consistency

---

## Concurrency
- Optimistic Concurrency
- `[Timestamp]`
- Prevents Lost Updates

---

## Performance
- `AsNoTracking()`
- Projection using `Select()`
- Avoid N+1 Problem
- Use `Include()` Carefully
- Pagination using `Skip()` & `Take()`

---

## EF Core vs Dapper
- EF Core → Full ORM, Productivity
- Dapper → Micro ORM, Faster
- EF Core → Complex Business Apps
- Dapper → Performance Critical Queries

> [!tip]
> **Memory Tip:** EF Core = Easy Development | Dapper = High Performance

---

## Interview Traps
- `IQueryable<T>` vs `IEnumerable<T>`
- Tracking vs `AsNoTracking()`
- Eager vs Lazy vs Explicit Loading
- Code First vs Database First
- `Include()` vs `Select()`
- EF Core vs Dapper
- `SaveChanges()` vs `SaveChangesAsync()`
- `DbContext` Lifetime (`Scoped`)

---

## 30-Second Revision Formula

ORM → `DbContext` → `DbSet<T>` → Code First → LINQ → Loading → Tracking → `IQueryable<T>` → Migrations → Relationships → Transactions → Concurrency → Performance → EF Core vs Dapper