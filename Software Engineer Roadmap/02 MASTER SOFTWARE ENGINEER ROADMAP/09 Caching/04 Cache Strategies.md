### Cache-Aside (Lazy Loading)

- Application checks cache first.
- On Cache Miss, retrieves data from database and stores it in cache.
- Most commonly used caching strategy.

---

### Read-Through

- Application reads data only from the cache.
- Cache retrieves missing data from the database automatically.

---

### Write-Through

- Data is written to both cache and database at the same time.
- Ensures cache and database remain consistent.

---

### Write-Behind (Write-Back)

- Data is written to the cache immediately.
- Cache updates the database asynchronously.
- Improves write performance.

---

### Refresh-Ahead

- Refreshes frequently accessed cache entries before they expire.
- Reduces cache misses.

---

### Cache-First

- Always attempt to read from cache before accessing the database.

---

### Database-First

- Read directly from the database.
- Cache updated only when necessary.

---

### Cache Warming

- Preloads frequently accessed data into cache during application startup.

---

### Cache Eviction

- Removes outdated or less frequently used cache entries.
- Prevents excessive memory usage.

---

### Benefits

- Reduced database load.
- Faster response times.
- Better scalability.
- Flexible caching approaches.

---

## Small improvement 💡

Let's also add:

### Cache-Aside Flow

- Cache → Database → Cache
- On Cache Miss, fetch from database and update cache.