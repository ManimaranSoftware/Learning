
## SOLID Principles
- `S` → Single Responsibility Principle (SRP)
- `O` → Open/Closed Principle (OCP)
- `L` → Liskov Substitution Principle (LSP)
- `I` → Interface Segregation Principle (ISP)
- `D` → Dependency Inversion Principle (DIP)

> [!tip]
> **Memory Tip:** **SOLID** = Build Flexible & Maintainable Code

---

## DRY, KISS & YAGNI
- DRY → Don't Repeat Yourself
- KISS → Keep It Simple, Stupid
- YAGNI → You Aren't Gonna Need It
- Avoid Duplicate Logic
- Prefer Simple Solutions
- Build Only What is Needed

---

## Separation of Concerns (SoC)
- Divide Application into Independent Parts
- UI → Business Logic → Data Access
- Easier Maintenance
- Better Testing

---

## Dependency Injection
- Loose Coupling
- Constructor Injection (Preferred)
- Better Unit Testing
- Built-in IoC Container

> [!tip]
> **Memory Tip:** Don't Create Dependencies, Inject Them

---

## Repository Pattern
- Separates Data Access Logic
- Uses Interfaces
- Easier Testing
- Common with EF Core

---

## Unit of Work Pattern
- Groups Multiple Operations
- Single Transaction
- One `SaveChanges()`
- Ensures Data Consistency

---

## Factory Pattern
- Creates Objects
- Hides Object Creation Logic
- Reduces Tight Coupling

> [!tip]
> **Memory Tip:** Factory = Object Manufacturing Unit

---

## Singleton Pattern
- Only One Instance
- Shared Across Application
- Common for Logging & Configuration
- Thread Safe Implementation

---

## Builder Pattern
- Builds Complex Objects Step-by-Step
- Improves Readability
- Useful for Large Object Construction

---

## Strategy Pattern
- Multiple Algorithms
- Select Behavior at Runtime
- Removes Large `if-else` Blocks

> [!tip]
> **Memory Tip:** Strategy = Choose One Algorithm

---

## Observer Pattern
- Publisher → Subscriber
- Automatic Notifications
- Event-Driven Programming
- Used with Events & Messaging

---

## Adapter Pattern
- Converts One Interface to Another
- Integrates Incompatible Systems
- Legacy System Integration

---

## Decorator Pattern
- Adds Behavior Dynamically
- No Class Modification
- Wrapper Around Existing Object

---

## CQRS (Basics)
- Command → Write Operations
- Query → Read Operations
- Separate Read & Write Models
- Better Scalability

---

## Clean Architecture
- Separation of Layers
- Domain Independent
- Business Rules at Center
- Infrastructure Depends on Domain
- Easier Testing & Maintenance

---

## Interview Traps
- SOLID Principles
- Repository vs Unit of Work
- Factory vs Builder
- Factory vs Strategy
- Singleton vs Static Class
- Adapter vs Decorator
- Composition vs Inheritance
- Tight Coupling vs Loose Coupling
- Dependency Injection vs Dependency Inversion
- Clean Architecture vs Layered Architecture

---

## 30-Second Revision Formula

SOLID → DRY/KISS/YAGNI → SoC → DI → Repository → Unit of Work → Factory → Singleton → Builder → Strategy → Observer → Adapter → Decorator → CQRS → Clean Architecture