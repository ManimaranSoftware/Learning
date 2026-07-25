# Quick Revision Topics — Master List

---

# 01 C# Fundamentals

---

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

- Delegate — what and why
- Single-cast vs Multicast delegate
- Anonymous Type vs Anonymous Method vs Lambda Expression
- `Action` vs `Func` vs `Predicate`
- Event — Publisher-Subscriber pattern
- Delegate vs Event
- `EventHandler` and `EventArgs`
- Custom `EventArgs`
- Lambda — Expression Lambda vs Statement Lambda
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

---

## 11 C# Advanced Concepts

- Pattern Matching — `is`, `switch`, type patterns, property patterns
- Tuples — `ValueTuple`, deconstruction
- `Span<T>` vs `Memory<T>` — high-performance memory
- `ref struct` — stack-only types
- Channels — producer/consumer pattern
- Source Generators — compile-time code generation
- `init` accessor — immutable after construction
- `required` keyword (C# 11)
- Raw string literals (`"""`)
- List patterns (C# 11)
- Global using directives
- File-scoped namespaces
- `IAsyncEnumerable<T>` — async streams

---
---

# 02 .NET Core

---

## 01 .NET Platform

- .NET Framework vs .NET Core vs .NET 5+
- CLR — Common Language Runtime
- BCL — Base Class Library
- JIT Compilation vs AOT Compilation
- Managed code vs Unmanaged code
- Assembly — DLL vs EXE
- GAC — Global Assembly Cache
- .NET SDK vs .NET Runtime
- `dotnet` CLI — build, run, publish, restore
- Target frameworks — `netstandard`, `net6.0`, `net8.0`
- Cross-platform support
- Minimal APIs vs Controller-based APIs

---

## 02 ASP.NET Core Basics

- ASP.NET Core vs ASP.NET Framework
- `Program.cs` — minimal hosting model
- `WebApplication` vs `WebApplicationBuilder`
- `Startup.cs` — `ConfigureServices` vs `Configure` (older versions)
- Kestrel vs IIS
- Host — Generic Host vs Web Host
- Environment — `Development`, `Staging`, `Production`
- `launchSettings.json`
- `appsettings.json` vs `appsettings.{Environment}.json`

---

## 03 Request Pipeline & Middleware

- What is middleware?
- Request pipeline — order matters
- `app.Use()` vs `app.UseWhen()` vs `app.Map()`
- `app.Run()` — terminal middleware
- Custom middleware class vs inline middleware
- Built-in middleware — `UseRouting`, `UseAuthentication`, `UseAuthorization`, `UseCors`, `UseStaticFiles`
- Short-circuiting the pipeline
- Exception handling middleware — `UseExceptionHandler`
- `HttpContext` — Request, Response, Items

---

## 04 Dependency Injection

- What is DI? Why use it?
- IoC Container — built-in DI in ASP.NET Core
- `AddTransient` vs `AddScoped` vs `AddSingleton`
- Constructor Injection vs Method Injection
- `IServiceProvider` — service locator (anti-pattern)
- Registering multiple implementations
- `IOptions<T>` vs `IOptionsSnapshot<T>` vs `IOptionsMonitor<T>`
- Keyed services (.NET 8)
- Captive dependency problem
- Lifetime mismatch — Scoped inside Singleton

---

## 05 MVC & Request Handling

- MVC pattern — Model, View, Controller
- Routing — Conventional vs Attribute routing
- Route constraints — `{id:int}`, `{name:alpha}`
- Model Binding — from query, route, body, header
- Model Validation — `[Required]`, `[Range]`, `[StringLength]`
- `ModelState.IsValid`
- Action Results — `Ok()`, `NotFound()`, `BadRequest()`, `CreatedAtAction()`
- `IActionResult` vs `ActionResult<T>`
- `[FromBody]` vs `[FromQuery]` vs `[FromRoute]` vs `[FromHeader]`
- Content Negotiation

---

## 06 Filters

- What are Filters?
- Filter types — Authorization, Resource, Action, Exception, Result
- Filter execution order
- `IActionFilter` vs `IAsyncActionFilter`
- `IExceptionFilter` — global exception handling
- `ServiceFilter` vs `TypeFilter`
- Filter scope — Global vs Controller vs Action

---

## 07 Authentication & Authorization

- Authentication vs Authorization
- Cookie Authentication
- JWT (JSON Web Token) — structure, claims, signing
- `[Authorize]` vs `[AllowAnonymous]`
- Role-based vs Claims-based vs Policy-based authorization
- `ClaimsPrincipal`, `ClaimsIdentity`, `Claim`
- Refresh Token — why and how
- OAuth 2.0 — Authorization Code, Client Credentials
- OpenID Connect (OIDC)
- Identity — ASP.NET Core Identity
- `AddAuthentication()` vs `AddAuthorization()`

---

## 08 API Features

- RESTful API principles
- API Versioning — URL, query string, header
- Pagination — `Skip`, `Take`, `PageNumber`, `PageSize`
- Filtering, Sorting, Searching
- HATEOAS — Hypermedia links
- Rate Limiting — `AddRateLimiter()` (.NET 7+)
- Response Caching — `[ResponseCache]`
- Output Caching (.NET 7+)
- Health Checks — `AddHealthChecks()`
- API Documentation — Swagger / OpenAPI
- Minimal APIs — `MapGet`, `MapPost`, route groups

---

## 09 Configuration & Logging

- Configuration sources — JSON, environment variables, command-line, user secrets
- `IConfiguration` — reading values
- Options pattern — `IOptions<T>`
- User Secrets — development secrets storage
- Logging providers — Console, Debug, File (Serilog, NLog)
- Log levels — `Trace`, `Debug`, `Information`, `Warning`, `Error`, `Critical`
- Structured logging
- `ILogger<T>` — DI-based logging
- Serilog — sinks, enrichers, configuration

---

## 10 Real-time Communication

- SignalR — what and when to use
- Hub — server-side
- Client connection — JavaScript, .NET client
- `SendAsync` vs `InvokeAsync`
- Groups — send to specific groups
- Streaming — server-to-client, client-to-server
- WebSocket vs SignalR
- Scaling SignalR — Redis backplane

---

## 11 MVC (Detailed)

- View Engine — Razor
- Razor syntax — `@`, `@{}`, `@model`
- Layout, `_ViewStart`, `_ViewImports`
- Partial View vs View Component
- Tag Helpers vs HTML Helpers
- ViewBag vs ViewData vs TempData
- Strongly-typed Views
- Areas — organizing large applications
- Data Annotations for validation
- Client-side vs Server-side validation

---
---

# 03 Data Access

---

## 01 SQL Fundamentals

- DDL vs DML vs DCL vs TCL
- `CREATE`, `ALTER`, `DROP`, `TRUNCATE`
- `INSERT`, `UPDATE`, `DELETE`, `SELECT`
- `WHERE` clause — operators, `LIKE`, `IN`, `BETWEEN`
- `NULL` handling — `IS NULL`, `ISNULL()`, `COALESCE()`
- Data types — `INT`, `VARCHAR`, `NVARCHAR`, `DECIMAL`, `DATETIME`
- Primary Key vs Foreign Key
- Unique Key vs Primary Key
- Constraints — `NOT NULL`, `DEFAULT`, `CHECK`, `UNIQUE`
- `IDENTITY` column — auto-increment

---

## 02 Joins

- `INNER JOIN` vs `LEFT JOIN` vs `RIGHT JOIN` vs `FULL OUTER JOIN`
- `CROSS JOIN` — Cartesian product
- Self Join — same table join
- Join vs Subquery — when to use which
- Multiple joins in one query
- `ON` vs `WHERE` in joins

---

## 03 Functions

- Scalar functions vs Table-valued functions
- Aggregate functions — `SUM`, `COUNT`, `AVG`, `MIN`, `MAX`
- String functions — `LEN`, `SUBSTRING`, `CHARINDEX`, `REPLACE`, `TRIM`
- Date functions — `GETDATE()`, `DATEADD`, `DATEDIFF`, `FORMAT`
- Conversion — `CAST()` vs `CONVERT()` vs `TRY_CAST()`
- `ISNULL()` vs `COALESCE()` vs `NULLIF()`
- User-defined functions (UDF)

---

## 04 Grouping & Sorting

- `GROUP BY` — rules and usage
- `HAVING` vs `WHERE`
- `ORDER BY` — `ASC`, `DESC`
- `TOP` vs `OFFSET-FETCH`
- `DISTINCT` — removing duplicates
- `GROUP BY` with aggregate functions

---

## 05 Subqueries & CTE

- Subquery — correlated vs non-correlated
- `EXISTS` vs `IN`
- CTE — Common Table Expression — `WITH`
- Recursive CTE — hierarchical data
- Derived Table vs CTE
- Temp Table vs Table Variable vs CTE

---

## 06 Advanced SQL

- Window Functions — `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`
- `PARTITION BY` vs `GROUP BY`
- `LEAD()`, `LAG()` — accessing adjacent rows
- `PIVOT` and `UNPIVOT`
- `MERGE` — upsert operation
- `CROSS APPLY` vs `OUTER APPLY`
- Dynamic SQL — `EXEC` vs `sp_executesql`

---

## 07 Views & Stored Procedures

- View — virtual table
- Indexed View — materialized view
- Stored Procedure — what and why
- SP vs Function — key differences
- `OUTPUT` parameters
- `RETURN` value
- `TRY...CATCH` in SP
- `RAISERROR` vs `THROW`
- Triggers — `AFTER` vs `INSTEAD OF`

---

## 08 Indexes

- What is an Index? Why use it?
- Clustered vs Non-Clustered Index
- Unique Index
- Composite Index — column order matters
- Covering Index — `INCLUDE`
- Index Seek vs Index Scan vs Table Scan
- When NOT to use indexes
- Index fragmentation — `REBUILD` vs `REORGANIZE`
- Filtered Index

---

## 09 Transactions & ACID

- ACID properties — Atomicity, Consistency, Isolation, Durability
- `BEGIN TRANSACTION`, `COMMIT`, `ROLLBACK`
- `SAVE TRANSACTION` — savepoints
- Transaction Isolation Levels — Read Uncommitted, Read Committed, Repeatable Read, Serializable, Snapshot
- Dirty Read, Non-Repeatable Read, Phantom Read
- Deadlock — detection and prevention
- `SET DEADLOCK_PRIORITY`

---

## 10 Performance Optimization

- Execution Plan — reading and analyzing
- Parameter Sniffing
- `SET STATISTICS IO` / `SET STATISTICS TIME`
- Avoiding `SELECT *`
- SARGable queries — what makes queries index-friendly
- `NOLOCK` hint — risks and when to use
- Temp table vs Table variable — performance
- Batch processing — chunking large operations
- Query hints — `OPTION (RECOMPILE)`, `MAXDOP`

---

## 11 ADO.NET

- What is ADO.NET? Connection-oriented vs Disconnected
- `SqlConnection`, `SqlCommand`, `SqlDataReader`
- `SqlDataAdapter`, `DataSet`, `DataTable`
- Connection string — `Trusted_Connection`, `Integrated Security`
- Connection pooling
- `ExecuteReader()` vs `ExecuteNonQuery()` vs `ExecuteScalar()`
- Parameterized queries — preventing SQL injection
- `using` with `SqlConnection`

---

## 12 Dapper

- What is Dapper? Micro-ORM
- `Query<T>()` vs `QueryFirst<T>()` vs `QueryFirstOrDefault<T>()`
- `Execute()` — insert, update, delete
- Multi-mapping — joins to objects
- `DynamicParameters`
- Stored Procedure execution with Dapper
- Dapper vs EF Core — when to use which
- Transaction support in Dapper

---

## 13 Entity Framework Core — Fundamentals

- What is EF Core? ORM concept
- Code First vs Database First
- `DbContext` — what it does
- `DbSet<T>` — entity collections
- Data Annotations vs Fluent API
- Migrations — `Add-Migration`, `Update-Database`
- Relationships — One-to-One, One-to-Many, Many-to-Many
- Navigation properties
- Shadow properties

---

## 14 EF Core — Querying & Loading

- LINQ to Entities
- Eager Loading — `Include()`, `ThenInclude()`
- Lazy Loading — proxies
- Explicit Loading — `Load()`
- `AsNoTracking()` — read-only queries
- Global Query Filters — soft delete
- Raw SQL — `FromSqlRaw()`, `FromSqlInterpolated()`
- Split Queries — `.AsSplitQuery()`
- Projection — `Select()` for performance

---

## 15 EF Core — Migrations & Transactions

- Migration workflow — `Add`, `Update`, `Remove`, `Script`
- Seed data — `HasData()`
- `SaveChanges()` — unit of work
- Transactions — `BeginTransaction()`, `Commit()`, `Rollback()`
- Concurrency — optimistic concurrency, `[ConcurrencyCheck]`, `[Timestamp]`
- Connection resiliency — retry policies

---

## 16 EF Core — Performance & Tracking

- Change Tracker — `EntityState`: Added, Modified, Deleted, Unchanged, Detached
- `AsNoTracking()` vs tracked queries
- Batch operations — `ExecuteUpdate()`, `ExecuteDelete()` (EF Core 7+)
- Compiled Queries
- Query caching
- N+1 problem — detection and fix
- `DbContext` pooling — `AddDbContextPool()`
- Bulk insert strategies

---

## 17 Caching Basics

- What is Caching? Why cache?
- Cache-aside pattern
- Read-through vs Write-through vs Write-behind
- Cache expiration — Absolute vs Sliding
- Cache invalidation — hardest problem
- When NOT to cache

---

## 18 In-Memory Cache

- `IMemoryCache` — built-in ASP.NET Core
- `Set()`, `Get()`, `TryGetValue()`, `Remove()`
- `MemoryCacheEntryOptions` — expiration, priority, size
- Cache eviction — `PostEvictionCallbacks`
- Thread safety — `GetOrCreate()` pattern
- Limitations — single server, no sharing

---

## 19 Distributed Cache (Redis)

- What is Redis? In-memory data store
- `IDistributedCache` interface
- Redis data types — String, Hash, List, Set, Sorted Set
- `GetAsync()`, `SetAsync()`, `RemoveAsync()`
- Redis CLI basics — `SET`, `GET`, `EXPIRE`, `TTL`
- Redis as message broker — Pub/Sub
- Redis Sentinel vs Redis Cluster
- Connection multiplexer — `StackExchange.Redis`

---

## 20 Cache Strategies

- Cache-aside vs Read-through vs Write-through
- Write-behind (Write-back) — async writing
- Cache warming — preloading
- TTL-based vs Event-based invalidation
- Lazy loading pattern
- Stale-while-revalidate

---

## 21 Cache Consistency

- Cache invalidation strategies
- Event-driven invalidation
- Cache stampede — thundering herd problem
- Distributed locking — preventing race conditions
- Eventual consistency with cache
- Versioned cache keys

---

## 22 Cache Performance

- Hit ratio — measuring cache effectiveness
- Memory pressure — eviction policies (LRU, LFU)
- Serialization overhead — JSON vs binary
- Cache key design — granularity
- Multi-layer caching — L1 (in-memory) + L2 (distributed)
- Monitoring — cache metrics and alerts

---
---

# 04 Communication & API Design

---

## 01 HTTP & HTTPS

- HTTP methods — GET, POST, PUT, PATCH, DELETE
- Safe vs Idempotent methods
- HTTP status codes — 1xx, 2xx, 3xx, 4xx, 5xx
- HTTP headers — `Content-Type`, `Authorization`, `Accept`, `Cache-Control`
- Request vs Response structure
- HTTPS — TLS/SSL, certificates
- HTTP/1.1 vs HTTP/2 vs HTTP/3
- Connection — Keep-Alive, `Connection: close`
- Cookies vs Headers for auth
- CORS — Cross-Origin Resource Sharing

---

## 02 REST

- What is REST? Constraints
- Resource-based URLs — nouns, not verbs
- HTTP methods mapping — CRUD operations
- Statelessness — no server-side session
- Richardson Maturity Model — levels 0–3
- HATEOAS — Hypermedia as the Engine of Application State
- Idempotency — why it matters
- REST vs RPC style
- RESTful best practices — naming, versioning, error format

---

## 03 API Design

- API versioning strategies — URL, header, query string
- Request/Response DTO — shaping data
- Pagination — offset, cursor-based
- Filtering, Sorting, Searching — query parameters
- Error response format — Problem Details (RFC 7807)
- Envelope pattern vs direct response
- Bulk operations — batch endpoints
- Partial updates — PATCH with JSON Patch
- API rate limiting — throttling strategies
- API idempotency keys

---

## 04 Authentication Protocols

- Basic Authentication — Base64 encoding
- Bearer Token — JWT
- OAuth 2.0 — flows: Authorization Code, Client Credentials, PKCE
- OpenID Connect (OIDC) — identity layer on OAuth
- API Key authentication
- HMAC-based authentication
- SAML — enterprise SSO
- Token refresh — access token vs refresh token lifecycle
- Multi-factor authentication (MFA)

---

## 05 API Security

- Input validation — never trust the client
- SQL Injection prevention
- XSS — Cross-Site Scripting prevention
- CSRF — Cross-Site Request Forgery prevention
- CORS configuration — whitelist origins
- Rate limiting and throttling
- IP whitelisting
- HTTPS enforcement
- Security headers — `X-Content-Type-Options`, `Strict-Transport-Security`
- Sensitive data — never expose in URLs or logs
- API Gateway — centralized security

---

## 06 Communication Protocols

- REST vs gRPC vs GraphQL
- gRPC — Protocol Buffers, HTTP/2, streaming
- GraphQL — queries, mutations, subscriptions
- WebSocket — full-duplex, real-time
- Server-Sent Events (SSE) — one-way streaming
- Message Queue — RabbitMQ, Azure Service Bus
- Synchronous vs Asynchronous communication
- Request-Reply vs Fire-and-Forget vs Pub/Sub
- Long polling vs WebSocket vs SSE

---

## 07 API Documentation

- OpenAPI / Swagger — specification format
- Swagger UI — interactive documentation
- `Swashbuckle` vs `NSwag`
- XML comments → Swagger docs
- API examples and schemas
- Versioned documentation
- Postman collections — sharing and testing

---
---

# 05 Architecture & Design Patterns

---

## 01 Software Architecture Basics

- What is Software Architecture?
- Architecture vs Design — scope difference
- Coupling vs Cohesion
- Separation of Concerns (SoC)
- DRY, KISS, YAGNI principles
- Horizontal vs Vertical slicing
- Monolith vs Distributed systems
- Scalability — horizontal vs vertical

---

## 02 N-Tier Architecture

- What is N-Tier? Layers explained
- Presentation Layer → Business Layer → Data Access Layer
- Layer vs Tier — logical vs physical
- Benefits — separation, testability
- Drawbacks — tight coupling between layers, anemic domain model
- When to use N-Tier vs other architectures

---

## 03 Clean Architecture

- What is Clean Architecture?
- Dependency Rule — inward only
- Layers — Domain, Application, Infrastructure, Presentation
- Domain Layer — entities, value objects, domain events
- Application Layer — use cases, interfaces, DTOs
- Infrastructure Layer — DB, external services, implementations
- Presentation Layer — API controllers, UI
- Interface Adapters — mapping between layers
- Clean Architecture vs Onion Architecture vs Hexagonal

---

## 04 Microservices

- Monolith vs Microservices — trade-offs
- Service boundaries — bounded contexts
- Communication — synchronous (HTTP/gRPC) vs asynchronous (messaging)
- API Gateway — routing, aggregation
- Service Discovery
- Data ownership — database per service
- Saga pattern — distributed transactions
- Circuit Breaker pattern — resilience
- Sidecar pattern
- Observability — logging, tracing, metrics
- Docker & containerization basics

---

## 05 Repository & Unit of Work

- Repository pattern — what and why
- Generic Repository vs Specific Repository
- `IRepository<T>` interface design
- Unit of Work pattern — coordinating multiple repositories
- `SaveChanges()` as Unit of Work boundary
- Repository + EF Core — is it needed?
- Anti-patterns — leaky abstraction, over-abstraction

---

## 06 CQRS

- Command Query Responsibility Segregation — concept
- Command vs Query — write model vs read model
- Separate read/write databases
- MediatR — implementing CQRS in .NET
- `IRequest<T>`, `IRequestHandler<T>`
- Benefits — scalability, optimization, separation
- When to use CQRS vs simple CRUD
- CQRS + Event Sourcing — overview

---

## 07 Domain-Driven Design (Basic)

- What is DDD? Strategic vs Tactical
- Ubiquitous Language
- Bounded Context — defining boundaries
- Entities vs Value Objects
- Aggregate — aggregate root, consistency boundary
- Domain Events — decoupled communication
- Domain Services vs Application Services
- Repository pattern in DDD context
- Anemic Domain Model vs Rich Domain Model

---

## 08 Event-Driven Architecture (Basic)

- What is Event-Driven Architecture?
- Event vs Command vs Message
- Event Sourcing — storing events, rebuilding state
- Event Store
- Pub/Sub pattern — publishers and subscribers
- Message Broker — RabbitMQ, Kafka, Azure Service Bus
- Eventual Consistency — trade-offs
- Idempotency in event processing
- Dead Letter Queue (DLQ)

---

## 09 Design Patterns — Basics

- What is a Design Pattern?
- Gang of Four (GoF) — 23 patterns
- Creational vs Structural vs Behavioral
- Pattern vs Anti-pattern
- When to use patterns — don't over-engineer
- UML basics for patterns

---

## 10 Creational Patterns

- Singleton — single instance, thread safety, `Lazy<T>`
- Factory Method — creating objects without specifying class
- Abstract Factory — family of related objects
- Builder — step-by-step complex object construction
- Prototype — cloning objects

---

## 11 Structural Patterns

- Adapter — incompatible interface bridge
- Decorator — adding behavior dynamically
- Facade — simplified interface to subsystem
- Proxy — controlled access to object
- Composite — tree structure, uniform treatment
- Bridge — abstraction from implementation
- Flyweight — sharing common state

---

## 12 Behavioral Patterns

- Strategy — interchangeable algorithms
- Observer — event notification
- Command — encapsulate request as object
- Template Method — algorithm skeleton, subclass steps
- Chain of Responsibility — pass along handlers
- Mediator — centralized communication (MediatR)
- State — behavior changes with state
- Iterator — sequential access without exposing structure

---

## 13 Architectural Patterns

- MVC — Model-View-Controller
- MVVM — Model-View-ViewModel
- Repository pattern
- Unit of Work pattern
- CQRS pattern
- Event Sourcing pattern
- Saga pattern — distributed transactions
- Strangler Fig — gradual migration

---

## 14 Distributed System Patterns

- Circuit Breaker — Polly, fail-fast
- Retry pattern — exponential backoff
- Bulkhead — isolation
- Timeout pattern
- Cache-aside pattern
- Outbox pattern — reliable messaging
- Saga — orchestration vs choreography
- Leader Election
- Sharding — data partitioning
- Sidecar pattern
- CQRS vs saga

---
---

# 06 Bonus — Interview Quick Hits

---

## Common Comparisons (Rapid Fire)

- `abstract class` vs `interface`
- `IEnumerable` vs `IQueryable`
- `Task` vs `Thread`
- `async void` vs `async Task`
- `==` vs `.Equals()`
- `String` vs `string`
- `const` vs `readonly` vs `static readonly`
- `Dispose()` vs Finalizer (`~`)
- `StringBuilder` vs `String`
- EF Core vs Dapper
- Scoped vs Transient vs Singleton
- `AddDbContext` vs `AddDbContextPool`
- REST vs gRPC
- Cookie vs Token authentication
- Monolith vs Microservices
- SQL vs NoSQL
- Clustered vs Non-Clustered Index
- `DELETE` vs `TRUNCATE` vs `DROP`
- Optimistic vs Pessimistic concurrency
- Repository pattern — yes or no with EF Core?
