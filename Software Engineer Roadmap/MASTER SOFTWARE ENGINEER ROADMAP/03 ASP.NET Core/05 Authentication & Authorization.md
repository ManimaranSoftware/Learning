### Authentication

- Authentication - Verifies the identity of a user.
- Answers - "Who are you?"
- Common Methods - JWT, Cookies, OAuth.

---

### Authorization

- Authorization - Determines what an authenticated user can access.
- Answers - "What are you allowed to do?"
- Performed after authentication.

---

### JWT (JSON Web Token)

- JWT - Token-based authentication mechanism.
- Structure - Header, Payload, Signature.
- Commonly used for REST APIs.

---

### Claims

- Claims - Information about the authenticated user.
- Examples - UserId, Name, Email, Role.

---

### Roles

- Roles - Group-based authorization.
- Examples - Admin, Manager, User.

---

### Policies

- Policies - Rule-based authorization.
- More flexible than role-based authorization.

---

### Identity

- ASP.NET Core Identity - Membership system for user authentication and management.
- Features - Login, Registration, Roles, Password Management.

---

### Cookie Authentication

- Stores authentication information in browser cookies.
- Commonly used for MVC applications.

---

### Bearer Authentication

- Uses JWT in the `Authorization` header.
- Commonly used for Web APIs.

---

### OAuth 2.0

- Authorization framework for third-party access.
- Used by Google, Microsoft, GitHub login.

---

### OpenID Connect (OIDC)

- Authentication layer built on OAuth 2.0.
- Provides user identity information.

---

### Benefits

- Secure user authentication.
- Role and policy-based access control.
- Stateless authentication using JWT.
- Supports third-party login providers.