11 Advanced C#  
│  
├── Extension Methods   
├── Anonymous Types   
├── Reflection   
├── Attributes   
├── Serialization   
├── File Handling   
├── Tuples   
├── Pattern Matching   
├── Records (Advanced)   
├── Expression Trees   
├── Span`<T>` & Memory`<T>`   
└── Nullable Reference Types 
# Extension Methods

- Extension Method - Adds new methods to existing types without modifying source code.
- Defined as - Static method inside a static class.
- First Parameter - Uses `this` keyword to specify the extended type.
- Benefits - Improves readability, Reusability and Maintainability.
- Common Usage - LINQ extension methods (`Where()`, `Select()`, `OrderBy()`).

**Imagine buying a Toyota car.** It already comes with **Steering, Brake, and Accelerator**. These are **Built-in Methods** because they are created by the manufacturer (original class).

Later, you install a **Dash Camera** and **Mobile Holder** without changing the car. These are **Extension Methods** because they add new functionality without modifying the original class.

**Memory Trick:**

> **Built-in = Born with the class**  
> **Extension = Added later without modifying the class**

Difference between Built-in Method vs Extension method
##### C# Example

**Built-in Method**

```
name.ToUpper();
```

`ToUpper()` is inside the `String` class.

---

**Extension Method**

```
name.ReverseText();
```

`ReverseText()` is in another static class.

Compiler changes it to:

```
StringExtensions.ReverseText(name);
```
---

# Anonymous Types 

- Anonymous Type - Object without explicitly defining a class.
- Created using - `new { }`
- Properties - Read-only after creation.
- Scope - Limited to the current method.
- Common Usage - LINQ projections.

##### Definition

- **Anonymous Type** - An object created **without defining a class**.
- The compiler automatically creates the class behind the scenes.

---

##### Normal Way

First create a class:

```
public class Employee
{    
public string Name { get; set; }    
public int Age { get; set; }
}

Employee emp = new Employee
{
	Name = "Mani",
	Age = 25
};
```

---

##### Anonymous Type

No class required.

```
var emp = new
{
    Name = "Mani",
    Age = 25
};
```

The compiler creates a hidden class for you.

---

##### Why use Anonymous Types?

- Temporary objects.
- LINQ queries.
- Returning selected data.
- Avoid creating small classes.

---

##### Common Example (LINQ)

```
var employees = db.Employees    
		.Select(e => new
		{
		        e.Name,
		        e.Department
	    });
```

Instead of returning the entire `Employee` object, it returns only:

- Name
- Department

---

##### Limitations

- No class name.
- Cannot be used as a method return type.
- Mostly used within a local scope.
---

# Reflection 

- Reflection - Inspects assemblies, types, methods and properties at runtime.
- Namespace - `System.Reflection`
- Common Usage - Dependency Injection, ORM, Unit Testing, Plugins.
- Drawback - Slower than direct access.

##### Reflection Examples
##### 1. Dependency Injection (ASP.NET Core)

- DI container uses Reflection to discover constructors.
- Automatically creates objects and injects dependencies.

```
services.AddScoped<IEmployeeService, EmployeeService>();
```

---

##### 2. Entity Framework Core

- Uses Reflection to discover entity classes and properties.
- Automatically maps classes to database tables.

```
public class Employee
{    
public int Id { get; set; } 
public string Name { get; set; }
}
```

---

##### 3. JSON Serialization

- Uses Reflection to read object properties.
- Converts objects to and from JSON.

```
JsonSerializer.Serialize(employee);
```
---
##### 4. Swagger / OpenAPI

- Uses Reflection to scan Controllers and API actions.
- Automatically generates API documentation.

---

##### 5. Manual Reflection

- Allows inspection of types, methods and properties at runtime.

```
Type type = typeof(Employee);
Console.WriteLine(type.Name);
foreach (var method in type.GetMethods())
{    
Console.WriteLine(method.Name);
}
```
---

