### API Security

- API Security - Protecting APIs from unauthorized access and attacks.

---

### HTTPS

- Encrypts data between client and server.
- Prevents eavesdropping and data tampering.

---

### Authentication

- Verifies user identity before granting access.

---

### Authorization

- Controls what an authenticated user can access.

---

### API Key

- Used to identify and authenticate API clients.
- Should be kept confidential.

---

### JWT Validation

- Validate Signature, Expiration and Issuer before accepting a token.

---

### Input Validation

- Validate all client inputs.
- Prevent invalid or malicious data.

---

### SQL Injection

- Attack where malicious SQL is injected into queries.
- Prevent using Parameterized Queries or ORM.

---

### Cross-Site Scripting (XSS)

- Injects malicious scripts into web pages.
- Prevent by validating and encoding user input.

---

### Cross-Site Request Forgery (CSRF)

- Tricks authenticated users into sending unwanted requests.
- Protect using Anti-Forgery Tokens.
- Mainly applicable to cookie-based authentication.

---

### CORS

- Restricts which origins can access an API.
- Configure only trusted domains.

---

### Rate Limiting

- Limits the number of requests from a client.
- Helps prevent abuse and DoS attacks.

---

### Secrets Management

- Never hardcode secrets.
- Store secrets securely (Environment Variables, Secret Manager, Azure Key Vault, AWS Secrets Manager).

---

### Logging & Monitoring

- Log authentication failures and suspicious activities.
- Monitor APIs for unusual traffic patterns.

---

### Principle of Least Privilege

- Grant only the minimum permissions required.
- Reduces security risks.

---

### Benefits

- Protects sensitive data.
- Prevents common attacks.
- Improves API reliability.
- Ensures secure communication.

---

## Small improvement 💡

Let's also add:

### OWASP API Security

- Industry-standard guidelines for securing APIs.
- Covers common API security risks and best practices.

_(Just a basic note. No need to dive into the Top 10 yet.)_

---

## I think **CSRF** should have a small note:

- **JWT/Bearer Token APIs** → Usually **not vulnerable** to CSRF because browsers don't automatically send bearer tokens.
- **Cookie-based authentication** → **Needs CSRF protection**.