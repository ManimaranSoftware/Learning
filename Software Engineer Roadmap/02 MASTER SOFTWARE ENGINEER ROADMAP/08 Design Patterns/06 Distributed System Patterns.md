### Distributed System Pattern

- Solves common problems in distributed applications.
- Improves reliability, scalability and fault tolerance.

---

### Retry Pattern

- Automatically retries failed operations.
- Used for temporary failures like network or service outages.

---

### Circuit Breaker

- Stops sending requests to an unhealthy service.
- Prevents cascading failures.
- Allows recovery after a timeout.

---

### Timeout

- Stops waiting for a response after a specified time.
- Prevents resources from being blocked indefinitely.

---

### Bulkhead

- Isolates resources between different services or operations.
- Prevents one failure from affecting the entire system.

---

### Saga Pattern

- Manages distributed transactions across multiple services.
- Uses compensating actions instead of database transactions.

---

### Compensating Transaction

- Reverses a previously completed operation if a later step fails.

---

### Outbox Pattern

- Stores events in the same database transaction as business data.
- Ensures reliable event publishing.

---

### Idempotency

- Repeating the same request produces the same result.
- Prevents duplicate processing.

---

### Dead Letter Queue (DLQ)

- Stores messages that cannot be processed successfully.
- Helps with debugging and recovery.

---

### Health Check

- Monitors service availability.
- Used by orchestrators and load balancers.

---

### Benefits

- Improved reliability.
- Better fault tolerance.
- Easier recovery from failures.
- Better scalability.
- Reliable message processing.

---

## Small improvement 💡

Let's also add:

### Exponential Backoff

- Increases retry delay after each failure.
- Prevents overwhelming an unhealthy service.