### Event-Driven Architecture (EDA)

- Event-Driven Architecture - Architectural style where services communicate through events.
- Promotes loose coupling between services.

---

### Event

- Event - Notification that something has happened in the system.
- Examples - OrderPlaced, PaymentCompleted, UserRegistered.

---

### Event Producer

- Service that publishes events.

---

### Event Consumer

- Service that listens to and processes events.

---

### Event Broker

- Middleware that routes events between producers and consumers.
- Examples - Kafka, RabbitMQ, AWS SNS/SQS.

---

### Publish

- Producer sends an event to the broker.

---

### Subscribe

- Consumer registers interest in specific events.

---

### Asynchronous Communication

- Producer does not wait for the consumer to finish processing.
- Improves responsiveness and scalability.

---

### Loose Coupling

- Services communicate through events instead of direct calls.
- Changes in one service have minimal impact on others.

---

### Eventual Consistency

- Data across services becomes consistent over time.
- Common in distributed systems.

---

### Benefits

- Better scalability.
- Loose coupling.
- Independent services.
- Improved fault tolerance.
- Easier integration.

---

## Small improvement 💡

Let's also add:

### Event Payload

- Event Payload - Data carried with an event.
- Should contain only the information required by consumers