### Repository Pattern

- Repository Pattern - Encapsulates data access logic.
- Provides abstraction over the data source.
- Promotes separation of concerns.

---

### Repository Interface

- Defines data access contract.
- Improves loose coupling and testability.

---

### Repository Implementation

- Concrete implementation of Repository Interface.
- Uses EF Core, Dapper or ADO.NET.

---

### Generic Repository

- Reusable repository implementation for multiple entities.
- Reduces duplicate CRUD code.

---

### Custom Repository

- Repository containing business-specific queries.
- Used when Generic Repository is not sufficient.

---

### Unit of Work

- Coordinates multiple repository operations in a single transaction.
- Ensures all operations succeed or fail together.

---

### SaveChanges()

- Persists all pending changes managed by the Unit of Work.

---

### Transaction Boundary

- Defines the scope of a business transaction.
- Usually one business operation.

---

### Dependency Injection

- Repository and Unit of Work are commonly registered through DI.
- Promotes maintainability and testability.

---

### Generic Repository Limitation

- May become too generic for complex business queries.
- Custom repositories are preferred when domain-specific logic is required.

---

### Repository Responsibility

- Repository should contain only data access logic.
- Business logic belongs in the Service/Application layer.

---

### Benefits

- Separation of concerns.
- Better maintainability.
- Improved testability.
- Reusable data access logic.
- Centralized transaction management.