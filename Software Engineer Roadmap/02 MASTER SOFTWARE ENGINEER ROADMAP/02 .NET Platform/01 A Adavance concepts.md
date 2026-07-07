# Minimal APIs

**Minimal APIs** are ==a streamlined, lightweight approach introduced in .NET 6 for building HTTP services with **minimal code, ceremony, and dependencies**==. Instead of using the traditional Model-View-Controller (MVC) architecture with separate controller classes, routes and actions are declared fluently directly inside the `Program.cs` file using lambda expressions. 

Traditional Controller API (Verbosity)

csharp

```
[ApiController]
[Route("[controller]")]
public class HelloWorldController : ControllerBase
{
    [HttpGet]
    public string Get() => "Hello World!";
}
```

Use code with caution.

Minimal API Approach (Simplicity)

csharp

```
var app = WebApplication.Create(args);
app.MapGet("/", () => "Hello World!");
app.Run();
```

# Native AOT

Native AOT (Ahead-of-Time) compilation in .NET ==compiles C# code directly into platform-specific native machine code at build time==. By eliminating the JIT (Just-In-Time) compiler, it drastically improves application startup times, reduces memory consumption, and creates lightweight, self-contained executable files

Key Benefits of Native AOT

- **Faster Startup:** Because the code is already compiled into native machine instructions, apps start almost instantly, making it ideal for cloud-native or serverless environments (e.g., AWS Lambda or Azure Functions).
- **Smaller Footprint:** It strips away the heavy framework overhead and JIT compiler, resulting in drastically smaller deployment sizes and container images.
- **No Runtime Required:** The app becomes a self-contained executable, meaning it can run on systems without the .NET runtime installed. 
- **Better Resource Usage:** Reduced memory consumption allows for higher deployment density on cloud servers.
Native AOT is highly recommended for **console applications, Minimal APIs, and microservices/serverless functions** where startup speed and memory size are critical. It is typically not recommended for desktop UI frameworks (like WPF or WinForms) or enterprise applications heavily reliant on dynamic reflection


How to Enable It

You can enable Native AOT in your project by adding `<PublishAot>true</PublishAot>` to your `.csproj` file:

xml

```
<PropertyGroup>
    <PublishAot>true</PublishAot>
</PropertyGroup>
```