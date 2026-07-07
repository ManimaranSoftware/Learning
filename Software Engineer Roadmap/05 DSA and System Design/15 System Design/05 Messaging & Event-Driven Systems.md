### Messaging

- Messaging - Communication between systems using messages.
- Enables asynchronous processing.

---

### Event-Driven Architecture (EDA)

- Services communicate by publishing and consuming events.
- Promotes loose coupling.

---

### Event

- Event - Represents something that has happened in the system.
- Example - OrderPlaced, PaymentCompleted.

---

### Message Queue

- Stores messages until they are processed.
- Improves reliability.

---

### Producer

- Publishes messages or events.

---

### Consumer

- Receives and processes messages.

---

### Publish / Subscribe (Pub/Sub)

- One publisher sends messages to multiple subscribers.

---

### Point-to-Point

- One producer sends a message.
- One consumer processes it.

---

### Asynchronous Processing

- Sender continues processing without waiting for the receiver.

---

### Dead Letter Queue (DLQ)

- Stores messages that repeatedly fail processing.
- Prevents message loss.

---

### Idempotency

- Processing the same message multiple times produces the same result.
- Prevents duplicate processing.

---

### Eventual Consistency

- Data across services becomes consistent over time.
- Common in distributed systems.

---

### Benefits

- Loose coupling.
- Better scalability.
- Improved reliability.
- Fault tolerance.
- Independent services.

---

## Small improvement 💡

Let's also add:

### Message Broker

- Routes messages between producers and consumers.
- Examples - RabbitMQ, Kafka.