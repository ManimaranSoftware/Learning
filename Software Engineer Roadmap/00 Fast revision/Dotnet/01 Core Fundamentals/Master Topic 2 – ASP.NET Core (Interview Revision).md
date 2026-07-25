
## ASP.NET Core Architecture
- Cross Platform
- Open Source
- High Performance
- Built-in DI
- Middleware-based Pipeline
- Kestrel Web Server

> [!tip]
> **Memory Tip:** ASP.NET Core = Fast + Cross Platform + Middleware

---

## Request Pipeline
- Request → Middleware → Endpoint → Response
- Order Matters
- Request passes through every Middleware
- Short Circuiting possible

> [!tip]
> **Memory Tip:** Pipeline = Water Pipe (Request flows through every pipe)

---

## Middleware
- Executes on every Request/Response
- Order is important
- Built-in & Custom Middleware
- `app.Use()` → Continue Pipeline
- `app.Run()` → Terminates Pipeline
- `app.Map()` → Branch Pipeline

> [!tip]
> **Memory Tip:** Middleware = Security Checkpoints

---

## Dependency Injection (DI)
- Loose Coupling
- Better Testability
- Built-in IoC Container
- Constructor Injection (Preferred)
- Avoid Service Locator

> [!tip]
> **Memory Tip:** DI = Don't Create, Inject

---

## Service Lifetimes
- `Transient` → New instance every request
- `Scoped` → One instance per HTTP Request
- `Singleton` → One instance for Application Lifetime

> [!tip]
> **Memory Tip:** T → S → S = Every Time → Single Request → Single Application

---

## Routing
- Attribute Routing
- Conventional Routing
- Route Parameters
- Route Constraints

---

## Model Binding
- `FromBody`
- `FromRoute`
- `FromQuery`
- `FromHeader`
- Converts HTTP data into C# Objects

---

## Validation
- Data Annotations
- `ModelState.IsValid`
- `[Required]`
- `[Range]`
- `[StringLength]`

---

## Filters
- Authorization Filter
- Action Filter
- Exception Filter
- Result Filter
- Resource Filter

> [!tip]
> **Memory Tip:** Filters = Execute Before/After Controller

---

## Configuration
- `appsettings.json`
- Environment Variables
- User Secrets
- `IConfiguration`
- `IOptions<T>`

---

## Logging
- `ILogger<T>`
- Log Levels
- Structured Logging
- Serilog (Common in Projects)

> [!tip]
> **Memory Tip:** Trace → Debug → Information → Warning → Error → Critical

---

## Authentication
- Verify User Identity
- Cookie Authentication
- JWT Authentication
- OAuth (Basics)

---

## Authorization
- Verify Permissions
- `[Authorize]`
- `[AllowAnonymous]`
- Role Based
- Policy Based
- Claims Based

---

## JWT
- Header
- Payload (Claims)
- Signature
- Stateless Authentication

> [!tip]
> **Memory Tip:** JWT = Header + Payload + Signature

---

## CORS
- Cross-Origin Resource Sharing
- Allows/Blocks Requests from other Domains
- Configure using `AddCors()` & `UseCors()`

---

## Global Exception Handling
- Exception Middleware
- `UseExceptionHandler()`
- Custom Exception Middleware
- Consistent Error Response

---

## Caching
- `IMemoryCache`
- `IDistributedCache`
- Redis
- Improves Performance
- Reduces Database Calls

---

## Health Checks
- `AddHealthChecks()`
- `/health`
- Used by Monitoring Tools
- Checks Application Dependencies

---

## Interview Traps
- Authentication vs Authorization
- `Transient` vs `Scoped` vs `Singleton`
- `app.Use()` vs `app.Run()` vs `app.Map()`
- Middleware vs Filters
- `FromBody` vs `FromQuery`
- Cookie vs JWT
- `IConfiguration` vs `IOptions<T>`
- `IMemoryCache` vs `IDistributedCache`
- Kestrel vs IIS

---

## 30-Second Revision Formula

Architecture → Pipeline → Middleware → DI → Lifetimes → Routing → Model Binding → Validation → Filters → Configuration → Logging → Authentication → Authorization → JWT → CORS → Exception Handling → Caching → Health Checks