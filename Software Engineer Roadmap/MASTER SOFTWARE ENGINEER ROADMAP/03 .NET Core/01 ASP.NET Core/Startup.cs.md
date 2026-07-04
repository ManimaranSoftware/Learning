Startup.cs (.NET Core 3.1 and Earlier)

- Startup.cs - Application configuration class
- ConfigureServices() - Register services - Add services to DI container
- Configure() -  Configure middleware pipeline - Add middleware to request pipeline

Program.cs vs Startup.cs

- Program.cs (.NET 6+) - Contains both service registration and middleware configuration
- Startup.cs (.NET Core 3.1 and earlier) - Separate class for configuration
- Modern .NET - Uses Program.cs (Minimal Hosting Model)


Startup.cs

ConfigureServices()
 ↓
Configure()


Startup.cs (.NET Core 3.1 and Earlier)

public class Startup
{
//Register Services
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddControllers();
        services.AddScoped<IUserService, UserService>();
    }

//Configure Middleware Pipeline
    public void Configure(IApplicationBuilder app)
    {
        app.UseRouting();
        app.UseAuthentication();
        app.UseAuthorization();
        app.UseEndpoints(endpoints =>
        {
            endpoints.MapControllers();
        });
    }
}