
## Messaging Basics
- Asynchronous Communication
- Decouples Services
- Improves Scalability
- Improves Reliability

> [!tip]
> **Memory Tip:** Messaging = Send Now, Process Later

---

## Synchronous vs Asynchronous
- Synchronous → Wait for Response
- Asynchronous → Continue Processing
- REST → Usually Synchronous
- Queue → Usually Asynchronous

> [!tip]
> **Memory Tip:** Sync = Wait | Async = Don't Wait

---

## Message Queue
- Stores Messages
- Producer → Queue → Consumer
- Reliable Delivery
- Buffers High Traffic

---

## Producer & Consumer
- Producer → Sends Messages
- Consumer → Processes Messages
- Independent Components
- Loose Coupling

---

## RabbitMQ
- Message Broker
- AMQP Protocol
- Queue-Based Messaging
- Reliable Delivery
- Supports Routing

> [!tip]
> **Memory Tip:** RabbitMQ = Queue First

---

## Apache Kafka
- Distributed Event Streaming
- High Throughput
- Durable Log Storage
- Event Replay
- Partition-Based Scaling

> [!tip]
> **Memory Tip:** Kafka = Event Streaming Platform

---

## AWS SQS
- Fully Managed Queue
- Serverless
- Standard Queue
- FIFO Queue
- Dead Letter Queue (DLQ)

---

## AWS SNS
- Publish/Subscribe Service
- One-to-Many Messaging
- Push Notifications
- Integrates with SQS, Lambda, Email, SMS

---

## Event-Driven Architecture
- Publisher
- Event
- Subscriber
- Loose Coupling
- Independent Processing

---

## Queue Patterns
- Point-to-Point
- Publish/Subscribe
- Fan-Out
- Event Broadcasting

---

## Dead Letter Queue (DLQ)
- Stores Failed Messages
- Retry Analysis
- Prevents Message Loss
- Helps Debugging

---

## Idempotency
- Safe to Process Multiple Times
- Prevents Duplicate Operations
- Common in Payment & Order Systems

> [!tip]
> **Memory Tip:** Idempotent = Same Result Every Time

---

## Retry Strategies
- Immediate Retry
- Exponential Backoff
- DLQ After Max Retries
- Avoid Infinite Retry Loops

---

## Ordering
- RabbitMQ → Queue Order
- Kafka → Partition Order
- SQS FIFO → Guaranteed Order
- SQS Standard → Best Effort Order

---

## Common Use Cases
- Order Processing
- Email Notifications
- Invoice Generation
- ETL Pipelines
- Audit Logging
- Background Jobs

---

## Best Practices
- Keep Messages Small
- Use Idempotent Consumers
- Implement Retries
- Configure DLQ
- Monitor Queue Length
- Handle Duplicate Messages

---

## Interview Traps
- RabbitMQ vs Kafka
- Queue vs Topic
- SQS vs SNS
- Standard Queue vs FIFO Queue
- Sync vs Async
- Event vs Message
- Queue vs Pub/Sub
- Retry vs DLQ
- Message Ordering
- At-Least-Once vs Exactly-Once Delivery

---

## 30-Second Revision Formula

Messaging → Sync/Async → Queue → Producer/Consumer → RabbitMQ → Kafka → SQS → SNS → Event-Driven → Queue Patterns → DLQ → Idempotency → Retry → Ordering → Use Cases → Best Practices