# Attributes

##### Overview

- Attribute adds metadata to assemblies, classes, methods, properties, or parameters.
- Provides additional information that can be read at runtime using Reflection.
- Does not change the program logic directly.
- Syntax: `[AttributeName]`
-  Syntax - `[AttributeName]`
- Custom Attribute - Created by inheriting from `Attribute`.
- Common Attributes - `[Obsolete]`, `[Serializable]`, `[Required]`, `[Authorize]`.

##### Why?

Before Attributes, developers had no standard way to attach extra information to code.

Attributes allow frameworks and tools to understand how a class or method should behave without changing its implementation.

##### Common Attributes

- `[Obsolete]` – Marks code as deprecated.
- `[Serializable]` – Indicates an object can be serialized.
- `[Required]` – Validates mandatory fields.
- `[Authorize]` – Restricts access to authenticated/authorized users.
- `[HttpGet]`, `[HttpPost]` – Defines HTTP endpoints in ASP.NET Core.

##### Custom Attribute

- Created by inheriting from the `Attribute` class.

```
public class DeveloperAttribute : Attribute{}
```

Usage:

```
[Developer]public class Employee{}
```

##### Uses

- Validation
- Authentication & Authorization
- Serialization
- Unit Testing
- Entity Framework
- ASP.NET Core Routing
- Logging

##### Benefits

- Separates metadata from business logic.
- Makes code cleaner and easier to maintain.
- Enables frameworks to add behavior using Reflection.
- Reduces hard-coded configuration.

##### Easy Story 

Imagine a file in an office.

You attach sticky notes saying:

- **Urgent**
- **Confidential**
- **Approved**

The file itself doesn't change, but people know how to handle it by reading the sticky notes.

Attributes work the same way—they add information to code without changing the code itself.

##### Memory Trick 

> **Attribute = Sticky Note attached to code.**

##### Interview

> An Attribute is metadata attached to code elements such as classes, methods, or properties. It provides additional information that frameworks and tools can read using Reflection to apply behaviors like validation, routing, serialization, and authorization.

---

# Serialization

- Serialization - Converts an object into JSON, XML or byte stream.
- Deserialization - Converts JSON, XML or byte stream back to an object.
- Common Library - `System.Text.Json`
- Common Usage - APIs, File Storage, Caching.


##### Definition

- **Serialization** - Process of converting an object into a transferable or storable format (JSON, XML, Binary).

---

##### Why Serialization?

- Send data over a network.
- Store data in a file.
- Save data in a cache.
- Exchange data between applications.

---

##### Example

##### Object

```
Employee emp = new Employee
{    
Name = "Mani",    
Age = 25
};
```

##### Serialize to JSON

```
string json = JsonSerializer.Serialize(emp);
```

Output:

```
{  
"Name": "Mani",
"Age": 25
}
```

---

##### Deserialization

##### Definition

- **Deserialization** - Process of converting serialized data back into an object.

```
Employee emp = JsonSerializer.Deserialize<Employee>(json);
```

##### Common Formats

- JSON  (Most Common)
- XML
- Binary (Less common today)

---

##### Common Uses

- REST APIs
- ASP.NET Core Web APIs
- Redis Cache
- File Storage
- Message Queues (RabbitMQ, Kafka)
- API Communication
---

# File Handling

- File - Static class for file operations.
- FileInfo - Instance-based file operations.
- Directory - Static class for directory operations.
- DirectoryInfo - Instance-based directory operations.
- StreamReader - Reads text files.
- StreamWriter - Writes text files.

**What is File Handling?**

> File Handling is the process of creating, reading, writing, updating and deleting files using classes like `File`, `FileInfo`, `StreamReader` and `StreamWriter`.

---

##### Memory Trick

> **CRUD for Files**

- **C** → Create
- **R** → Read
- **U** → Update (Write/Append)
- **D** → Delete
##### Common Operations

##### Read File

