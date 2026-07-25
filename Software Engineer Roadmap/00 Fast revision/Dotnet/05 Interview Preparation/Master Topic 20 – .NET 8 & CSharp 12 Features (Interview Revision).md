## .NET 8 Highlights
- Long-Term Support (LTS)
- Better Performance
- Native AOT
- Improved ASP.NET Core
- Improved Minimal APIs
- Better Container Support

> [!tip]
> **Memory Tip:** .NET 8 = Faster + Smaller + Cloud Ready

---

## Native AOT
- Ahead-of-Time Compilation
- Faster Startup
- Lower Memory Usage
- Smaller Deployment
- Best for Microservices & Serverless

---

## ASP.NET Core Improvements
- Better Performance
- Improved Routing
- Better Request Handling
- Faster JSON Serialization
- Enhanced Minimal APIs

---

## Minimal APIs
- Less Boilerplate Code
- Lightweight APIs
- Faster Development
- Suitable for Small Services

```csharp
app.MapGet("/", () => "Hello World");
```

---

## `TimeProvider`
- Centralized Time Abstraction
- Easier Unit Testing
- Replace `DateTime.Now`
- Dependency Injection Friendly

---

## Keyed Dependency Injection
- Multiple Implementations
- Register with Keys
- Resolve Specific Service
- Built-in Support

---

## C# 12 Primary Constructors
- Constructor in Class Declaration
- Less Boilerplate
- Cleaner Code

```csharp
public class Employee(string name)
{
}
```

---

## Collection Expressions
- Simplified Collection Initialization

```csharp
int[] numbers = [1, 2, 3];
```

---

## Default Lambda Parameters
- Lambda Expressions can have Default Parameters
- Cleaner Delegate Definitions

---

## Performance Improvements
- Better Garbage Collection
- Faster LINQ
- Faster JSON (`System.Text.Json`)
- Reduced Memory Allocation

---

## Container Improvements
- Smaller Docker Images
- Better Linux Support
- Faster Startup
- Cloud Optimized

---

## JSON Improvements
- `System.Text.Json`
- Better Serialization
- Better Deserialization
- Improved Performance

---

## Dependency Injection Improvements
- Keyed Services
- Better Service Resolution
- Improved Performance

---

## Interview Traps
- .NET Framework vs .NET
- .NET 6 vs .NET 8
- Native AOT vs JIT
- MVC vs Minimal APIs
- `DateTime.Now` vs `TimeProvider`
- `Newtonsoft.Json` vs `System.Text.Json`
- Constructor Injection vs Keyed DI
- Primary Constructor vs Traditional Constructor

---

## 30-Second Revision Formula

.NET 8 → Native AOT → ASP.NET Core → Minimal APIs → `TimeProvider` → Keyed DI → Primary Constructors → Collection Expressions → Performance → Containers → JSON → DI Improvements