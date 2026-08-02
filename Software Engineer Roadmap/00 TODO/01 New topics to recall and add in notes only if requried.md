# param vs args

// 'message' is a PARAMETER (the placeholder)
void ShowMessage(string message) 
{
    Console.WriteLine(message);
}

// "Hello World" is an ARGUMENT (the actual data passed)
ShowMessage("Hello World"); 

# Custom Exception in C# - Short Notes

**Definition**

- A custom exception is a user-defined exception.
- Used to represent business-specific errors.
- Inherit from the `Exception` class.

**Syntax**

```
public class InvalidAgeException : Exception
{
    public InvalidAgeException(string message)
        : base(message)
    {
    }
}
```

**Throw**

```
throw new InvalidAgeException("Age must be 18 or above.");
```

**Catch**

```
try
{
    throw new InvalidAgeException("Invalid age.");
}
catch (InvalidAgeException ex)
{
    Console.WriteLine(ex.Message);
}
```

### Interview Points

- ✅ Inherit from `Exception`.
- ✅ Pass the message to the base constructor (`base(message)`).
- ✅ Use custom exceptions for business rules, not system errors.
- ✅ Name exceptions with the **`Exception`** suffix (e.g., `OrderNotFoundException`).

### Real-world Examples

- `InsufficientBalanceException`
- `EmployeeNotFoundException`
- `InvalidOrderException`
- `ProductOutOfStockException`
- `DuplicateUserException`

# Steps to create custom middleware

### 1. Create a Middleware class

```
public class LoggingMiddleware
{
    private readonly RequestDelegate _next;

    public LoggingMiddleware(RequestDelegate next)
    {
        _next = next;
    }

    public async Task InvokeAsync(HttpContext context)
    {
        Console.WriteLine($"Request: {context.Request.Path}");

        await _next(context); // Pass request to next middleware

        Console.WriteLine($"Response: {context.Response.StatusCode}");
    }
}
```

---

### 2. Register it in `Program.cs`

```
app.UseMiddleware<LoggingMiddleware>();
```

---

### 3. Request Flow

```
Request
   ↓
LoggingMiddleware
   ↓
Authentication
   ↓
Authorization
   ↓
Controller
   ↓
Response
```

---

### Interview Points

- Middleware executes for every request.
- Must have `RequestDelegate` in the constructor.
- Main method is `InvokeAsync(HttpContext context)`.
- `await _next(context)` calls the next middleware.
- Code before `_next` runs before the controller.
- Code after `_next` runs after the controller (during response).

---

### Common uses

- Logging
- Exception handling
- Request/Response modification
- Authentication
- CORS
- Custom headers
- Performance monitoring

**One-line interview answer:**

> "A custom middleware is a class that intercepts HTTP requests and responses. It contains a constructor with `RequestDelegate` and an `InvokeAsync` method. It's registered using `app.UseMiddleware<T>()` and can execute logic before and after passing the request to the next middleware."


# IoC (Inversion of Control)
**IoC (Inversion of Control)** is a design principle where the framework controls the creation and management of objects instead of your code creating them.

### Without IoC

You create the dependency yourself.

```
public class OrderService
{
    private EmailService _emailService = new EmailService();
}
```

**Problem:** `OrderService` is tightly coupled to `EmailService`.

---

### With IoC (Dependency Injection)

The framework creates and injects the dependency.

```
public class OrderService
{
    private readonly IEmailService _emailService;

    public OrderService(IEmailService emailService)
    {
        _emailService = emailService;
    }
}
```

Register it in `Program.cs`:

```
builder.Services.AddScoped<IEmailService, EmailService>();
```

Now ASP.NET Core creates `EmailService` and injects it into `OrderService`.

---

### Benefits

- Loose coupling
- Easier unit testing (can inject mock objects)
- Better maintainability
- Easier to replace implementations

---

### IoC vs DI

- **IoC (Inversion of Control):** The design principle.
- **DI (Dependency Injection):** The technique used to achieve IoC.

---

### Interview answer (30 seconds)

> "Inversion of Control is a design principle where object creation and dependency management are handled by the IoC container instead of the class itself. In ASP.NET Core, this is implemented using Dependency Injection by registering services with methods like `AddScoped`, `AddSingleton`, or `AddTransient`, and the framework injects the required dependencies automatically."



# `IEnumerable` vs `IQueryable`

I never saw Ienumerable or Iqueryable keywords in my code base

That is completely normal! You do not see `IEnumerable` or `IQueryable` because they are hidden behind **`var`**, **LINQ extension methods**, or **Entity Framework models**. They are working under the hood right now.

Here is exactly where they are hiding in your codebase:

