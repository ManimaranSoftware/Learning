## REST
- Resource-Based Architecture
- Stateless
- Client-Server
- Uniform Interface
- Cacheable
- Uses HTTP Protocol

> [!tip]
> **Memory Tip:** REST = Resources over HTTP

---

## HTTP Methods
- `GET` → Read
- `POST` → Create
- `PUT` → Full Update
- `PATCH` → Partial Update
- `DELETE` → Delete

> [!tip]
> **Memory Tip:** CRUD = GET → POST → PUT/PATCH → DELETE

---

## HTTP Status Codes
- `200 OK` → Success
- `201 Created` → Resource Created
- `204 No Content` → Success, No Response Body
- `400 Bad Request` → Invalid Request
- `401 Unauthorized` → Authentication Required
- `403 Forbidden` → No Permission
- `404 Not Found` → Resource Not Found
- `409 Conflict` → Duplicate/Conflict
- `500 Internal Server Error` → Server Failure

---

## API Design
- Resource-based URLs
- Use Nouns, Not Verbs
- Consistent Naming
- DTOs for Request/Response
- Keep APIs Stateless

---

## Model Validation
- Data Annotations
- `ModelState.IsValid`
- Return `400 BadRequest()` for Invalid Model

---

## Action Results
- `Ok()`
- `CreatedAtAction()`
- `BadRequest()`
- `Unauthorized()`
- `Forbid()`
- `NotFound()`
- `NoContent()`

> [!tip]
> **Memory Tip:** Return the most appropriate HTTP Status Code

---

## DTO (Data Transfer Object)
- Hides Entity Structure
- Request/Response Model
- Improves Security
- Reduces Payload

---

## API Versioning
- URL Versioning (`/api/v1/products`)
- Header Versioning
- Query String Versioning

---

## Pagination
- `Skip()`
- `Take()`
- `PageNumber`
- `PageSize`
- Reduces Response Size

---

## Filtering & Sorting
- Query Parameters
- `OrderBy()`
- `Where()`
- Search Keyword

---

## Swagger
- OpenAPI Documentation
- API Testing
- Interactive UI
- Auto Documentation

---

## File Upload
- `IFormFile`
- Multipart/Form-Data
- Validate File Size & Type
- Store Locally / Cloud (`S3`, Azure Blob)

---

## API Security
- JWT Authentication
- HTTPS
- Input Validation
- Prevent SQL Injection
- Prevent XSS
- Prevent CSRF (Cookies)

---

## Best Practices
- Stateless APIs
- Proper Status Codes
- Global Exception Handling
- Logging
- Validation
- Versioning
- DTOs
- Async APIs

---

## Interview Traps
- `PUT` vs `PATCH`
- `401` vs `403`
- `200` vs `204`
- Entity vs DTO
- Authentication vs Authorization
- `GET` vs `POST`
- REST vs SOAP
- Stateless vs Stateful

---

## 30-Second Revision Formula

REST → HTTP Methods → Status Codes → API Design → Validation → Action Results → DTO → Versioning → Pagination → Filtering → Swagger → File Upload → Security → Best Practices