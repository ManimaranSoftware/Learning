## System Design Basics
- Design Scalable Systems
- Design Reliable Systems
- Design Maintainable Systems
- Balance Performance & Cost

> [!tip]
> **Memory Tip:** System Design = Scale + Reliability + Maintainability

---

## Functional Requirements
- What the System Should Do
- Business Features
- User Requirements
- APIs

---

## Non-Functional Requirements (NFRs)
- Scalability
- Availability
- Reliability
- Performance
- Security
- Maintainability

---

## Scalability
- Vertical Scaling → Increase Server Resources
- Horizontal Scaling → Add More Servers
- Stateless Services
- Auto Scaling

> [!tip]
> **Memory Tip:** Vertical = Bigger Machine | Horizontal = More Machines

---

## Load Balancer
- Distributes Traffic
- Prevents Server Overload
- Improves Availability
- Improves Scalability

---

## Caching
- Reduces Database Calls
- Improves Response Time
- In-Memory Cache
- Distributed Cache (`Redis`)

---

## Database Design
- SQL → Structured Data
- NoSQL → Flexible Schema
- Normalization
- Denormalization
- Indexing

---

## CAP Theorem
- Consistency
- Availability
- Partition Tolerance
- Choose Any Two During Network Partition

> [!tip]
> **Memory Tip:** CAP = C + A + P (Only Two During Failure)

---

## Consistency Models
- Strong Consistency
- Eventual Consistency
- Read Your Writes

---

## Messaging
- Synchronous → REST/gRPC
- Asynchronous → Queue
- Event-Driven Architecture
- Message Broker (`SQS`, RabbitMQ, Kafka)

---

## API Design
- REST APIs
- Stateless
- Versioning
- Pagination
- Proper Status Codes

---

## High Availability
- Multiple Instances
- Load Balancer
- Health Checks
- Failover
- Redundancy

---

## Logging & Monitoring
- Centralized Logging
- Metrics
- Distributed Tracing
- Correlation ID
- Alerts

---

## Security
- Authentication
- Authorization
- HTTPS
- JWT
- Encryption
- Secrets Management

---

## Performance Optimization
- Caching
- Database Indexes
- Async Processing
- Connection Pooling
- CDN
- Compression

---

## Common Design Flow
- Gather Requirements
- Estimate Scale
- Design High-Level Architecture
- Design Database
- Design APIs
- Identify Bottlenecks
- Optimize Performance

> [!tip]
> **Memory Tip:** Requirements → Architecture → Database → APIs → Scale

---

## Interview Traps
- Vertical vs Horizontal Scaling
- SQL vs NoSQL
- Cache vs Database
- Load Balancer vs API Gateway
- REST vs Messaging
- Strong Consistency vs Eventual Consistency
- Stateless vs Stateful
- Scaling vs Availability
- Normalization vs Denormalization
- Monolith vs Microservices

---

## 30-Second Revision Formula

Requirements → NFRs → Scalability → Load Balancer → Caching → Database → CAP → Consistency → Messaging → APIs → High Availability → Logging → Security → Performance → Design Flow