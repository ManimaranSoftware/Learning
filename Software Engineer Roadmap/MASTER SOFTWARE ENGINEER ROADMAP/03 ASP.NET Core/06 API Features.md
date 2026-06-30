### REST

- REST - Architectural style for designing web APIs.
- Communication - Uses HTTP protocol.
- Resource-Based - Everything is treated as a resource.

---

### REST Constraints

- Client-Server - Separation of client and server.
- Stateless - Server does not store client state.
- Cacheable - Responses can be cached.
- Uniform Interface - Standardized communication.
- Layered System - Supports multiple intermediary layers.
- Code on Demand - Optional execution of client-side code.

---

### HTTP

- HTTP - Protocol for communication between client and server.
- Request - Sent by client.
- Response - Returned by server.

---

### HTTP Status Codes

- 200 OK - Request successful.
- 201 Created - Resource created successfully.
- 204 No Content - Success with no response body.
- 400 Bad Request - Invalid request.
- 401 Unauthorized - Authentication required.
- 403 Forbidden - Access denied.
- 404 Not Found - Resource not found.
- 405 Method Not Allowed - HTTP method not supported.
- 409 Conflict - Resource conflict.
- 500 Internal Server Error - Server-side error.
- 503 Service Unavailable - Service temporarily unavailable.

---

### Content Negotiation

- Content Negotiation - Determines response format based on client request.
- Common Formats - JSON, XML.

---

### CORS

- CORS (Cross-Origin Resource Sharing) - Controls access to APIs from different origins.
- Purpose - Prevents unauthorized cross-origin requests.

---

### Swagger / OpenAPI

- Swagger - API documentation and testing tool.
- OpenAPI - Standard specification for REST APIs.
- Common Package - Swashbuckle.

---

### API Versioning

- API Versioning - Supports multiple API versions.
- Methods - URL, Query String, Header.

---

### Minimal API

- Minimal API - Lightweight API development with minimal configuration.
- Introduced - .NET 6.

---

### Idempotency

- Idempotency - Multiple identical requests produce the same result.
- Idempotent Methods - GET, PUT, DELETE.
- Non-Idempotent Method - POST.

---

### Health Checks

- Monitors application health.
- Used by load balancers and monitoring tools.
- Common Endpoint - `/health`.
---

### Benefits

- Standardized communication.
- Easy API documentation.
- Better API maintainability.
- Version support.
- Secure cross-origin access.