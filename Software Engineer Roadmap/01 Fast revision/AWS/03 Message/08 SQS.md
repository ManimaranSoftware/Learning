> **SQS → Queue → Producer → Consumer → Standard → FIFO → Visibility Timeout → DLQ → Asynchronous**

---

# 60-Second Revision

**SQS**

- Fully managed message queuing service.
- Enables asynchronous communication between services.

**Producer**

- Sends messages to the queue.

**Consumer**

- Receives and processes messages.

**Queue Types**

- Standard: High throughput, best-effort ordering.
- FIFO: Preserves message order.

**Visibility Timeout**

- Temporarily hides a message while it is being processed.

**Dead Letter Queue**

- Stores messages that repeatedly fail.

**Benefits**

- Decouples services.
- Handles traffic spikes.
- Supports retries.
- Improves reliability.

**Project Example**

- Used for background processing such as notifications, report generation, or other long-running tasks without delaying the API response.