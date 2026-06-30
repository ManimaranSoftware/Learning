### Authentication

- Authentication - Verifies the identity of a user.
- Answers - "Who are you?"

---

### Authorization

- Authorization - Determines what an authenticated user can access.
- Answers - "What are you allowed to do?"

---

### API Key

- API Key - Unique key used to authenticate API clients.
- Commonly used for server-to-server communication.

---

### Basic Authentication

- Sends Username and Password encoded using Base64.
- Should always be used with HTTPS.

---

### Bearer Token

- Authentication using an access token.
- Sent in the `Authorization` header.

---

### JWT (JSON Web Token)

- Token-based authentication mechanism.
- Structure - Header, Payload, Signature.
- Stateless authentication.

---

### OAuth 2.0

- Authorization framework for delegated access.
- Allows third-party applications to access resources without sharing passwords.

---

### OpenID Connect (OIDC)

- Authentication layer built on OAuth 2.0.
- Provides user identity information.

---

### Access Token

- Short-lived token used to access protected resources.

---

### Refresh Token

- Used to obtain a new Access Token after expiration.
- Usually longer-lived than an Access Token.

---

### Claims

- Information stored inside a JWT.
- Examples - UserId, Email, Role.

---

### Token Expiration

- Tokens should have a limited lifetime.
- Reduces security risks if a token is compromised.

---

### Benefits

- Secure authentication.
- Stateless APIs.
- Supports Single Sign-On (SSO).
- Supports third-party authentication.

---

### Single Sign-On (SSO)

- Allows users to log in once and access multiple applications.
- Commonly implemented using OAuth 2.0 and OpenID Connect.