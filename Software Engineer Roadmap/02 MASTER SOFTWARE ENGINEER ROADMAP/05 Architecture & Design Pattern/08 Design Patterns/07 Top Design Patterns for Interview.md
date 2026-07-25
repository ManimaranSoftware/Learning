### Why These 6 Patterns

- Most frequently asked in .NET backend interviews.
- Used in real-world ASP.NET Core projects daily.
- Cover all three GoF categories + architectural.
- Understanding these deeply is better than memorizing all 23.

---

## 1. Singleton Pattern (Creational)

---

### What

- Singleton - Ensures only one instance of a class exists throughout the application.
- Provides a global access point to that instance.

---

### When to Use

- Logging service. - one instance can handle multiple request at the same time stamp - singleton for logging because no user specific data - if we use other lot of creation and dispose
- Configuration manager.
- Database connection pool. - if we use using - no need of conn.close - reusing the connections
- Caching service. - in memory cache (single server - not shared)- distributed cache( shared across applications)
---
### Why do we need it?

- Prevents multiple instances of the same class.
- Ensures a single shared object throughout the application.
- Reduces unnecessary object creation.
- Provides a centralized point of access.
---

### C# Implementation

```csharp
public sealed class Logger
{
    private static readonly Lazy<Logger> _instance = 
        new Lazy<Logger>(() => new Logger());

    private Logger() { }

    public static Logger Instance => _instance.Value;

    public void Log(string message) => Console.WriteLine(message);
}
```

---

### In ASP.NET Core (DI Way)

```csharp
builder.Services.AddSingleton<ILogger, Logger>();
```

- DI container manages the single instance.
- Preferred over manual Singleton in modern .NET.

---

### Thread Safety

- `Lazy<T>` ensures thread-safe initialization.
- Avoid `static` fields without proper locking.

---

### Interview Points

- Difference between Singleton and Static class.
- Static class - Cannot implement interfaces, no DI support, no inheritance.
- Singleton - Can implement interfaces, supports DI, lazy initialization.
- When NOT to use - When state changes frequently or in multi-tenant apps.

---

## 2. Factory Pattern (Creational)

---

### What

- Factory - Creates objects without exposing creation logic to the client.
- Client uses an interface, factory decides which concrete class to instantiate.

---
### Why
- Hides object creation logic.
- Reduces tight coupling between client and concrete classes. 
- Makes the code easier to extend and test.
---
### When to Use

- Object creation depends on runtime conditions.
- Multiple implementations of an interface.
- Decoupling object creation from business logic.

---

### C# Implementation

```csharp
public interface INotification
{
    void Send(string message);
}

public class EmailNotification : INotification
{
    public void Send(string message) => Console.WriteLine($"Email: {message}");
}

public class SmsNotification : INotification
{
    public void Send(string message) => Console.WriteLine($"SMS: {message}");
}

public class NotificationFactory
{
    public INotification Create(string type) => type switch
    {
        "email" => new EmailNotification(),
        "sms" => new SmsNotification(),
        _ => throw new ArgumentException("Invalid type")
    };
}
```

---

### Abstract Factory

- Factory of factories.
- Creates families of related objects.
- Example - `IDatabaseFactory` creating `IConnection`, `ICommand`, `IReader` for SQL Server or PostgreSQL.

---

### Interview Points

- Factory vs Abstract Factory - Factory creates one type, Abstract Factory creates a family.
- Factory vs `new` keyword - Factory provides loose coupling and testability.
- Real use case - Payment gateway selection, notification channels.

---

## 3. Strategy Pattern (Behavioral)

---

### What

- Strategy - Defines a family of algorithms, encapsulates each one, and makes them interchangeable.
- Client selects the algorithm at runtime.

---

### When to Use

- Multiple ways to perform an operation.
- Avoid long `if-else` or `switch` chains.
- Algorithm selection depends on user input or configuration.

---

### C# Implementation

