## Filters

- Filters execute before or after an action method.
    
- Used for cross-cutting concerns like authorization, logging, exception handling, and response modification.
    

---

## Types of Filters

### Authorization Filter

- Executes **before** the action.
    
- Checks whether the user is authorized.
    

```csharp
[Authorize]
public IActionResult Get()
{
    return Ok();
}
```

---

### Action Filter

- Executes **before and after** an action method.
    
- Used for logging, validation, etc.
    

---

### Exception Filter

- Handles exceptions thrown by action methods.
    

---

### Result Filter

- Executes **before and after** the action result is executed.
    
- Used to modify the response.
    

---

## Controller vs `ControllerBase`

|Controller|ControllerBase|
|---|---|
|Used for MVC applications|Used for Web APIs|
|Supports `View()`|Does not support `View()`|
|Returns Views and APIs|Returns APIs only|

---

## Middleware vs Filter

|Middleware|Filter|
|---|---|
|Runs for every HTTP request|Runs only for MVC actions|
|Part of request pipeline|Part of MVC pipeline|
|Executes before MVC|Executes after routing selects an MVC action|

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