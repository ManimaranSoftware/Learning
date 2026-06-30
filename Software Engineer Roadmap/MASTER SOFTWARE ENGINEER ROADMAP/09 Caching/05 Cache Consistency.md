### Cache Consistency

- Cache Consistency - Ensures cache data matches the source database.

---

### Cache Invalidation

- Removes or updates cached data when the underlying data changes.
- One of the biggest challenges in caching.

---

### Write-Through

- Updates cache and database together.
- Keeps data synchronized.

---

### Write-Behind (Write-Back)

- Updates cache first.
- Database is updated asynchronously.
- Temporary inconsistency may occur.

---

### Cache Refresh

- Updates stale cache with the latest data from the database.

---

### Cache Expiration

- Automatically removes stale cache entries after a configured time.

---

### Time To Live (TTL)

- Defines how long cache data remains valid.
- Prevents serving outdated data.

---

### Event-Based Invalidation

- Cache is updated or removed when an application event occurs.
- Common in Event-Driven Architecture.

---

### Distributed Cache Synchronization

- Ensures multiple application instances use consistent cached data.
- Commonly achieved using Redis.

---

### Eventual Consistency

- Cache and database may be temporarily different.
- They become consistent over time.

---

### Benefits

- Prevents stale data.
- Improves application reliability.
- Maintains data accuracy.
- Supports distributed systems.

---

## Small improvement 💡

Let's also add:

### Cache Coherency

- Cache Coherency - Ensures all cache copies contain the latest data.
- Important in distributed caching environments.