1. Hidden Behind `var`

When you write a LINQ query, the compiler automatically assigns the correct interface type behind the scenes.

csharp

```
// You write this:
var products = _context.Products.Where(p => p.IsActive);

// The compiler actually sees this (IQueryable):
IQueryable<Product> products = _context.Products.Where(p => p.IsActive);
```

Use code with caution.

2. Hidden Inside Collections (Lists and Arrays)

If your code uses standard collections, you are using `IEnumerable` without naming it. The [List Class](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1) and all arrays implicitly implement `IEnumerable`. [[1](https://www.jetbrains.com/help/resharper/PossibleMultipleEnumeration.html), [2](https://tutorials.eu/ienumerable-vs-list-in-c-the-differences/)]

csharp

```
// Both of these are secretly IEnumerables:
List<string> names = new List<string> { "Alice", "Bob" };
string[] array = { "C#", "Java" };

// This is why you can use 'foreach' on them!
foreach (var name in names) { ... }
```

Use code with caution.

3. Hidden Inside Entity Framework `DbSet`

If you look at your database context file, you will see `DbSet<T>`. The [DbSet Class](https://learn.microsoft.com/en-us/dotnet/api/microsoft.entityframeworkcore.dbset-1) inherits directly from `IQueryable`. [[1](https://code-maze.com/linq-resolving-call-is-ambiguous-error/)]

csharp

```
public class MyDbContext : DbContext
{
    // DbSet<Product> IS an IQueryable!
    public DbSet<Product> Products { get; set; } 
}
```

Use code with caution.

How to Spot Them Instantly

You can unhide them right now in your IDE (like Visual Studio or VS Code):

- **Hover your mouse** over the `var` keyword in any LINQ query. A tooltip will pop up showing whether it is actually an `IEnumerable` or an `IQueryable`.
- Look at any method that takes a list as a parameter or filters data. [[1](https://www.reddit.com/r/dotnet/comments/vjv48j/ienumerable_versus_list_what_is_main_reason_to/)]

Are you trying to **optimize a slow query**, or would you like to know how to use these interfaces to **write cleaner method signatures**?


# `yield return` Cheat Sheet

💡 What is it?

A keyword that creates **lazy-evaluated (on-demand)** collections. It pauses method execution and returns items **one by one** without creating a whole list in RAM. [[1](https://www.linkedin.com/pulse/how-use-yield-c-rest-apis-luis-gabriel-ahumada-oaode), [2](https://believemy.com/en/glossaries/python/yield), [3](https://medium.com/geekculture/understanding-the-power-of-yield-return-c3886668375d), [4](https://www.bigeye.com/glossary/yield), [5](https://www.c-sharpcorner.com/article/making-sense-of-yield-in-c-sharp/)]

⚙️ How it Works (Under the Hood)

- **Deferred Execution:** Code runs only when a loop (like `foreach`) requests the next item.
- **State Machine:** The compiler builds a hidden tracker to remember exactly where the method paused. [[1](https://www.geeksforgeeks.org/c-sharp/iterators-in-c-sharp/), [2](https://github.com/redux-saga/redux-saga/issues/306), [3](https://dev.to/onicolassb/do-you-really-know-what-yield-return-does-2oei)]

⚠️ Strict Rules

- **Return Types:** Must return `IEnumerable<T>`, `IEnumerable`, `IEnumerator<T>`, or `IEnumerator`.
- **Restrictions:** Cannot use `out` or `ref` parameters. Cannot be placed inside a standard `try-catch` block (only `try-finally`).
- **`yield break`:** Instantly exits the iteration loop early. [[1](https://dev.to/hootanht/the-double-edged-sword-of-ienumerable-and-yield-return-in-c-1j3c), [2](https://learn.microsoft.com/en-us/dotnet/visual-basic/language-reference/statements/yield-statement), [3](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/best-practices?view=aspnetcore-10.0), [4](https://blog.stackademic.com/what-really-happens-when-you-use-yield-in-c-d2e9c4a9cad0), [5](https://www.linkedin.com/posts/mwaseemzakir_have-you-heard-about-yield-keyword-yield-activity-7107242325281533952-od5b)]

---

💻 Code Example

csharp

```
// Consumer Loop
foreach (int num in GetNumbers()) {
    Console.Write(num + " "); // Output: 2 4 6
}

// Iterator Method
IEnumerable<int> GetNumbers() {
    yield return 2; // Pauses here, returns 2
    yield return 4; // Resumes, pauses here, returns 4
    yield return 6; // Resumes, pauses here, returns 6
}
```

Use code with caution.

---

🚀 Real-Time Use Cases

1. Streaming Massive Files (Log Parsers)

- **Keywords:** `StreamReader`, **O(1) Memory**, Crash Prevention.
- **Why:** Avoids loading a 10 GB file into RAM by processing it line-by-line.

csharp

```
IEnumerable<string> ReadErrors(string path) {
    using var reader = new StreamReader(path);
    while (reader.ReadLine() is string line)
        if (line.Contains("ERROR")) yield return line;
}
```

Use code with caution.

2. Paginated API Data (Batching)

- **Keywords:** Lazy Fetching, On-Demand Network Calls.
- **Why:** Fetches page 2 _only_ if the user scrolls down and requests more items.

csharp

```
IEnumerable<Item> StreamApi() {
    int page = 1;
    while (true) {
        var batch = FetchPage(page++);
        foreach (var item in batch) yield return item;
    }
}
```

Use code with caution.

3. Time-Slicing & Delays (Unity Coroutines)

- **Keywords:** Non-blocking, **Multi-frame execution**, UI Responsiveness.
- **Why:** Pauses tasks across frames so the application or game doesn't freeze.

csharp

```
IEnumerator FadeOut() {
    while (alpha > 0) {
        alpha -= 0.1f;
        yield return new WaitForSeconds(0.1f); // Pauses code, keeps UI responsive
    }
}
```

Use code with caution.

# char vs nchar
# decimal vs double

# anonymous type vs anonymous method

# Middleware vs filter

## Middleware (.NET Core)

### Definition

Middleware is a component in the **HTTP request pipeline** that processes **every incoming request** and **every outgoing response**.

### Key Points

- Runs **before MVC/Controller**.
- Executes for **all requests** (Controllers, Static Files, Minimal APIs, Health Checks, etc.).
- Can **modify**, **continue**, or **stop** the request.
- Configured in **Program.cs**.

### Common Uses

- Authentication
- Authorization
- Exception Handling
- Logging
- CORS
- HTTPS Redirection
- Static Files

### Interview One-liner

> Middleware is an HTTP pipeline component that executes for every request before it reaches the controller and is used for application-wide concerns.

---

## Filters (.NET Core)

### Definition

Filters execute **inside the MVC pipeline** around **controller actions**.

### Key Points

- Runs **after middleware**.
- Executes **only for MVC/API controller actions**.
- Can run **before and after** an action.
- Applied using **attributes** or registered globally.

### Types

- Authorization Filter
- Resource Filter
- Action Filter
- Exception Filter
- Result Filter

### Common Uses

- Action logging
- Model validation
- Custom authorization
- Exception handling (controller level)
- Modifying action results

### Interview One-liner

> Filters are MVC components that execute around controller actions for action-specific logic such as validation, authorization, and logging.

---

## Middleware vs Filter

| Middleware                 | Filter                       |
| -------------------------- | ---------------------------- |
| HTTP Pipeline              | MVC Pipeline                 |
| Runs first                 | Runs after middleware        |
| Every request              | Only controller actions      |
| Configured in `Program.cs` | Applied as attributes/global |
| App-wide logic             | Action-specific logic        |

---

## Execution Flow

```
Request
   ↓
Middleware
   ↓
Routing
   ↓
Filters
   ↓
Controller
   ↓
Filters
   ↓
Middleware
   ↓
Response
```

---

### Follow-up Interview Questions

### 1. Which runs first?

**Middleware.**

---

### 2. Can middleware stop a request?

**Yes.** It can return a response without calling `next()`.

---

### 3. Can filters stop execution?

**Yes.** Filters can short-circuit a controller action by setting a result.

---

### 4. Can middleware access controller/action details?

**No.** Middleware runs before the controller is selected (except endpoint metadata after routing).

---

### 5. Can filters run for static files?

**No.** They only execute for MVC/API controller actions.

---

### 6. Why not use middleware for everything?

Because middleware runs for **every request**, even images, CSS, JS, and health checks. If logic is only needed for controller actions, **filters are more appropriate**.

---

### 7. When do you choose Middleware?

Use middleware for **cross-cutting, application-wide concerns**:

- Logging
- Authentication
- CORS
- Exception handling
- HTTPS

---

### 8. When do you choose Filters?

Use filters for **controller/action-specific concerns**:

- Action logging
- Model validation
- Custom authorization
- Modifying action results

---

## 30-Second Interview Answer

> Middleware executes first in the HTTP request pipeline and processes every request. It's used for application-wide concerns like authentication, logging, CORS, and exception handling. If the request is routed to an MVC controller, the filter pipeline starts. Filters execute only around controller actions and are used for action-specific logic such as validation, authorization, and action logging.