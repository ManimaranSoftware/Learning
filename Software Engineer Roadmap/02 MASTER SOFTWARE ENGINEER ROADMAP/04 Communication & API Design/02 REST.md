### REST

- REST (Representational State Transfer) - Architectural style for designing web APIs.
- Uses HTTP protocol for communication.

---

### Resource

- Resource - Any object or data exposed through an API.
- Identified using a URI.

---

### Endpoint

- Endpoint - URL that provides access to a resource.

---

### Representation

- Representation - Format in which a resource is transferred.
- Common Formats - JSON, XML.

---

### Client-Server

- Client requests resources.
- Server processes requests and returns responses.

---

### Stateless

- Every request contains all information required by the server.
- Server does not maintain client state.

---

### Cacheable

- Responses can be cached to improve performance.

---

### Uniform Interface

- Standard way of interacting with resources.
- Simplifies client-server communication.

---

### Layered System

- Multiple intermediary layers (Gateway, Load Balancer, Proxy) can exist between client and server.

---

### Code on Demand (Optional)

- Server can send executable code to the client.
- Rarely used in REST APIs.

---

### Resource Naming

- Use nouns instead of verbs.
- Example:
    - ✅ `/users`
    - ❌ `/getUsers`

---

### HTTP Methods

- GET - Retrieve resource.
- POST - Create resource.
- PUT - Replace entire resource.
- PATCH - Partially update resource.
- DELETE - Remove resource.

---

### Idempotency

- GET - Idempotent.
- PUT - Idempotent.
- DELETE - Idempotent.
- POST - Not Idempotent.
- PATCH - Generally Not Idempotent.

---

### REST Benefits

- Scalable.
- Stateless.
- Platform independent.
- Easy to maintain.
- Widely supported.

---

### Richardson Maturity Model (Basic)

- Level 0 - Single endpoint.
- Level 1 - Resources.
- Level 2 - Proper HTTP Methods.
- Level 3 - HATEOAS.

_(Just a basic introduction. We'll keep it simple.)_

---
### HATEOAS

- Hypermedia As The Engine Of Application State.
- API responses include links to related actions or resources.
- Represents Level 3 of the Richardson Maturity Model.