### Microservices

- Microservices - Architecture where an application is divided into small, independent services.
- Each service focuses on a specific business capability.

---

### Service Boundary

- Defines the responsibility of a microservice.
- Based on business capability, not database tables.

---

### API Gateway

- Single entry point for client requests.
- Handles routing, authentication and rate limiting.

---

### Service Discovery

- Enables services to find and communicate with each other dynamically.

---

### Distributed System

- Collection of independent services working together as one system.

---

### Loose Coupling

- Services communicate with minimal dependencies.
- Improves maintainability and scalability.

---

### Independent Deployment

- Each service can be deployed without affecting others.

---

### Fault Tolerance

- System continues operating even if one service fails.

---

### Circuit Breaker

- Stops requests to an unhealthy service.
- Prevents cascading failures.

---

### Retry Pattern

- Retries temporary failures before reporting an error.

---

### Saga Pattern

- Manages transactions across multiple services using compensating actions.

---

### Outbox Pattern

- Ensures reliable event publishing.
- Prevents data inconsistency between database and message broker.

---

### Distributed Transaction

- Transaction spanning multiple services.
- Usually avoided in Microservices.

---

### Benefits

- Better scalability.
- Independent deployments.
- Fault isolation.
- Technology flexibility.
- Easier maintenance.

---

## Small improvement 💡

Let's also add:

### Service Communication

- Services communicate using REST, gRPC or Messaging.
- Choose the communication style based on business requirements.