```csharp
public interface IPricingStrategy
{
    decimal CalculatePrice(decimal basePrice);
}

public class RegularPricing : IPricingStrategy
{
    public decimal CalculatePrice(decimal basePrice) => basePrice;
}

public class PremiumPricing : IPricingStrategy
{
    public decimal CalculatePrice(decimal basePrice) => basePrice * 0.8m; // 20% discount
}

public class PricingStrategyFactory
{
    public static IPricingStrategy Create(string customerType)
    {
        return customerType switch
        {
            "Premium" => new PremiumPricing(),
            "Regular" => new RegularPricing(),
            _ => throw new ArgumentException("Invalid customer type")
        };
    }
}

public class OrderService
{
    private readonly IPricingStrategy _strategy;

    public OrderService(IPricingStrategy strategy)
    {
        _strategy = strategy;
    }

    public decimal GetTotal(decimal price)
    {
        return _strategy.CalculatePrice(price);
    }
}

public class Program
{
    public static void Main()
    {
        string customerType = "Premium";

        IPricingStrategy strategy = PricingStrategyFactory.Create(customerType);

        OrderService orderService = new OrderService(strategy);

        decimal total = orderService.GetTotal(1000);

        Console.WriteLine($"Final Price: {total}");
    }
}
```

---

### With DI in ASP.NET Core

```csharp
// Register based on config or condition
builder.Services.AddScoped<IPricingStrategy, PremiumPricing>();
```

---

### Interview Points

- Strategy vs Factory - Strategy changes behavior, Factory changes object creation.
- Follows OCP (Open/Closed Principle) - Add new strategies without modifying existing code.
- Real use case - Sorting algorithms, discount calculation, authentication methods.

---

## 4. Observer Pattern (Behavioral)

---

### What

- Observer - One-to-many dependency. When one object changes state, all dependents are notified.
- Publisher/Subscriber model.

---

### When to Use

- Event-driven systems.
- Notifications.
- UI updates on data change.
- Decoupling event producers from consumers.

---

### C# Built-in Support

```csharp
public class OrderService
{
    public event EventHandler<Order> OrderPlaced;

    public void PlaceOrder(Order order)
    {
        // process order
        OrderPlaced?.Invoke(this, order);
    }
}

public class EmailService
{
    public void OnOrderPlaced(object sender, Order order)
    {
        Console.WriteLine($"Email sent for order {order.Id}");
    }
}

// Usage
var orderService = new OrderService();
var emailService = new EmailService();
orderService.OrderPlaced += emailService.OnOrderPlaced;
```

---

### In ASP.NET Core (MediatR)

```csharp
public class OrderPlacedNotification : INotification
{
    public int OrderId { get; set; }
}

public class SendEmailHandler : INotificationHandler<OrderPlacedNotification>
{
    public Task Handle(OrderPlacedNotification notification, CancellationToken ct)
    {
        // send email
        return Task.CompletedTask;
    }
}
```

---

### Interview Points

- Observer vs Event - Same concept. C# `event` keyword is Observer pattern built-in.
- Observer vs Pub/Sub - Observer is direct coupling, Pub/Sub uses a message broker (decoupled).
- Real use case - SignalR notifications, domain events, logging triggers.

---

## 5. Decorator Pattern (Structural)

---

### What

- Decorator - Adds behavior to an object dynamically without modifying its class.
- Wraps the original object with additional functionality.

---

### When to Use

- Adding logging, caching, validation around existing behavior.
- Extending functionality without inheritance.
- Middleware-like wrapping.

---

### C# Implementation