```
string text = File.ReadAllText("data.txt");
```

---

##### Write File

```
File.WriteAllText("data.txt", "Hello World");
```

---

##### Append File

```
File.AppendAllText("data.txt", "New Line");
```

---

##### Check File Exists

```
bool exists = File.Exists("data.txt");
```

---

##### Delete File

```
File.Delete("data.txt");
```

---

##### Common Uses

- Reading configuration files.
- Writing logs.
- Importing/Exporting CSV files.
- Reading JSON/XML files.
- Report generation.
- File uploads/downloads.
---

# Tuples 

- Tuple - Groups multiple values without creating a class.
- ValueTuple - Lightweight tuple introduced in C# 7.
- Named Tuple - Supports meaningful element names.
- Common Usage - Returning multiple values from methods.
##### Definition

- **Tuple** - Lightweight data structure used to store multiple values in a single object.
- Does **not** require creating a class.

---

##### Example

```
(string Name, int Age) employee = ("Mani", 25);
Console.WriteLine(employee.Name);
Console.WriteLine(employee.Age);
```

---

##### Returning Multiple Values

```
public (int Sum, int Product) Calculate(int a, int b)
{
    return (a + b, a * b);
}
var result = Calculate(5, 10);
Console.WriteLine(result.Sum);
Console.WriteLine(result.Product);
```

---

##### Why Use Tuples?

- Return multiple values from a method.
- Temporary grouping of related data.
- Avoid creating a small class.

---

##### Tuple vs Anonymous Type

|Tuple|Anonymous Type|
|---|---|
|Can be returned from methods|Mostly used within local scope|
|Named or unnamed values|Compiler-generated properties|
|Lightweight data container|Temporary object|

---

##### Common Uses

- Returning multiple values.
- LINQ queries.
- Temporary data grouping.
- Method results.

---
**What is a Tuple?**

> A Tuple is a lightweight data structure that groups multiple values into a single object without creating a separate class. It is commonly used to return multiple values from a method.

---

#### Memory Trick 

> **Class = Permanent structure**   
> **Tuple = Temporary bundle of values** 

---

# Pattern Matching 

- Pattern Matching - Simplifies conditional logic based on type or value.
- Type Pattern - Checks object type using `is`.
- Switch Pattern - Uses `switch` with patterns.
- Property Pattern - Matches object properties.
- Relational Pattern - Uses `<`, `>`, `<=`, `>=`.

##### Pattern Matching

- Simplifies conditional logic based on an object's **type, value, or properties**.
- Reduces explicit casting and improves readability.

---

##### Type Pattern

- Checks an object's type using `is`.

```
object obj = "Hello";  
  
if (obj is string text)  
{  
Console.WriteLine(text.Length);  
}
```

---

##### Switch Pattern

- Uses `switch` to match different types or values.

```
object value = 10;  
  
switch (value)  
{  
case int i:  
Console.WriteLine("Integer");  
break;  
  
case string s:  
Console.WriteLine("String");  
break;  
}
```

---
### `switch` Expression

```
string result = value switch  
{  
int => "Integer",  
string => "String",  
_ => "Unknown"  
};
```

---

##### Property Pattern

- Matches object properties.

```
person is { Age: >= 18 }
```

---

##### Relational Pattern

- Matches values using `<`, `>`, `<=`, `>=`.

```
age is >= 18
```

---

##### Benefits

- Cleaner code.
- Eliminates explicit casting.
- More readable than nested `if-else`.
- Safer type checking.

---

##### Memory Trick 

> **Pattern Matching = Match an object's Type, Value, or Properties.**

**Not Regex!**

- **C# Pattern Matching** → Objects (`is`, `switch`, properties)
- **Regex Pattern Matching** → Text (`Regex.IsMatch()`)

---

##### Interview Answer

**Q: What is Pattern Matching in C#?**

> Pattern Matching is a C# feature that simplifies conditional logic by matching an object's **type, value, or properties**, making the code more readable and reducing explicit casting.

