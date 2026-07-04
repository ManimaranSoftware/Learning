## Filters

- Filters execute before or after an action method.
- Used for authorization, logging, validation, exception handling, and modifying responses.

---

## Types of Filters

### Authorization Filter

- Executes first.
- Checks whether the user is authorized.

```csharp
[Authorize]
public IActionResult Get()
{
    return Ok();
}
```

---

### Resource Filter

- Executes before and after model binding.
- Used for caching and resource management.

```csharp
public class MyResourceFilter : IResourceFilter
{
    public void OnResourceExecuting(ResourceExecutingContext context)
    {
        Console.WriteLine("Before Model Binding");
    }

    public void OnResourceExecuted(ResourceExecutedContext context)
    {
        Console.WriteLine("After Response");
    }
}
```

---

### Action Filter

- Executes before and after an action method.
- Commonly used for logging and validation.

```csharp
public class MyActionFilter : IActionFilter
{
    public void OnActionExecuting(ActionExecutingContext context)
    {
        Console.WriteLine("Before Action");
    }

    public void OnActionExecuted(ActionExecutedContext context)
    {
        Console.WriteLine("After Action");
    }
}
```

---

### Exception Filter

- Handles exceptions thrown by action methods.

```csharp
public class MyExceptionFilter : IExceptionFilter
{
    public void OnException(ExceptionContext context)
    {
        Console.WriteLine("Exception Handled");
    }
}
```

---

### Result Filter

- Executes before and after the action result.
- Used to modify the response.

```csharp
public class MyResultFilter : IResultFilter
{
    public void OnResultExecuting(ResultExecutingContext context)
    {
        Console.WriteLine("Before Result");
    }

    public void OnResultExecuted(ResultExecutedContext context)
    {
        Console.WriteLine("After Result");
    }
}
```

### Interview Answer

> ASP.NET Core provides **five main filters**:
> 
> - **Authorization Filter** → Checks authorization.
> - **Resource Filter** → Runs before/after model binding for caching and resource management.
> - **Action Filter** → Runs before/after the action method for logging and validation.
> - **Exception Filter** → Handles exceptions from action methods.
> - **Result Filter** → Runs before/after the action result to modify the response.

---

Authorization Filter
        ↓
Resource Filter
        ↓
Model Binding
        ↓
Action Filter
        ↓
Action Method
        ↓
Exception Filter (only if exception occurs)
        ↓
Result Filter
        ↓
HTTP Response

---

## Controller vs `ControllerBase`

| Controller                | ControllerBase            |
| ------------------------- | ------------------------- |
| Used for MVC applications | Used for Web APIs         |
| Supports `View()`         | Does not support `View()` |
| Returns Views and APIs    | Returns APIs only         |

---

## Middleware vs Filter

| Middleware                  | Filter                                       |
| --------------------------- | -------------------------------------------- |
| Runs for every HTTP request | Runs only for MVC actions                    |
| Part of request pipeline    | Part of MVC pipeline                         |
| Executes before MVC         | Executes after routing selects an MVC action |

---

## Conventional Routing vs Attribute Routing

|Conventional Routing|Attribute Routing|
|---|---|
|Defined centrally in `Program.cs`|Defined on controllers/actions|
|Better for traditional MVC|Preferred for Web APIs|

### Conventional Routing

```csharp
app.MapControllerRoute(
    name: "default",
    pattern: "{controller=Home}/{action=Index}/{id?}");
```

### Attribute Routing

```csharp
[Route("api/employees")]
[HttpGet]
public IActionResult Get()
{
    return Ok();
}
```

---

## Common MVC Attributes

```csharp
[ApiController]

[Route]

[HttpGet]
[HttpPost]
[HttpPut]
[HttpPatch]
[HttpDelete]

[FromBody]
[FromRoute]
[FromQuery]

[Authorize]
```

---

## Common Interview Comparisons

### Model vs View vs Controller

|Model|View|Controller|
|---|---|---|
|Data & Business Logic|UI|Handles HTTP Requests|

---

### Controller vs Action Method

|Controller|Action Method|
|---|---|
|Class|Public Method|
|Groups related requests|Handles one specific request|

---

### `IActionResult` vs `ActionResult<T>`

|`IActionResult`|`ActionResult<T>`|
|---|---|
|Flexible response types|Strongly typed response|
|Used when response varies|Used for typed Web APIs|

---

### GET vs POST

|GET|POST|
|---|---|
|Retrieve data|Create data|
|Parameters in URL|Data in request body|
|Safe and idempotent|Used to create resources|

---

### PUT vs PATCH

|PUT|PATCH|
|---|---|
|Updates the entire resource|Updates only specified fields|

---

## Benefits of MVC

- Separation of concerns.
    
- Better maintainability.
    
- Easier testing.
    
- Reusable components.
    
- Flexible routing.
    
- Automatic model binding.
    
- Built-in validation.
    
- Supports Dependency Injection.
    
- Well suited for scalable applications.
    

---

## MVC Request Flow

```text
Client
   │
HTTP Request
   │
   ▼
Routing
   │
   ▼
Controller
   │
   ▼
Action Method
   │
   ▼
Model / Service
   │
   ▼
Database
   │
   ▼
Action Result
   │
HTTP Response
   │
   ▼
Client
```