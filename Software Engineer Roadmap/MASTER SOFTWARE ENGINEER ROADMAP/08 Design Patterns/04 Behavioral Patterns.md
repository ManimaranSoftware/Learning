### Behavioral Pattern

- Behavioral Pattern - Focuses on communication and responsibility between objects.

---

### Strategy

- Defines a family of algorithms.
- Allows algorithms to be selected at runtime.

---

### Observer

- One object notifies multiple dependent objects when its state changes.
- Commonly used in event-driven programming.

---

### Command

- Encapsulates a request as an object.
- Supports queuing, logging and undo operations.

---

### Mediator

- Centralizes communication between multiple objects.
- Reduces direct dependencies.
- Commonly used in CQRS (e.g., MediatR).

---

### State

- Changes an object's behavior based on its internal state.
- Eliminates large conditional statements.

---

### Chain of Responsibility

- Passes a request through a chain of handlers.
- Each handler decides whether to process or forward it.

---

### Template Method

- Defines the skeleton of an algorithm.
- Allows subclasses to customize specific steps.

---

### Specification

- Encapsulates business rules or query conditions into reusable specifications.
- Commonly used with Repository Pattern.

---

### Iterator

- Sequentially accesses elements of a collection without exposing its internal structure.

---

### Benefits

- Better separation of responsibilities.
- Flexible behavior.
- Reduced coupling.
- Improved maintainability.
- Better code reusability.

---

## Small improvement 💡

Let's also add:

### Visitor

- Separates operations from object structure.
- Useful when adding new operations without modifying existing classes.

_(Basic knowledge is enough.)_