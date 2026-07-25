Messaging is a broad topic. For now, these are interview-focused notes. We can expand each concept in detail later if needed.
### Messaging

- Messaging - Communication between applications using messages.
- Enables asynchronous and decoupled communication.

---

### Synchronous Communication

- Sender waits for the receiver to respond.
- Example - REST API.

---

### Asynchronous Communication

- Sender does not wait for the receiver.
- Message is processed later.

---

### Message

- Message - Data exchanged between applications or services.

---

### Message Queue

- Stores messages until they are processed.
- Decouples producers and consumers.

---

### Producer

- Sends messages to a queue or topic.

---

### Consumer

- Receives and processes messages.

---

### Message Broker

- Manages message routing between producers and consumers.
- Examples - RabbitMQ, Kafka.

---

### Queue

- Messages are processed by one consumer.
- Implements Point-to-Point communication.

---

### Topic

- Messages are delivered to multiple subscribers.
- Implements Publish/Subscribe communication.

---

### Publish / Subscribe (Pub/Sub)

- Publisher sends messages.
- Multiple subscribers receive the same message.

---

### Point-to-Point

- One producer sends a message.
- One consumer processes the message.

---

### RabbitMQ

- Message broker implementing AMQP.
- Best suited for reliable message delivery and task queues.

---

### Apache Kafka

- Distributed event streaming platform.
- Best suited for high-throughput event streaming and analytics.

---

### AWS SQS

- Fully managed message queue service.
- Supports Standard Queue and FIFO Queue.

---

### AWS SNS

- Publish/Subscribe messaging service.
- Delivers messages to multiple subscribers.

---

### Amazon EventBridge

- Event bus service for routing events between AWS services and applications.

---

### ACK (Acknowledgement)

- Confirms that a message has been processed successfully.

---

### Retry

- Retries processing when a temporary failure occurs.

---

### Dead Letter Queue (DLQ)

- Stores messages that repeatedly fail processing.
- Used for debugging and recovery.

---

### Idempotency

- Prevents duplicate message processing.
- Ensures repeated processing produces the same result.

---

### Message Ordering

- Ensures messages are processed in the expected sequence.
- Important for business-critical workflows.

---

### Benefits

- Loose coupling.
- Better scalability.
- Reliable communication.
- Fault tolerance.
- Asynchronous processing.

---

## Small improvement 💡

Let's also add:

### Event

- Event - Notification that something has happened.
- Consumers react to the event without the producer knowing about them.