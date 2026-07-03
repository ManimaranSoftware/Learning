### Dependency Injection (DI)

- Dependency Injection - Design pattern for providing object dependencies instead of creating them manually.
- Purpose - Reduces coupling and improves testability.
- Built-in - Supported by ASP.NET Core.

---

### Dependency

- Dependency - Object required by another object to perform its work.

---

### Inversion of Control (IoC)

- IoC - Principle where framework manages object creation and lifecycle.
- DI - One implementation of IoC.

---

### Service Registration

- Registers services in the DI container.
- Configured in `Program.cs`.

---

### Service Resolution

- DI container automatically creates and injects required dependencies.

---

### Constructor Injection

- Dependencies provided through constructor.
- Most recommended approach.

---

### Method Injection

- Dependencies passed as method parameters.

---

### Property Injection

- Dependencies assigned through properties.
- Less commonly used.

---

### Service Lifetime

- Singleton - One instance for entire application lifetime.
- Scoped - One instance per HTTP request.
- Transient - New instance every time requested.

---

### DI Container

- Built-in container manages service registration and resolution.

---

### Benefits

- Loose coupling.
- Better maintainability.
- Easier unit testing.
- Better code reusability.
- Centralized dependency management.