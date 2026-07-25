# Minimal APIs

- Introduced in **.NET 6**.
- Lightweight approach for building HTTP APIs with minimal code.
- Uses route handlers directly in `Program.cs`.
- Eliminates the need for Controllers in simple applications.
- Ideal for:
	- Small APIs
	- Microservices
	- Serverless applications
	- Prototypes

## Traditional Controller API

```csharp
[ApiController]
[Route("[controller]")]
public class HelloWorldController : ControllerBase
{
    [HttpGet]
    public string Get() => "Hello World!";
}
```

## Minimal API

```csharp
var app = WebApplication.CreateBuilder(args).Build();

app.MapGet("/", () => "Hello World!");

app.Run();
```

## Advantages

- Less boilerplate code.
- Faster development.
- Better performance.
- Easy to read and maintain.
- Perfect for lightweight APIs.

## Limitations

- Not ideal for large enterprise applications.
- Complex business logic is easier to organize using Controllers.

---

# Native AOT (Ahead-of-Time Compilation)

- Introduced in **.NET 7** and significantly improved in **.NET 8**.
- Compiles C# code into native machine code during publish time.
- Eliminates the need for JIT compilation at runtime.

## Benefits

- Faster application startup.
- Lower memory usage.
- Smaller deployment size.
- Self-contained executable.
- No .NET Runtime required on the target machine.

## Best Use Cases

- Console Applications
- Minimal APIs
- Microservices
- Serverless Applications (AWS Lambda, Azure Functions)

## Limitations

- Limited support for Reflection.
- Not recommended for:
	- WPF
	- WinForms
	- Applications heavily using dynamic loading or Reflection.

## Enable Native AOT

Add the following to your `.csproj` file:

```xml
<PropertyGroup>
    <PublishAot>true</PublishAot>
</PropertyGroup>
```

---

# Interview Summary

| Topic | Definition |
|--------|------------|
| Minimal APIs | Lightweight way to build HTTP APIs without Controllers. |
| Native AOT | Compiles C# directly to native machine code during publish time, removing the need for JIT at runtime. |