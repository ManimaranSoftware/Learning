(Reference page - most concepts were already covered in previous sections.)

### Repository Pattern

- Encapsulates data access logic.
- Provides abstraction over the data source.

---

### Unit of Work

- Coordinates multiple repository operations in a single transaction.
- Ensures data consistency.

---

### Dependency Injection (DI)

- Provides object dependencies instead of creating them manually.
- Improves loose coupling and testability.
- Common implementation of the IoC principle.

---

### Inversion of Control (IoC)

- Design principle where object creation and lifecycle are managed externally.
- Dependency Injection is one way to implement IoC.

---

### CQRS

- Separates read operations from write operations.
- Improves scalability and maintainability.

---

### Specification Pattern

- Encapsulates business rules or query conditions into reusable specifications.
- Reduces duplication of complex queries.

---

### Dependency Inversion Principle (DIP)

- High-level modules should depend on abstractions, not concrete implementations.
- One of the SOLID principles.

---

### Benefits

- Loose coupling.
- Better maintainability.
- Easier testing.
- Reusable architecture.
- Clear separation of responsibilities.

---

## Small improvement 💡

Let's also add:

### Service Layer

- Contains business logic and coordinates application operations.
- Acts as a bridge between Controllers and Repositories.