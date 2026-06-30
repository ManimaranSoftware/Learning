### MVC

- MVC - Design pattern separating application into Model, View and Controller.
- Model - Represents business logic and data.
- View - Displays UI.
- Controller - Handles HTTP requests and returns responses.

---

### Controller

- Controller - Handles incoming HTTP requests.
- Inherits from `Controller` or `ControllerBase`.
- Contains action methods.

---

### Action Method

- Action Method - Public method that handles a request and returns a response.

---

### Routing

- Routing - Maps incoming URL to controller action or endpoint.
- Types - Conventional Routing, Attribute Routing.
- Common Attribute - `[Route]`.

---

### Endpoint

- Endpoint - Final destination that processes an HTTP request.

---

### HTTP Verbs

- GET - Retrieve data.
- POST - Create new resource.
- PUT - Update entire resource.
- PATCH - Partially update resource.
- DELETE - Remove resource.

---

### Model

- Model - Represents application data and business rules.

---

### Model Binding

- Model Binding - Automatically maps HTTP request data to action parameters or models.

---

### Model Validation

- Model Validation - Validates incoming data before processing.
- Uses Data Annotation attributes.

---

### Data Annotations

- `[Required]` - Field is mandatory.
- `[StringLength]` - Limits string length.
- `[Range]` - Restricts numeric range.
- `[EmailAddress]` - Validates email format.
- `[Phone]` - Validates phone number.

---

### Action Result

- IActionResult - Returns different HTTP responses.
- ActionResult`<T>` - Returns strongly typed response with status code.
- Common Results - `Ok()`, `Created()`, `BadRequest()`, `NotFound()`, `NoContent()`, `Unauthorized()`.

---

### ModelState

- ModelState - Stores model binding and validation results.
- `ModelState.IsValid` - Checks whether validation passed.

---

### Benefits

- Clear separation of concerns.
- Automatic model binding.
- Built-in validation.
- Flexible response handling.
- Easy routing.