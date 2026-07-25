## 01 C# Basics

- `var` vs `dynamic` vs `object`
- Value type vs Reference type
- Stack vs Heap — what is stored where?
- Nullable type — `HasValue`, `Value`
- `??` vs `??=` vs `?.`
- `is` vs `as`
- switch vs switch expression
- `break` vs `continue` vs `return`
- Method overloading
- Optional parameters vs Named parameters
- Expression-bodied method (`=>`)
- `ref` vs `out` vs `in` vs `params`
- String vs StringBuilder
- `==` vs `.Equals()` vs `ReferenceEquals()`
- `IsNullOrEmpty` vs `IsNullOrWhiteSpace`
- String interpolation
- `StringComparison.OrdinalIgnoreCase`
- Enum — when and why
- Struct vs Class
- Record vs Class
- `with` expression in records
- Implicit vs Explicit conversion
- Boxing vs Unboxing
- `File` vs `FileInfo`
- `StreamReader` vs `StreamWriter`
- Serialization vs Deserialization
- `System.Text.Json` vs `Newtonsoft.Json`
- Reflection
- Attributes — `[Obsolete]`, `[Required]`, `[Authorize]`

---

## 02 OOP

- Class vs Object
- Encapsulation
- Abstraction
- Inheritance — Single, Multilevel, Hierarchical
- Polymorphism — Compile-time vs Runtime
- Method Overloading vs Method Overriding
- Interface vs Abstract Class
- Static class vs Static method vs Static constructor
- Virtual vs Override vs Sealed
- Access Modifiers — `public`, `private`, `protected`, `internal`, `protected internal`, `private protected`

---

## 03 SOLID

- Single Responsibility Principle (SRP)
- Open/Closed Principle (OCP)
- Liskov Substitution Principle (LSP)
- Interface Segregation Principle (ISP)
- Dependency Inversion Principle (DIP)

---

## 04 Memory Management

- Stack vs Heap
- Value type vs Reference type — storage exceptions
- Boxing vs Unboxing
- Garbage Collection (GC)
- `IDisposable` and `Dispose()`
- `using` statement — how it works internally
- When does value type go to heap?
- When does reference variable go to stack?

---

## 05 Collections

- Array vs `List<T>`
- `List<T>` vs `ArrayList`
- `Dictionary<TKey, TValue>` vs `Hashtable`
- `HashSet<T>` — uniqueness
- `Queue<T>` (FIFO) vs `Stack<T>` (LIFO)
- `LinkedList<T>` — when to use
- Concurrent Collections — `ConcurrentDictionary`, `ConcurrentQueue`
- `IEnumerable<T>` vs `ICollection<T>` vs `IList<T>`
- `IReadOnlyCollection<T>` vs `IReadOnlyList<T>`
- Interface vs Concrete class — which to use as parameter type

---

## 06 Generics

- What are Generics? Why use them?
- Generic class, method, interface, delegate
- Generic constraints — `where T : class`, `struct`, `new()`, `BaseClass`, `IInterface`
- `Action<T>` vs `Func<T>` vs `Predicate<T>`
- Type parameters — `T`, `TKey`, `TValue`, `TResult`

---

## 07 Delegates, Events, Lambda Expressions

- Delegate - what and why
- Single-cast vs Multicast delegate
- Anonymous Type vs Anonymous Method vs Lambda Expression
- `Action` vs `Func` vs `Predicate`
- Event - Publisher-Subscriber pattern
- Delegate vs Event
- `EventHandler` and `EventArgs`
- Custom `EventArgs`
- Lambda - Expression Lambda vs Statement Lambda
- Closure in Lambda
- Where are delegates used?

---

## 08 LINQ

- Query Syntax vs Method Syntax
- `Where()`, `Select()`, `SelectMany()`
- `OrderBy()`, `OrderByDescending()`, `ThenBy()`
- `GroupBy()`, `Join()`
- `Distinct()`, `Any()`, `All()`, `Count()`
- `First()` vs `FirstOrDefault()`
- `Single()` vs `SingleOrDefault()`
- `Last()` vs `LastOrDefault()`
- `Skip()` and `Take()` — pagination
- `Aggregate()`
- Deferred Execution vs Immediate Execution
- `IEnumerable<T>` vs `IQueryable<T>`
- `ToList()`, `ToArray()`

---

## 09 Async Programming

- Thread vs Task
- Thread vs Process
- `async` and `await`
- Thread Pool
- Parallel programming — `Parallel.For`
- `Task.WhenAll()` vs `Task.WhenAny()`
- `CancellationToken`
- `ConfigureAwait(false)`
- Deadlock — what causes it
- Lock — thread safety
- Race Condition vs Lock
- I/O-bound vs CPU-bound

---

## 10 Exception Handling

- `try`, `catch`, `finally`
- `throw` vs `throw ex`
- Custom Exception
- Inner Exception — root cause
- Exception Filter — `when` keyword
- Common exceptions — `NullReferenceException`, `ArgumentException`, `InvalidOperationException`, `FormatException`
