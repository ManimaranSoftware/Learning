Program.cs(.NET 6+)

- Program.cs - Application entry point
- WebApplication.CreateBuilder(args) - Host Builder

- Creates application builder and configures services, configuration(appsettings.json), logging, and hosting(Hosting Environment)
- Creates application host and initializes configuration, logging, and DI

- builder.Services - Register dependencies (Register Services)
- builder.Build() - Build application
- app.UseXXX() - Configure middleware pipeline
- app.MapControllers() - Maps controller endpoints (Endpoint Mapping)
- app.Run() - Starts application
- Host Builder - Creates and configures application host
- Service Registration - Register services in DI container

- builder.Services.AddControllers();
- builder.Services.AddScoped<IUserService, UserService>();
- builder.Services.AddDbContext`<AppDbContext>()`;

- Middleware Registration - Configure request pipeline - Configure HTTP request pipeline

- app.UseAuthentication();
- app.UseAuthorization();
- app.UseExceptionHandler();

Common Methods

- AddControllers() - Register controllers
- AddDbContext() - Register EF Core DbContext
- AddScoped() - Scoped service registration
- AddSingleton() - Singleton service registration
- AddTransient() - Transient service registration

Important Middlewares Order

- UseSerilogRequestLogging() - Logs HTTP requests and responses
-  UseExceptionHandler() - Global exception handling
-  UseHttpsRedirection() - HTTP → HTTPS
-  UseRouting() - Route matching
-  UseAuthentication() - Verify user identity
-  UseAuthorization() - Verify permissions
-  MapControllers() - Execute controller endpoint
-  app.Run() - Start application



## Code Snippit


Program.cs (.NET 6+)

var builder = WebApplication.CreateBuilder(args);

builder.Services.AddControllers();
builder.Services.AddScoped<IUserService, UserService>();

var app = builder.Build();

app.UseAuthentication();
app.UseAuthorization();
app.MapControllers();

app.Run();



Logging
 ↓
Exception
 ↓
HTTPS
 ↓
Routing
 ↓
Authentication
 ↓
Authorization
 ↓
Controllers
 ↓
Run



Program.cs

Services
 ↓
Build
 ↓
Middleware
 ↓
MapControllers
 ↓
Run