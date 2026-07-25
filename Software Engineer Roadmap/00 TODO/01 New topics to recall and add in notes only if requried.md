# param vs args

// 'message' is a PARAMETER (the placeholder)
void ShowMessage(string message) 
{
    Console.WriteLine(message);
}

// "Hello World" is an ARGUMENT (the actual data passed)
ShowMessage("Hello World"); 

### Custom Exception in C# - Short Notes

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

### Steps to create custom middleware

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