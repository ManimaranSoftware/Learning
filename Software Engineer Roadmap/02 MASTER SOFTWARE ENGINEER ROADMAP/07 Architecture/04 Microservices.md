
### Microservices

- Microservices - Architectural style where an application is built as a collection of small, independent services.
- Each service focuses on a single business capability.

---

### Service

- Service - Independent application responsible for a specific business function.

---

### Single Responsibility

- Each microservice should have one business responsibility.

---

### Independent Deployment

- Each service can be deployed independently without affecting others.

---

### Independent Database

- Each microservice owns its own database.
- Avoid sharing databases between services.

---

### Communication

- Services communicate using REST, gRPC, Message Queue or Events.

---

### API Gateway

- Single entry point for client requests.
- Handles routing, authentication and rate limiting.

---

### Service Discovery

- Allows services to locate each other dynamically.

---

### Load Balancer

- Distributes requests across multiple service instances.

---

### Fault Tolerance

- Application continues functioning even if one service fails.

---

### Scalability

- Scale only the services that need additional resources.

---

### Distributed System

- Multiple services running on different servers working together.

---

### Event-Driven Communication

- Services communicate through events using a message broker.
- Reduces direct dependencies.

---

### Benefits

- Independent deployment.
- Better scalability.
- Fault isolation.
- Technology flexibility.
- Easier maintenance.

---

## Small improvement 💡

Let's also add:

### Monolith

- Monolith - Entire application deployed as a single unit.
- Simpler for small applications.
- Harder to scale independently.

### Service Boundary

- Service Boundary - Defines what belongs inside a microservice.
- Based on business capability, not database tables.

This is a **senior-level concept** that's commonly discussed in microservices interviews.