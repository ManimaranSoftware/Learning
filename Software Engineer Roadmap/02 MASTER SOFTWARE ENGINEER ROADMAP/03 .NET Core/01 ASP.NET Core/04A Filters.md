### Filters

- Filters - Code that runs before or after specific stages in the request pipeline.
- Purpose - Cross-cutting concerns like logging, authorization, caching, exception handling.
- Scope - Applied globally, at controller level, or at action level.
- Execution - Filters run within the MVC filter pipeline (after routing selects the endpoint).

---

### Filter Pipeline

- Filter Pipeline - Sequence of filter stages that execute around an action method.
- Flow - Authorization → Resource → Action → Exception → Result.
- Each stage has a "before" and "after" phase.

---

### Types of Filters

- Authorization Filter - Runs first, determines if user is authorized.
- Resource Filter - Runs after authorization, before model binding. Used for caching.
- Action Filter - Runs before and after action method execution.
- Exception Filter - Handles unhandled exceptions thrown by the action.
- Result Filter - Runs before and after the action result is executed.

---

### Authorization Filter

- Interface - `IAuthorizationFilter` or `IAsyncAuthorizationFilter`.
- Runs first in the pipeline.
- Can short-circuit the pipeline by setting a result.
- Built-in - `[Authorize]` attribute.

---

### Resource Filter

- Interface - `IResourceFilter` or `IAsyncResourceFilter`.
- Runs after authorization, before model binding.
- Use Case - Response caching, short-circuiting expensive processing.
- Methods - `OnResourceExecuting()`, `OnResourceExecuted()`.

---

### Action Filter

- Interface - `IActionFilter` or `IAsyncActionFilter`.
- Runs immediately before and after the action method.
- Methods - `OnActionExecuting()`, `OnActionExecuted()`.
- Use Case - Logging, modifying arguments, modifying result.

---

### Exception Filter

- Interface - `IExceptionFilter` or `IAsyncExceptionFilter`.
- Runs only when action or action filters throw an unhandled exception.
- Method - `OnException()`.
- Use Case - Global error handling, custom error responses.

---

### Result Filter

- Interface - `IResultFilter` or `IAsyncResultFilter`.
- Runs before and after action result execution.
- Methods - `OnResultExecuting()`, `OnResultExecuted()`.
- Use Case - Modifying response, adding headers.

---

### Filter Execution Order

- Global filters run first.
- Controller-level filters run second.
- Action-level filters run third.
- Order Property - `Order` property controls execution priority within same scope.
- Lower order value runs first.

---

### Applying Filters

- Globally - `builder.Services.AddControllers(options => options.Filters.Add<MyFilter>())`.
- Controller Level - `[ServiceFilter(typeof(MyFilter))]` on controller.
- Action Level - `[ServiceFilter(typeof(MyFilter))]` on action method.
- TypeFilter - `[TypeFilter(typeof(MyFilter))]` for filters with constructor dependencies.

---

### Custom Action Filter Example

- Create class implementing `IActionFilter`.
- Override `OnActionExecuting()` for before logic.
- Override `OnActionExecuted()` for after logic.
- Register in DI container.
- Apply using `[ServiceFilter]` or `[TypeFilter]`.

---

### ServiceFilter vs TypeFilter

- ServiceFilter - Resolves filter from DI container. Must be registered in DI.
- TypeFilter - Creates filter instance using DI. No need to register in DI.

---

### Filter vs Middleware

- Middleware - Runs for every request. No access to MVC context.
- Filter - Runs only for MVC requests. Has access to ActionContext, ModelState, routing data.
- Middleware - Better for cross-cutting concerns across all requests (logging, CORS).
- Filter - Better for MVC-specific concerns (validation, authorization on actions).

---

### Short-Circuiting

- Filters can short-circuit the pipeline by setting `context.Result`.
- Prevents subsequent filters and the action from executing.
- Common in Authorization and Resource filters.

---

### Benefits

- Reusable cross-cutting logic.
- Clean separation of concerns.
- Granular control over execution order.
- Access to MVC-specific context.
- Easy to apply at different scopes.