---

# Records (Advanced) 

- Record - Reference type with value-based equality.
- Immutable by default.
- Supports `with` expression for cloning.
- Primary Constructor - Declared directly in record definition.
- Common Usage - DTOs, API Models, Immutable Objects.
##### Record

- **Record** - Reference type designed to store immutable data.
- Automatically provides value-based equality.

---

##### Normal Class (Reference Equality)

```
public class Employee{    public string Name { get; set; }    public int Age { get; set; }}var e1 = new Employee { Name = "Mani", Age = 25 };var e2 = new Employee { Name = "Mani", Age = 25 };Console.WriteLine(e1 == e2);   // False
```

➡️ Different objects in memory, so they are **not equal**.

---

##### Record (Value Equality)

```
public record Employee(string Name, int Age);var e1 = new Employee("Mani", 25);var e2 = new Employee("Mani", 25);Console.WriteLine(e1 == e2);   // True
```

➡️ Same values, so they are **equal**.

---

##### Memory Trick 

- **Class** → Compares **Reference (Memory Address)**.
- **Record** → Compares **Values (Data)**.

Class = Same Object?
Record = Same Data?

---

##### Immutability

Properties are immutable by default.

```
public record Employee(string Name, int Age);

var emp = new Employee("Mani", 25);  // emp.Name = "John"; ❌
```

---

##### Value-Based Equality

Two records with the same values are considered equal.

```
var e1 = new Employee("Mani", 25);
var e2 = new Employee("Mani", 25);
Console.WriteLine(e1 == e2);   // True
```

---

##### `with` Expression

Creates a copy with modified values.

```
var e2 = e1 with { Age = 26 };
```

---

##### Common Uses

- DTOs (Data Transfer Objects)
- API Request/Response Models
- Immutable objects
- Configuration objects

---

##### Class vs Record

|Class|Record|
|---|---|
|Reference equality|Value equality|
|Mutable by default|Immutable by default|
|Business objects|DTOs / Data models|

---

##### Benefits

- Less boilerplate code.
- Immutable by default.
- Value-based equality.
- Easy object copying using `with`.

---

##### Memory Trick 

> **Record = Immutable data + Value equality.**

Use a **Record** when you want to represent **data**.

Use a **Class** when you want to represent **behavior and business logic**.

---

##### Interview Answer

**Q: What is a Record in C#?**

> A Record is a reference type introduced in C# 9 that is designed for immutable data. Unlike classes, records compare objects based on their values rather than their references and support easy copying using the `with` expression.

---

##### Easy Analogy 

Think of an **Aadhaar Card**.

- It represents **information** (Name, DOB, Address).
- If two Aadhaar cards have the **same details**, they represent the same data.
- You don't usually modify an Aadhaar card—you issue a **new one** if details change.

A **Record** is like that: it's meant to hold **data**, not behavior.

##### Performance

- **Class** → Slightly faster 
- **Record** → Slightly slower (because it compares values)

The difference is **very small**. In real applications, you almost never choose based on performance.

---

##### When to use Class 

Use a **Class** when your object has:

- Business logic
- Mutable state
- Methods
- Behavior

Example:

```
EmployeeOrderBankAccountShoppingCart
```

These objects **do things**, not just hold data.

---

##### When to use Record 

Use a **Record** when your object is just **data**.

Example:

```
EmployeeDtoLoginRequestLoginResponseUserResponseConfiguration
```

These objects only **carry information**.

---

##### Real project example

##### Entity → Class 

```
public class Employee{    public int Id { get; set; }    public string Name { get; set; }    public void Promote()    {        ...    }}
```

Has behavior.

---

##### DTO → Record 

```
public record EmployeeDto(    int Id,    string Name);
```

Only transfers data.

---

##### Memory Trick 

> **Class = Behavior**
> 
> **Record = Data**

Don't think:

- "Which is faster?"

