### Cache

- Cache - Temporary storage for frequently accessed data.
- Reduces database calls and improves application performance.

---

### Caching

- Caching - Storing frequently used data for faster retrieval.

---

### Cache Hit

- Requested data is found in the cache.

---

### Cache Miss

- Requested data is not found in the cache.
- Data is retrieved from the original source.

---

### Cache Warm-up

- Preloads frequently accessed data into the cache during application startup.

---

### Cache Invalidation

- Removes or updates stale cache entries.
- Keeps cached data consistent with the data source.

---

### Time To Live (TTL)

- Defines how long cached data remains valid.
- Data expires automatically after the configured duration.

---

### Expiration

- Absolute Expiration - Cache expires at a fixed time.
- Sliding Expiration - Expiration resets whenever the cache is accessed.

---

### Eviction

- Automatic removal of cache entries.
- Occurs due to expiration or memory limits.

---

### Benefits

- Faster response time.
- Reduced database load.
- Better scalability.
- Improved user experience.

---

## Small improvement 💡

Let's also add:

### Cache Stampede

- Multiple requests regenerate the same expired cache simultaneously.
- Can overload the database.