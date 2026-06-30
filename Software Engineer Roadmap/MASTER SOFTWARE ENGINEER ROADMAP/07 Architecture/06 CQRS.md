### CQRS

- CQRS (Command Query Responsibility Segregation) - Separates read operations from write operations.
- Improves scalability and maintainability.

---

### Command

- Command - Operation that modifies data.
- Examples - Create, Update, Delete.

---

### Query

- Query - Operation that retrieves data.
- Does not modify application state.

---

### Command Handler

- Processes command requests.
- Contains business logic for write operations.

---

### Query Handler

- Processes query requests.
- Optimized for read operations.

---

### Read Model

- Optimized model for querying data.
- May differ from the write model.

---

### Write Model

- Responsible for validating business rules and updating data.

---

### Separation of Responsibility

- Read and write operations are implemented independently.
- Improves flexibility and maintainability.

---

### Event Integration

- CQRS is often combined with Event-Driven Architecture.
- Events synchronize read and write models.

---

### Benefits

- Better scalability.
- Clear separation of responsibilities.
- Optimized read and write performance.
- Easier maintenance.
- Improved flexibility.

---

## Small improvement 💡

Let's also add:

### Mediator Pattern

- Often used to implement CQRS.
- Routes Commands and Queries to their respective Handlers.
- Popular library - MediatR.

_(We'll study the Mediator Pattern in Design Patterns.)_