### Request Pipeline

- Request Pipeline - Sequence of middleware components that process HTTP requests and responses.
- Flow - Request → Middleware → Endpoint → Response.
- Order - Middleware execution order is important.

---

### Middleware

- Middleware - Software component that processes HTTP requests and responses.
- Purpose - Logging, Authentication, Exception Handling, CORS, Routing.
- Execution - Each middleware can handle, modify or pass the request to the next middleware.

---

### Built-in Middleware

- Exception Handling Middleware - Handles unhandled exceptions globally.
- HTTPS Redirection - Redirects HTTP requests to HTTPS.
- Static Files Middleware - Serves static files (CSS, JS, Images).
- Routing Middleware - Matches incoming requests to endpoints.
- Authentication Middleware - Authenticates users.
- Authorization Middleware - Checks user permissions.
- CORS Middleware - Controls cross-origin requests.
- Endpoint Middleware - Executes matched endpoint.

---

### Custom Middleware

- Custom Middleware - User-defined middleware for custom request processing.
- Created Using - Class with `Invoke()` or `InvokeAsync()` method.
- Registered Using - `app.UseMiddleware<T>()`.

---

### Middleware Registration

- `Use()` - Executes middleware and calls next middleware.
- `Run()` - Terminal middleware, Ends request pipeline.
- `Map()` - Creates separate request pipeline for specific path.
- `MapWhen()` - Branches pipeline based on condition.
- `UseWhen()` - Executes middleware conditionally.

---

### Request Delegate

- Request Delegate - Represents the next middleware in the pipeline.
- Invoked Using - `await next(context)`.

---

### Endpoint

- Endpoint - Final destination that processes the request.
- Examples - Controller Action, Minimal API, Razor Page.

---

### Benefits

- Modular architecture.
- Easy request processing.
- Reusable components.
- Better separation of concerns.
- Easy customization.