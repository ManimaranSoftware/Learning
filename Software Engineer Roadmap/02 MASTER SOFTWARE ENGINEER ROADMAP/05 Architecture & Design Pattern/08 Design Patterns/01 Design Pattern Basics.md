# Design Patterns

## What is a Design Pattern?

A **Design Pattern** is a proven, reusable solution to a commonly occurring software design problem.

> A design pattern is **not code**. It is a blueprint or template for solving a recurring design problem.

### Benefits

- Improves code reusability
- Improves maintainability
- Promotes loose coupling
- Makes code easier to extend
- Improves readability
- Encourages best practices

---

# Gang of Four (GoF)

The **Gang of Four (GoF)** introduced the 23 classic Object-Oriented Design Patterns in the book:

**Design Patterns: Elements of Reusable Object-Oriented Software (1994)**

### Authors

- Erich Gamma
- Richard Helm
- Ralph Johnson
- John Vlissides

The 23 patterns are grouped into three categories:

- Creational (5)
- Structural (7)
- Behavioral (11)

---

# Categories of GoF Design Patterns

## 1. Creational Patterns

### Purpose

Focuses on **how objects are created**.

### Goal

- Hide object creation logic
- Make object creation flexible
- Reduce tight coupling

### Patterns

1. **Singleton** – Ensures only one instance of a class exists and provides a global access point.
2. **Factory Method** – Creates objects through a factory method without specifying the exact concrete class.
3. **Abstract Factory** – Creates families of related objects without depending on their concrete classes.
4. **Builder** – Constructs complex objects step by step while allowing different representations.
5. **Prototype** – Creates new objects by cloning an existing object instead of creating one from scratch.

---

## 2. Structural Patterns

### Purpose

Focuses on **how classes and objects are composed**.

### Goal

- Build flexible relationships
- Simplify complex structures
- Extend functionality without modifying existing code

### Patterns

1. **Adapter** – Converts one interface into another so incompatible classes can work together.
2. **Bridge** – Separates abstraction from implementation so both can evolve independently.
3. **Composite** – Treats individual objects and groups of objects uniformly in a tree structure.
4. **Decorator** – Adds new behavior to an object dynamically without modifying its class.
5. **Facade** – Provides a simplified interface to a complex subsystem.
6. **Flyweight** – Reduces memory usage by sharing common object data among multiple objects.
7. **Proxy** – Provides a placeholder or surrogate object to control access to another object.

---

## 3. Behavioral Patterns

### Purpose

Focuses on **communication and responsibility between objects**.

### Goal

- Define object interaction
- Improve collaboration
- Make behavior flexible

### Patterns

1. **Chain of Responsibility** – Passes a request through a chain of handlers until one processes it.
2. **Command** – Encapsulates a request as an object to support queuing, logging, and undo operations.
3. **Interpreter** – Defines a grammar and interprets expressions in a language.
4. **Iterator** – Provides a way to access elements of a collection sequentially without exposing its implementation.
5. **Mediator** – Centralizes communication between objects to reduce direct dependencies.
6. **Memento** – Captures and restores an object's previous state without exposing its internal details.
7. **Observer** – Notifies dependent objects automatically when an object's state changes.
8. **State** – Changes an object's behavior when its internal state changes.
9. **Strategy** – Encapsulates interchangeable algorithms and selects one at runtime.
10. **Template Method** – Defines the skeleton of an algorithm while allowing subclasses to customize specific steps.
11. **Visitor** – Adds new operations to objects without modifying their classes.

---

# Enterprise Application Patterns

These are **NOT** part of the GoF 23.

They solve common enterprise application problems such as data access, business logic and transactions.

### Common Patterns

- Repository
- Unit of Work
- Service Layer
- Data Mapper
- Identity Map
- Lazy Loading

> These patterns were popularized by Martin Fowler in *Patterns of Enterprise Application Architecture*.

---

# Architectural Patterns

Architectural patterns define the **overall structure of an application**.

### Examples

- Layered (N-Tier)
- Clean Architecture
- MVC
- MVVM
- CQRS
- Microservices
- Event-Driven Architecture

---

# Distributed System Patterns

Used when multiple services communicate across a network.

### Common Patterns

- Retry
- Circuit Breaker
- Saga
- Outbox
- Bulkhead
- API Gateway

---

# Design Principles

Design principles guide how software should be designed.

They are **not** design patterns.

## SOLID

- Single Responsibility Principle (SRP)
- Open/Closed Principle (OCP)
- Liskov Substitution Principle (LSP)
- Interface Segregation Principle (ISP)
- Dependency Inversion Principle (DIP)

---

## Composition over Inheritance

Prefer combining objects rather than inheriting behavior.

### Benefits

- More flexible
- Easier to extend
- Lower coupling

---

## Loose Coupling

Components should know as little as possible about each other.

### Benefits

- Easier testing
- Easier maintenance
- Easier replacement of implementations

---

## High Cohesion

A class should contain closely related responsibilities.

### Benefits

- Better readability
- Easier maintenance
- Simpler debugging

---

# When to Use Design Patterns

Use a design pattern when:

- A design problem occurs repeatedly
- The pattern makes the solution simpler
- It improves maintainability
- It reduces coupling
- It increases flexibility

Avoid using a design pattern when:

- The solution becomes unnecessarily complex
- A simple solution is sufficient
- The pattern adds no real benefit

---

# Quick Summary

| Category | Purpose | Examples |
|----------|----------|----------|
| GoF Creational | Object creation | Singleton, Factory, Builder |
| GoF Structural | Object composition | Adapter, Decorator, Facade |
| GoF Behavioral | Object interaction | Strategy, Observer, Command |
| Enterprise Patterns | Enterprise application design | Repository, Unit of Work |
| Architectural Patterns | Overall application structure | Clean Architecture, MVC, Microservices |
| Distributed Patterns | Communication between services | Retry, Circuit Breaker, Saga |

---

# Interview Tip

Remember this hierarchy:

Software Design
├── Design Principles
│   ├── SOLID
│   ├── Composition over Inheritance
│   ├── Loose Coupling
│   └── High Cohesion
│
├── GoF Design Patterns
│   ├── Creational (5)
│   ├── Structural (7)
│   └── Behavioral (11)
│
├── Enterprise Patterns
│   ├── Repository
│   ├── Unit of Work
│   └── Service Layer
│
├── Architectural Patterns
│   ├── Layered
│   ├── Clean Architecture
│   ├── MVC
│   ├── CQRS
│   └── Microservices
│
└── Distributed System Patterns
    ├── Retry
    ├── Circuit Breaker
    ├── Saga
    └── Outbox