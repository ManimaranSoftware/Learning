### API Design

- API Design - Process of designing clear, consistent and maintainable APIs.

---

### Resource-Oriented Design

- Design APIs around resources (nouns), not actions (verbs).

---

### Naming Convention

- Use plural nouns for resources.
- Examples - `/users`, `/orders`, `/products`.

---

### URI Design

- Keep URIs simple and meaningful.
- Avoid verbs and unnecessary nesting.

---

### Versioning

- Version APIs to support backward compatibility.
- Common Formats - URL, Header, Query String.

---

### Request Validation

- Validate all incoming requests.
- Return appropriate error responses for invalid data.

---

### Response Structure

- Keep response format consistent across all APIs.
- Return meaningful data and status codes.

---

### Pagination

- Return data in smaller chunks.
- Common Parameters - `page`, `pageSize`, `limit`, `offset`.

---

### Filtering

- Allow clients to filter results.
- Example - `/users?city=Bangalore`

---

### Sorting

- Allow sorting using query parameters.
- Example - `/users?sort=name`

---

### Searching

- Support keyword-based search.
- Example - `/products?search=laptop`

---

### Error Handling

- Return meaningful error messages.
- Use appropriate HTTP status codes.

---

### Idempotency

- Design APIs considering idempotent operations.
- Prevent duplicate processing where required.

---

### API Naming Best Practices

- Use nouns, not verbs.
- Use lowercase URLs.
- Use hyphens instead of underscores.
- Keep URLs short and meaningful.

---

### Benefits

- Easy to understand.
- Consistent API structure.
- Better maintainability.
- Easier client integration.

---

### API Response Wrapper

- Standardizes API responses.
- Common fields - `success`, `message`, `data`, `errors`.

_(Many companies use a standard response format, so it's good to know the concept.)_