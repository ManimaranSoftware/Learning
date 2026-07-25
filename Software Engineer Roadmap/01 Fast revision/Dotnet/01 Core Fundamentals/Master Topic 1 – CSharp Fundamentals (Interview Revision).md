
## Runtime
- CLR → Executes managed code, GC, JIT, Exception Handling
- CTS → Common Type System (Common Data Types)
- CLS → Rules for .NET language interoperability
- Managed Code → Runs under CLR
- Unmanaged Code → Runs directly on OS

> [!tip]
> **Memory Tip:** CLR = Heart of .NET

---

## Memory Management
- Stack → Mostly Value Types, Local Variables, Method Calls, LIFO, Fast
- Heap → Mostly Reference Types, Objects, GC Managed
- Value Type → Own Copy, Usually Stack
- Reference Type → Reference in Stack, Object in Heap
- Boxing → Value → Object (Heap)
- Unboxing → Object → Value
- GC → Cleans Heap (Gen0 → Gen1 → Gen2)
- `IDisposable` → Manual cleanup for unmanaged resources
- `using` → Automatically calls `Dispose()`

> [!tip]
> **Memory Tip:** Stack = Plates | Heap = Warehouse

---

## OOP
- Class → Blueprint
- Object → Instance
- Encapsulation → Data Hiding
- Inheritance → Code Reuse
- Polymorphism → One Interface, Many Forms
- Abstraction → Hide Complexity
- Interface → Contract (Multiple Inheritance)
- Abstract Class → Partial Implementation

> [!tip]
> **Memory Tip:** Interface = Rules | Abstract = Half-built House

---

## Language Features
- `var` → Compile-time Type
- `dynamic` → Runtime Type
- `object` → Base Type of all .NET Types
- `const` → Compile-time Constant - public const double Pi = 3.14159;
- `readonly` → Runtime Constant - public readonly DateTime LaunchTime; later assinged in constructor - LaunchTime = DateTime.Now;
- `static` → Shared by all Objects (example count)
- `sealed` → Cannot Inherit
- `partial` → Split Class into Multiple Files
- `ref` → Pass & Modify (Must Initialize)
- `out` → Output Parameter (No Initialization Needed)
- `in` → Read-only Reference
- `params` → Variable Number of Arguments

---

## Collections
- Array → Fixed Size
- `List<T>` → Dynamic Size
- `Dictionary<TKey, TValue>` → Key-Value, O(1) Lookup
- `HashSet<T>` → Unique Values
- `Queue<T>` → FIFO
- `Stack<T>` → LIFO
- `LinkedList<T>` → Fast Insert/Delete

> [!tip]
> **Memory Tip:** Dictionary = Fast Search | HashSet = Unique | List = Dynamic

---

## Generics
- Type Safe
- Reusable Code
- Better Performance (No Boxing)

---

## Delegates & Events
- Delegate → Function Pointer. rules - method signature should be same, no of param.
- `Action` → No Return
- `Func<T>` → Returns Value
- `Predicate<T>` → Returns `bool`
- Event → Publisher → Subscriber

---

## LINQ
- `Where()` → Filter
- `Select()` → Projection
- `OrderBy()` → Sorting
- `GroupBy()` → Grouping
- `Join()` → Combine Tables
- `Any()` → Exists?
- `FirstOrDefault()` → Safe Fetch
- `SingleOrDefault()` → Expect One Record
- `Skip()` / `Take()` → Pagination
- `IEnumerable<T>` → In-Memory
- `IQueryable<T>` → Database Query

> [!tip]
> **Memory Tip:** `IQueryable` = SQL | `IEnumerable` = RAM

---

## Exception Handling
- `try-catch-finally`
- `throw` → Preserves Stack Trace
- `throw ex` → Resets Stack Trace
- Custom Exception
- Inner Exception → Root Cause

---

## Async Programming
- Thread ≠ Task
- `async` / `await` → Non-Blocking
- `Task.WhenAll()` → Parallel Execution
- `Task.WhenAny()` → First Completed
- `CancellationToken` → Cancel Operation
- I/O Bound → `async` / `await`
- CPU Bound → `Task.Run()`

> [!tip]
> **Memory Tip:** Async = Don't Wait, Continue Working

---

## Strings
- `String` → Immutable
- `StringBuilder` → Mutable
- `==` / `.Equals()` → Value Comparison
- `ReferenceEquals()` → Memory Reference
- `IsNullOrEmpty()` vs `IsNullOrWhiteSpace()`

---

## Interview Traps
- Stack vs Heap
- Value Type vs Reference Type
- Interface vs Abstract Class
- `var` vs `dynamic` vs `object`
- `ref` vs `out` vs `in`
- `String` vs `StringBuilder`
- `throw` vs `throw ex`
- `IEnumerable<T>` vs `IQueryable<T>`
- Task vs Thread
- `Action` vs `Func<T>` vs `Predicate<T>`
- Boxing vs Unboxing

---

## 30-Second Revision Formula

Runtime → Memory → OOP → Language → Collections → Generics → Delegates → LINQ → Exception → Async → Strings → Interview Traps