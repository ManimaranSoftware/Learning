
## What is Microservices?
- Small Independent Services
- Single Business Responsibility
- Independently Deployable
- Own Database
- Communicate via APIs/Messaging

> [!tip]
> **Memory Tip:** One Service = One Business Capability

---

## Monolith vs Microservices
- Monolith → Single Application
- Microservices → Multiple Independent Services
- Monolith → Easier Initially
- Microservices → Better Scalability & Maintainability

---

## Microservice Characteristics
- Loosely Coupled
- Highly Cohesive
- Independent Deployment
- Fault Isolation
- Technology Independent

---

## Communication
- Synchronous → REST API, gRPC
- Asynchronous → Message Queue
- Request/Response
- Event-Driven Communication

> [!tip]
> **Memory Tip:** Sync = Wait | Async = Don't Wait

---

## API Gateway
- Single Entry Point
- Routing
- Authentication
- Rate Limiting
- Load Balancing
- Aggregates Responses

---

## Service Discovery
- Dynamically Finds Services
- Avoids Hardcoded URLs
- Client-side Discovery
- Server-side Discovery

---

## Database Per Service
- Each Service Owns Its Database
- No Shared Database
- Loose Coupling
- Independent Scaling

---

## Event-Driven Architecture
- Publisher → Event → Subscriber
- Asynchronous Communication
- Loose Coupling
- Better Scalability

---

## Message Brokers
- RabbitMQ
- Apache Kafka
- AWS SQS
- Azure Service Bus

> [!tip]
> **Memory Tip:** Broker = Post Office for Messages

---

## Resiliency Patterns
- Retry
- Circuit Breaker
- Timeout
- Fallback
- Bulkhead

---

## Distributed Transactions
- Avoid Two-Phase Commit
- Saga Pattern
- Eventual Consistency
- Compensation Transactions

---

## Scalability
- Horizontal Scaling
- Load Balancer
- Stateless Services
- Auto Scaling

---

## Logging & Monitoring
- Centralized Logging
- Distributed Tracing
- Correlation ID
- Health Checks
- Metrics

---

## Security
- JWT Authentication
- API Gateway Authentication
- HTTPS
- Service-to-Service Authentication
- OAuth/OpenID Connect

---

## Containerization
- Docker
- Kubernetes
- Independent Deployment
- Consistent Runtime Environment

---

## Best Practices
- Single Responsibility
- Independent Deployment
- API Versioning
- Database Per Service
- Stateless Services
- Centralized Logging
- Health Checks
- Circuit Breaker

---

## Interview Traps
- Monolith vs Microservices
- REST vs Messaging
- Sync vs Async Communication
- API Gateway vs Load Balancer
- RabbitMQ vs Kafka
- Database Per Service vs Shared Database
- Scalability vs Availability
- Saga vs Two-Phase Commit
- Stateless vs Stateful Services
- Docker vs Kubernetes

---

## 30-Second Revision Formula

Microservices → Monolith → Characteristics → Communication → API Gateway → Service Discovery → Database → Event-Driven → Message Broker → Resiliency → Distributed Transactions → Scalability → Logging → Security → Containers → Best Practices