Think:

- "Is this object **doing work** or **carrying data**?"

That's how senior developers choose.

---

##### Interview Answer 

**When would you use a Record instead of a Class?**

> I use a **Record** for immutable data models like DTOs, API requests/responses, and configuration objects because it provides value-based equality with less boilerplate. I use a **Class** for domain models and business entities that contain behavior, mutable state, or business logic.

---

# Expression Trees 

- Expression Tree - Represents code as a data structure.
- Namespace - `System.Linq.Expressions`
- Used by - Entity Framework, LINQ Providers.
- Enables dynamic query generation.

##### Expression Tree

- **Expression Tree** - Represents code as a **data structure (tree)** instead of executing it immediately.
- Namespace: `System.Linq.Expressions`

---

##### Normal Lambda

The lambda executes immediately.

```
Func<int, bool> isAdult = age => age >= 18;
```

Calling:

```
isAdult(20);
```

returns `true`.

---

##### Expression Tree

The lambda is stored as a tree.

```
Expression<Func<int, bool>> isAdult = age => age >= 18;
```

It is **not executed**.

Instead, C# stores:

```
age >= 18
```

as a tree structure.

---

##### Why use Expression Trees?

- LINQ Providers
- Entity Framework Core
- Dynamic Query Generation
- ORM Frameworks

---

##### Example (Entity Framework)

```
context.Employees       .Where(e => e.Age >= 18);
```

EF Core receives the Expression Tree and converts it into SQL:

```
SELECT *FROM EmployeesWHERE Age >= 18
```

---

### Func vs Expression

|Func|Expression|
|---|---|
|Executes code|Stores code as a tree|
|Returns result|Can be analyzed or converted|
|Used in memory|Used by LINQ providers like EF Core|

---

##### Benefits

- Dynamic query generation.
- SQL translation.
- Runtime code analysis.
- Flexible LINQ providers.

---

##### Real-Life Example 

Imagine writing:

> **Age >= 18**

### Func

A person immediately checks the age and says:

> "True"

The instruction is executed.

---

### Expression Tree

Instead of executing, someone **writes the instruction on paper**.

```
Age >= 18
```

Now another person (EF Core) reads that instruction and translates it into SQL.

---

## Memory Trick 

> **Func = Execute the code.**
> 
> **Expression = Store the code.**

---

## Interview Answer

**Q: What is an Expression Tree?**

> An Expression Tree represents code as a tree structure instead of executing it immediately. It is mainly used by Entity Framework Core and LINQ providers to analyze expressions and translate them into SQL or other query languages.

---

### Why Microsoft introduced Expression Trees

Normal C# code executes **inside .NET**.

But frameworks like **Entity Framework** need to know **what you wrote**, not just the result.

They can't convert a `Func` into SQL because it has already been compiled and executed.

An **Expression Tree** preserves the code structure, allowing frameworks to inspect it and generate SQL dynamically.

That's why you'll commonly see:

- `Func<T, bool>` → In-memory filtering (`List<T>`)
- `Expression<Func<T, bool>>` → Database queries (`IQueryable<T>`, EF Core)
---
# `Span<T>` 

##### `Span<T>`

- Represents a contiguous region of memory.
- Stack-only type (`ref struct`).
- Provides fast access to arrays, strings, and buffers.
- Avoids unnecessary memory allocations and copying.
- Cannot be stored on the heap or used with `async`/`await`.

##### Why `Span<T>`?

- Improves performance.
- Avoids copying large data.
- Reduces memory allocations.
- Used for short-lived, synchronous operations.

##### Common Uses

- String processing.
- File processing.
- Buffer manipulation.
- Parsing data.

##### Benefits

- Faster execution.
- Less memory usage.
- Allocation-free operations.

##### Easy Story 

Imagine you need to read **10 pages** from a 1000-page book.

**Without `Span<T>`**

> You **photocopy** those 10 pages and then read them.

**With `Span<T>`**

