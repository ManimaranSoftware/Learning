### Clean Architecture

- Clean Architecture - Organizes application into independent layers with dependencies pointing inward.
- Proposed by - Robert C. Martin (Uncle Bob).

---

### Core Principle

- Business logic should not depend on frameworks, databases or UI.

---

### Domain Layer

- Contains Entities and Business Rules.
- Independent of external technologies.

---

### Application Layer

- Contains Use Cases and Business Workflows.
- Coordinates Domain and Infrastructure.

---

### Infrastructure Layer

- Implements external concerns.
- Examples - Database, File System, Email, Third-party APIs.

---

### Presentation Layer

- Exposes the application to users.
- Examples - ASP.NET Core Web API, MVC, React.

---

### Dependency Rule

- Dependencies always point toward the Domain layer.
- Outer layers depend on inner layers.

---

### Entity

- Core business object containing business rules.

---

### Use Case

- Represents a business operation.
- Example - Create Order, Process Payment.

---

### Interface

- Defined in inner layers.
- Implemented by outer layers.

---

### Dependency Injection

- Used to inject Infrastructure implementations into Application layer.

---

### Benefits

- Independent of database.
- Independent of UI.
- Easy to test.
- Easy to maintain.
- Flexible architecture.

---

## Small improvement 💡

Let's also add:

### Dependency Flow

```
Presentation      ↓Application      ↓Domain      ↑Infrastructure
```

- Infrastructure depends on Application/Domain through interfaces.
- Domain depends on nothing.

### Dependency Direction

- Source code dependencies always point inward.
- Inner layers never depend on outer layers.