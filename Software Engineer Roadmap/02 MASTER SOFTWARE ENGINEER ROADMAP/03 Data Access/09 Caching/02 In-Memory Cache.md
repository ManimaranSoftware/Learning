### In-Memory Cache

- In-Memory Cache - Stores cached data in the application's memory.
- Available only within the current application instance.

---

### IMemoryCache

- Built-in ASP.NET Core caching service.
- Used to store and retrieve data in memory.

---

### Set()

- Adds data to the cache.

---

### Get()

- Retrieves data from the cache.

---

### Remove()

- Removes a cache entry.

---

### TryGetValue()

- Checks whether a cache key exists.
- Retrieves the value if present.

---

### Cache Key

- Unique identifier for cached data.
- Should be meaningful and unique.

---

### Absolute Expiration

- Cache expires after a fixed time.

---

### Sliding Expiration

- Expiration time resets whenever the cache entry is accessed.

---

### Cache Entry Options

- Configure expiration, priority and size for cache entries.

---

### Cache Priority

- Determines which entries are removed first when memory is low.
- Examples - Low, Normal, High, NeverRemove.

---

### Benefits

- Extremely fast access.
- Easy to implement.
- Reduces database queries.
- Suitable for single-server applications.

---

## Small improvement 💡

Let's also add:

### Limitation

- Cache is lost when the application restarts.
- Not shared across multiple application instances.
---
### Cache Size Limit

- Limits the total cache size.
- Helps prevent excessive memory usage.
