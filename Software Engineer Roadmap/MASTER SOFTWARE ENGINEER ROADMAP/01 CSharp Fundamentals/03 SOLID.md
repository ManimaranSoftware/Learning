### S - Single Responsibility Principle (SRP)

- A class should have only one responsibility and one reason to change.
- Improves maintainability and readability.
- Example - Separate `InvoiceService` and `EmailService`.

---

### O - Open/Closed Principle (OCP)

- Software entities should be open for extension but closed for modification.
- Add new functionality without changing existing code.
- Achieved using interfaces, inheritance and polymorphism.

---

### L - Liskov Substitution Principle (LSP)

- Derived class should be replaceable with its base class without changing program behavior.
- Child class should not break parent class functionality.
- Prevents incorrect inheritance.

---

### I - Interface Segregation Principle (ISP)

- Clients should not be forced to depend on methods they do not use.
- Prefer multiple small interfaces over one large interface.
- Improves flexibility and maintainability.

---

### D - Dependency Inversion Principle (DIP)

- High-level modules should not depend on low-level modules.
- Both should depend on abstractions (interfaces).
- Achieved using Dependency Injection (DI).

---

### Benefits

- Better maintainability
- Loose coupling
- High cohesion
- Easier testing
- Better scalability
- Improved code reusability