> You simply place a **bookmark** on those pages and read them directly.

 No photocopy.  
 No extra memory.  
 Just a view into existing memory.

##### Memory Trick 

> **`Span<T>` = View into existing memory (No Copy).**

##### Interview Answer

> `Span<T>` is a stack-only type that provides fast, allocation-free access to contiguous memory. It improves performance by avoiding unnecessary memory allocations and copying.

---

# `Memory<T>` 

##### `Memory<T>`

- Heap-based equivalent of `Span<T>`.
- Represents a contiguous region of memory.
- Can be stored in fields and passed between methods.
- Supports asynchronous programming (`async`/`await`).

##### Why `Memory<T>`?

- `Span<T>` cannot survive across `async`/`await`.
- `Memory<T>` allows memory to live longer than a single synchronous method.
- Used when data needs to be accessed after an asynchronous operation.

##### Common Uses

- Asynchronous file processing.
- Network programming.
- Pipelines.
- Stream processing.
- High-performance applications.

##### Benefits

- Supports `async`/`await`.
- Can be stored on the heap.
- Efficient memory handling.
- Reduces unnecessary data copying.

##### Easy Story 

Imagine your friend gives you a book.

**`Span<T>`**

> Read it **now** and return it immediately.

**`Memory<T>`**

> Keep the book with you, pause, and continue reading later.

`Memory<T>` exists because the data needs to survive while your program is waiting (for example, during `await`).

##### Memory Trick 

> **`Memory<T>` = `Span<T>` that can survive `async`/`await`.**

##### Interview Answer

> `Memory<T>` is the heap-based equivalent of `Span<T>`. It was introduced because `Span<T>` cannot be used across `async`/`await`. `Memory<T>` provides efficient access to memory in asynchronous and long-lived scenarios.

---

##### Quick Revision 

|`Span<T>`|`Memory<T>`|
|---|---|
|Stack|Heap|
|Synchronous|Asynchronous|
|Cannot cross `async`/`await`|Can cross `async`/`await`|
|Immediate work|Long-lived work|
|View into existing memory|`Span<T>` that survives `async`/`await`|

##### One-line Memory Trick

> **`Span<T>` = Read now (Bookmark).**  
> **`Memory<T>` = Read later (Keep the book)**

---

# Nullable Reference Types 

##### Overview

- Helps prevent `NullReferenceException`.
- Introduced in C# 8.
- Enabled using `#nullable enable`.
- `string` → Non-nullable reference.
- `string?` → Nullable reference.
- Improves null safety during compile time.
- Distinguishes nullable and non-nullable reference types.

##### Why?

Before C# 8, reference types could always be `null`.

```
string name = null;
```

The compiler allowed it, which often caused `NullReferenceException` at runtime.

Nullable Reference Types were introduced to detect these issues during compilation.

##### Syntax

```
string name;
```

- Non-nullable reference type.
- Compiler expects it to always have a value.

```
string? name;
```

- Nullable reference type.
- Can contain `null`.

Enable the feature:

```
#nullable enable
```

##### Uses

- DTOs
- API Models
- Domain Models
- ASP.NET Core applications
- Large enterprise applications

##### Benefits

- Prevents `NullReferenceException`.
- Detects null issues during compile time.
- Improves code quality.
- Makes null handling explicit.

##### Easy Story 

Imagine a hotel.

Before C# 8:

> Every room **might** be empty.  
> You only discover it after opening the door.

After Nullable Reference Types:

Each room has a label.

- **Occupied** → `string`
- **May be Empty** → `string?`

Now you know before opening the door whether the room can be empty.

##### Memory Trick 

> **`string` = Never null**  
> **`string?` = May be null**

##### Interview

> Nullable Reference Types were introduced in C# 8 to reduce `NullReferenceException` by distinguishing nullable (`string?`) and non-nullable (`string`) reference types. The compiler provides warnings when nullable values are used without proper null checks.