## `IActionResult`

- Returns different types of HTTP responses.
    
- Used when the response type can vary.
    

```csharp
public IActionResult Get()
{
    return Ok();
}
```

---

## `ActionResult<T>`

- Returns a strongly typed object with an HTTP status code.
    
- Recommended for Web APIs.
    

```csharp
public ActionResult<Employee> Get()
{
    return Ok(new Employee());
}
```

---

## `IActionResult` vs `ActionResult<T>`

|`IActionResult`|`ActionResult<T>`|
|---|---|
|Returns different response types|Returns a strongly typed object|
|Flexible responses|Strongly typed API responses|

---

## Common Action Results

### `Ok()`

- Returns **200 OK**.
    

```csharp
return Ok(employee);
```

---

### `Created()`

- Returns **201 Created**.
    

```csharp
return Created("/api/employees/1", employee);
```

---

### `BadRequest()`

- Returns **400 Bad Request**.
    

```csharp
return BadRequest();
```

---

### `NotFound()`

- Returns **404 Not Found**.
    

```csharp
return NotFound();
```

---

### `NoContent()`

- Returns **204 No Content**.
    

```csharp
return NoContent();
```

---

### `Unauthorized()`

- Returns **401 Unauthorized**.
    

```csharp
return Unauthorized();
```

---

## HTTP Status Codes

- `200 OK` → Request successful.
    
- `201 Created` → Resource created.
    
- `204 No Content` → Success with no response body.
    
- `400 Bad Request` → Invalid request.
    
- `401 Unauthorized` → Authentication required.
    
- `403 Forbidden` → Access denied.
    
- `404 Not Found` → Resource not found.
    
- `500 Internal Server Error` → Server error.
    

---

## Dependency Injection (DI)

- Injects required services into a controller.
    
- Promotes loose coupling and testability.
    

```csharp
public class EmployeeController : ControllerBase
{
    private readonly IEmployeeService _service;

    public EmployeeController(IEmployeeService service)
    {
        _service = service;
    }
}
```

---

## REST API

- Follows REST principles.
    
- Uses HTTP methods to perform CRUD operations.
    
- Resources are identified using URLs.
    
- Typically returns JSON.
    

### CRUD Mapping

|Operation|HTTP Verb|
|---|---|
|Create|POST|
|Read|GET|
|Update|PUT / PATCH|
|Delete|DELETE|

---

## Example REST API

```text
GET    /api/employees

GET    /api/employees/1

POST   /api/employees

PUT    /api/employees/1

PATCH  /api/employees/1

DELETE /api/employees/1
```

---

## Flow

```text
Client
   │
HTTP Request
   │
   ▼
Controller
   │
   ▼
Service
   │
   ▼
Database
   │
   ▼
ActionResult
   │
HTTP Response
```