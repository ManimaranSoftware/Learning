### Change Tracking

- Change Tracking - Monitors entity changes before saving to the database.
- Enabled by default in EF Core.

---

### Tracking Query

- Tracking Query - Retrieved entities are tracked by `DbContext`.
- Suitable for update operations.

---

### No Tracking Query

- No Tracking Query - Retrieved entities are not tracked.
- Improves read-only query performance.
- Uses `AsNoTracking()`.

---

### Entity State

- Represents current status of an entity.
- States - Added, Modified, Deleted, Unchanged, Detached.

---

### Detect Changes

- Detects modifications made to tracked entities.
- Executed automatically before `SaveChanges()`.

---

### Attach()

- Attaches an existing entity to `DbContext`.
- Entity state becomes `Unchanged`.

---

### Update()

- Marks entity as `Modified`.
- Updates all properties.

---

### Entry()

- Provides access to entity tracking information.
- Used to inspect or change entity state.

---

### AutoDetectChanges

- Automatically detects entity modifications.
- Can be disabled for bulk operations to improve performance.

---

### Compiled Query

- Precompiled LINQ query.
- Reduces query compilation overhead.
- Useful for frequently executed queries.

---

### Split Query

- Loads related data using multiple SQL queries.
- Helps avoid Cartesian explosion.

---

### Single Query

- Loads related data using one SQL query.
- Default behavior for `Include()`.

---

### Bulk Operations

- Performs large INSERT, UPDATE or DELETE efficiently.
- Often implemented using third-party libraries.

---
### DbContext Lifetime

- Scoped - Recommended lifetime for ASP.NET Core applications.
- One `DbContext` instance per HTTP request.
- Avoid registering `DbContext` as Singleton.

---
### Optimistic Concurrency

- Detects conflicts when multiple users update the same data.
- Commonly implemented using `RowVersion` or Timestamp.

---

### Concurrency Token

- Property used to detect concurrent updates.
- Prevents accidental data overwrite.

---

### Benefits

- Better query performance.
- Reduced memory usage.
- Efficient change tracking.
- Optimized database access.