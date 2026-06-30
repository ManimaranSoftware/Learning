### Configuration

- Configuration - Stores application settings outside the code.
- Sources - `appsettings.json`, Environment Variables, User Secrets, Azure Key Vault.

---

### appsettings.json

- Default configuration file.
- Stores Connection Strings, JWT, Logging, Custom Settings.

---

### appsettings.{Environment}.json

- Environment-specific configuration.
- Examples - `appsettings.Development.json`, `appsettings.Production.json`.

---

### IConfiguration

- Interface used to read configuration values.
- Supports hierarchical configuration.

---

### Options Pattern

- Binds configuration sections to strongly typed classes.
- Improves maintainability and type safety.
- Commonly uses `IOptions<T>`.

---

### Environment

- Identifies current application environment.
- Common Values - Development, Staging, Production.

---

### Logging

- Logging - Records application events, errors and diagnostic information.
- Helps in monitoring and troubleshooting.

---

### ILogger

- Built-in logging interface in ASP.NET Core.
- Supports multiple logging providers.
- Common Log Levels - Trace, Debug, Information, Warning, Error, Critical.

---

### Serilog

- Popular structured logging framework.
- Supports sinks like File, SQL Server, Elasticsearch and Seq.

---

### NLog

- Alternative logging framework.
- Supports file, database and event log targets.

---

### Exception Handling Middleware

- Handles unhandled exceptions globally.
- Returns consistent error responses.
- Prevents exposing internal application details.

---

### Benefits

- Centralized configuration.
- Environment-specific settings.
- Structured logging.
- Easier debugging.
- Better monitoring.
- Improved application reliability.