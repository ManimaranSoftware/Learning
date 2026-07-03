## Model Binding

- Automatically maps HTTP request data to action method parameters or models.
    

**Example**

```csharp
public IActionResult Create([FromBody] Employee employee)
{
    return Ok(employee);
}
```

---

## Model Binding Attributes

### `[FromBody]`

- Reads data from the request body.
    
- Commonly used with POST and PUT requests.
    

```csharp
public IActionResult Create([FromBody] Employee employee)
```

---

### `[FromRoute]`

- Reads values from the URL.
    

```csharp
[HttpGet("{id}")]
public IActionResult Get([FromRoute] int id)
```

**Example URL**

```text
GET /api/employees/1
```

---

### `[FromQuery]`

- Reads values from query string parameters.
    

```csharp
public IActionResult Search([FromQuery] string name)
```

**Example URL**

```text
GET /api/employees?name=Mani
```

---

## Model Validation

- Validates incoming data before processing.
    
- Uses Data Annotation attributes.
    

---

## Data Annotations

### `[Required]`

- Field is mandatory.
    

```csharp
[Required]
public string Name { get; set; }
```

---

### `[StringLength]`

- Limits string length.
    

```csharp
[StringLength(50)]
public string Name { get; set; }
```

---

### `[Range]`

- Restricts numeric values.
    

```csharp
[Range(18, 60)]
public int Age { get; set; }
```

---

### `[EmailAddress]`

- Validates email format.
    

```csharp
[EmailAddress]
public string Email { get; set; }
```

---

### `[Phone]`

- Validates phone number format.
    

```csharp
[Phone]
public string Mobile { get; set; }
```

---

## Complete Model Example

```csharp
public class Employee
{
    [Required]
    public string Name { get; set; }

    [Range(18, 60)]
    public int Age { get; set; }

    [EmailAddress]
    public string Email { get; set; }
}
```

---

## ModelState

- Stores model binding and validation results.
    
- `ModelState.IsValid` checks whether validation succeeded.
    

```csharp
if (!ModelState.IsValid)
{
    return BadRequest(ModelState);
}
```

---

## `[ApiController]`

- Identifies the controller as an API controller.
    
- Enables automatic model validation.
    
- Automatically returns **400 Bad Request** when the model is invalid.
    
- Improves API behavior by enabling Web API conventions.
    

```csharp
[ApiController]
[Route("api/[controller]")]
public class EmployeeController : ControllerBase
{
}
```

---

## Flow

```text
HTTP Request
      ↓
Model Binding
      ↓
Model Validation
      ↓
ModelState.IsValid
      ↓
Valid ? -------- No
  │               │
 Yes              ▼
  │        400 Bad Request
  ▼
Controller Logic
  │
  ▼
Response
```