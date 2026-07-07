
## MVC

- MVC (Model-View-Controller) is a design pattern that separates an application into **Model**, **View**, and **Controller**.
    
- Improves separation of concerns, maintainability, and testability.
    

---

## MVC Architecture

```text
Client
   │
HTTP Request
   │
   ▼
Controller
   │
   ├── Calls Model
   │
   ▼
Model (Business Logic & Data)
   │
   ▼
Controller
   │
   ▼
View / JSON Response
   │
HTTP Response
   │
   ▼
Client
```

---

## Request Lifecycle

```text
HTTP Request
      ↓
Routing
      ↓
Controller
      ↓
Action Method
      ↓
Model / Service
      ↓
Response (View / JSON)
```

---

## Model

- Represents application data and business logic.
    
- Communicates with the database or service layer.
    

**Example**

```csharp
public class Employee
{
    public int Id { get; set; }

    public string Name { get; set; }
}
```

---

## View

- Responsible for displaying the UI.
    
- Typically written using Razor (`.cshtml`).
    

```csharp
return View();
```

---

## Controller

- Handles incoming HTTP requests.
    
- Processes business logic (usually through services).
    
- Returns a View or API response.
    
- Inherits from `Controller` or `ControllerBase`.
    

**Example**

```csharp
public class EmployeeController : Controller
{
}
```

---

## Action Method

- Public method inside a controller.
    
- Handles a request and returns a response.
    

```csharp
[HttpGet]
public IActionResult Get()
{
    return Ok();
}
```

---

## Routing

- Maps an incoming URL to a controller action.
    
- Types:
    
    - Conventional Routing
        
    - Attribute Routing
        

### Attribute Routing

```csharp
[Route("api/employees")]
[HttpGet]
public IActionResult Get()
{
    return Ok();
}
```

### Conventional Routing

```csharp
app.MapControllerRoute(
    name: "default",
    pattern: "{controller=Home}/{action=Index}/{id?}");
```

---

## Endpoint

- The final destination that processes an HTTP request.
    

**Example**

```text
GET /api/employees
        │
        ▼
EmployeeController.Get()
```

---

## HTTP Verbs

- **GET** → Retrieve data.
    
- **POST** → Create a new resource.
    
- **PUT** → Update an entire resource.
    
- **PATCH** → Partially update a resource.
    
- **DELETE** → Remove a resource.
    

**Example**

```csharp
[HttpGet]

[HttpPost]

[HttpPut]

[HttpPatch]

[HttpDelete]
```

---

## Benefits of MVC

- Clear separation of concerns.
    
- Easy to maintain and test.
    
- Supports reusable components.
    
- Better code organization.
    
- Flexible routing.
    
- Built-in support for model binding and validation.