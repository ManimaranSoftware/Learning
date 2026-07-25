## Authentication vs Authorization
- Authentication → Verify Identity
- Authorization → Verify Permissions
- Authentication First
- Authorization Next

> [!tip]
> **Memory Tip:** Authentication = Who are you? | Authorization = What can you access?

---

## JWT (JSON Web Token)
- Stateless Authentication
- Header
- Payload (Claims)
- Signature
- Sent in `Authorization` Header
- `Bearer <token>`

> [!tip]
> **Memory Tip:** JWT = Header + Payload + Signature

---

## OAuth 2.0
- Authorization Framework
- Third-Party Login
- Access Token
- Refresh Token
- Used by Google, Microsoft, GitHub

---

## OpenID Connect (OIDC)
- Built on OAuth 2.0
- Provides User Identity
- Returns ID Token
- Used for Login

---

## Claims-Based Authentication
- Claims → User Information
- Examples:
  - UserId
  - Email
  - Role
  - Department
- Stored inside JWT Payload

---

## Role-Based Authorization
- Roles:
  - Admin
  - Manager
  - User
- `[Authorize(Roles = "...")]`

---

## Policy-Based Authorization
- Rule-Based Authorization
- Uses Policies
- Supports Custom Requirements
- More Flexible than Roles

---

## HTTPS
- Encrypts Communication
- Uses SSL/TLS
- Prevents Data Interception
- Required for Production APIs

---

## Encryption vs Hashing
- Encryption → Reversible
- Hashing → One-Way
- Encryption → Sensitive Data
- Hashing → Passwords

> [!tip]
> **Memory Tip:** Encrypt = Hide | Hash = Fingerprint

---

## Password Security
- Never Store Plain Text Passwords
- Use Salted Hash
- `BCrypt` (Common Choice)
- Strong Password Policy

---

## OWASP Top 10 (Important)
- SQL Injection
- Cross-Site Scripting (XSS)
- Cross-Site Request Forgery (CSRF)
- Broken Authentication
- Security Misconfiguration
- Sensitive Data Exposure

---

## SQL Injection Prevention
- Parameterized Queries
- ORM (`EF Core`)
- Input Validation
- Never Concatenate SQL Strings

---

## XSS Prevention
- Validate User Input
- Encode Output
- Avoid Rendering Raw HTML
- Content Security Policy (CSP)

---

## CSRF Prevention
- Anti-Forgery Token
- `SameSite` Cookies
- Validate Requests
- Mostly Cookie-Based Authentication

---

## CORS
- Cross-Origin Resource Sharing
- Restricts Cross-Domain Requests
- Configure Trusted Origins
- `AddCors()`
- `UseCors()`

---

## Secrets Management
- Don't Hardcode Secrets
- Environment Variables
- AWS Secrets Manager
- Azure Key Vault

---

## Secure API Best Practices
- HTTPS Everywhere
- JWT Authentication
- Input Validation
- Least Privilege
- Rate Limiting
- Logging & Monitoring
- Token Expiration
- Secret Rotation

---

## Interview Traps
- Authentication vs Authorization
- OAuth vs OpenID Connect
- Encryption vs Hashing
- JWT vs Session Authentication
- Role-Based vs Policy-Based Authorization
- SQL Injection vs XSS vs CSRF
- Access Token vs Refresh Token
- HTTPS vs HTTP
- Claims vs Roles
- CORS vs CSRF

---

## 30-Second Revision Formula

Authentication → Authorization → JWT → OAuth → OIDC → Claims → Roles → Policies → HTTPS → Encryption → Password Security → OWASP → SQL Injection → XSS → CSRF → CORS → Secrets → Secure APIs