```csharp
public interface IOrderRepository
{
    Order GetById(int id);
}

public class OrderRepository : IOrderRepository
{
    public Order GetById(int id) => // fetch from DB
}

public class CachedOrderRepository : IOrderRepository
{
    private readonly IOrderRepository _inner;
    private readonly IMemoryCache _cache;

    public CachedOrderRepository(IOrderRepository inner, IMemoryCache cache)
    {
        _inner = inner;
        _cache = cache;
    }

    public Order GetById(int id)
    {
        return _cache.GetOrCreate($"order_{id}", entry =>
        {
            entry.AbsoluteExpirationRelativeToNow = TimeSpan.FromMinutes(5);
            return _inner.GetById(id);
        });
    }
}
```

---

### In ASP.NET Core

- HttpClient message handlers (DelegatingHandler) are decorators.
- Middleware pipeline is decorator-like.

```csharp
// DelegatingHandler example
public class LoggingHandler : DelegatingHandler
{
    protected override async Task<HttpResponseMessage> SendAsync(
        HttpRequestMessage request, CancellationToken ct)
    {
        Console.WriteLine($"Request: {request.RequestUri}");
        var response = await base.SendAsync(request, ct);
        Console.WriteLine($"Response: {response.StatusCode}");
        return response;
    }
}
```

---

### Interview Points

- Decorator vs Inheritance - Decorator is flexible at runtime, inheritance is fixed at compile time.
- Decorator vs Proxy - Decorator adds behavior, Proxy controls access.
- Real use case - Caching repositories, logging handlers, retry wrappers.

---

## 6. Repository Pattern (Architectural)

---

### What

- Repository - Abstracts data access logic behind an interface.
- Acts as an in-memory collection of domain objects.

---

### When to Use

- Decoupling business logic from data access.
- Making data access testable (mock the repository).
- Centralizing query logic.

---

### C# Implementation

```csharp
public interface IRepository<T> where T : class
{
    Task<T> GetByIdAsync(int id);
    Task<IEnumerable<T>> GetAllAsync();
    Task AddAsync(T entity);
    void Update(T entity);
    void Delete(T entity);
}

public class Repository<T> : IRepository<T> where T : class
{
    private readonly DbContext _context;
    private readonly DbSet<T> _dbSet;

    public Repository(DbContext context)
    {
        _context = context;
        _dbSet = context.Set<T>();
    }

    public async Task<T> GetByIdAsync(int id) => await _dbSet.FindAsync(id);
    public async Task<IEnumerable<T>> GetAllAsync() => await _dbSet.ToListAsync();
    public async Task AddAsync(T entity) => await _dbSet.AddAsync(entity);
    public void Update(T entity) => _dbSet.Update(entity);
    public void Delete(T entity) => _dbSet.Remove(entity);
}
```

---

### Unit of Work

- Unit of Work - Coordinates multiple repositories under a single transaction.
- Calls `SaveChanges()` once for all operations.

```csharp
public interface IUnitOfWork : IDisposable
{
    IRepository<Order> Orders { get; }
    IRepository<Product> Products { get; }
    Task<int> SaveChangesAsync();
}
```

---

### Interview Points

- Repository vs DbContext directly - Repository adds abstraction, testability, and query centralization.
- Controversy - Some argue EF Core's DbSet is already a repository. Valid point, but repository still helps with testing and domain logic separation.
- Generic vs Specific - Generic repository for CRUD, specific repositories for complex queries.
- Real use case - Any layered or clean architecture project.

---

## Quick Comparison Table

| Pattern    | Category      | Problem it Solves        |
| ---------- | ------------- | ------------------------ |
| Singleton  | Creational    | Single shared instance   |
| Factory    | Creational    | Flexible object creation |
| Strategy   | Behavioral    | Swappable algorithms     |
| Observer   | Behavioral    | Event notification       |
| Decorator  | Structural    | Add behavior dynamically |
| Repository | Architectural | Abstract data access     |

---

### Study Tips

- Understand the "why" before the "how".
- Be ready to draw class diagrams in interviews.
- Know at least one real-world .NET example for each.
- Understand how DI container replaces manual pattern implementation.
- Practice explaining in 2-3 sentences (elevator pitch).
