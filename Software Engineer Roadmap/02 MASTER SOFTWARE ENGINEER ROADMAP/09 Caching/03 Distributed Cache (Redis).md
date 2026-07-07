### Redis

- Redis (Remote Dictionary Server) - In-memory data store used for caching, messaging and fast data access.

---

### Distributed Cache

- Distributed Cache - Shared cache accessible by multiple application instances.
- Suitable for scalable applications.

---

### IDistributedCache

- ASP.NET Core interface for distributed caching.
- Supports Redis and SQL Server distributed cache.

---

### Cache Key

- Unique identifier for cached data.
- Should be consistent and meaningful.

---

### Set()

- Stores data in the distributed cache.

---

### Get()

- Retrieves cached data.

---

### Remove()

- Removes a cache entry.

---

### Refresh()

- Resets the sliding expiration of a cache entry.

---

### Serialization

- Objects are serialized before storing in Redis.
- Common formats - JSON, MessagePack.

---

### Persistence

- Redis can optionally persist data to disk.
- Supports RDB and AOF persistence.

---

### Pub/Sub

- Publish/Subscribe messaging mechanism.
- Enables real-time communication between applications.

---

### Distributed Lock

- Prevents multiple applications from processing the same resource simultaneously.

---

### Benefits

- Shared across multiple servers.
- Very high performance.
- Reduces database load.
- Supports horizontal scaling.

---

## Small improvement 💡

Let's also add:

### Common Redis Uses

- Distributed Cache
- Session Storage
- Rate Limiting
- Distributed Locking
- Pub/Sub Messaging