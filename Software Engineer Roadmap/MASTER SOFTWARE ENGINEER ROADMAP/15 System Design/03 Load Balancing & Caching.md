### Load Balancer

- Load Balancer - Distributes incoming requests across multiple servers.
- Improves availability and scalability.

---

### Load Balancing

- Process of distributing traffic evenly among multiple servers.
- Prevents server overload.

---

### Round Robin

- Requests are distributed sequentially to each server.

---

### Least Connections

- Requests are sent to the server with the fewest active connections.

---

### Health Check

- Monitors server health.
- Removes unhealthy servers from request routing.

---

### Failover

- Automatically redirects traffic to healthy servers when a failure occurs.

---

### Reverse Proxy

- Receives client requests and forwards them to backend servers.
- Common Examples - NGINX, HAProxy.

---

### Cache

- Stores frequently accessed data.
- Reduces response time and database load.

---

### Cache-Aside

- Application checks cache first.
- On cache miss, retrieves data from the database and updates the cache.

---

### Distributed Cache

- Shared cache accessible by multiple application instances.
- Example - Redis.

---

### CDN (Content Delivery Network)

- Delivers static content from servers closer to users.
- Reduces latency.
- Example - Amazon CloudFront.

---

### Benefits

- Better scalability.
- Faster response times.
- High availability.
- Reduced database load.
- Improved user experience.

---

## Small improvement 💡

Let's also add:

### Sticky Session

- Routes a user's requests to the same server.
- Useful for stateful applications.
- Generally avoided for stateless APIs.