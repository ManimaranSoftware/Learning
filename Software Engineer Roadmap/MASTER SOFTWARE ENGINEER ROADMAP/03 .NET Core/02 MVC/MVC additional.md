Session & Cookies

- Session - Server-side user data storage
- Cookie - Client-side browser storage
- Session State - Per-user temporary data
- Persistent Cookie - Survives browser restart
- Session Timeout - Automatic expiration

Authentication & Authorization

- Authentication - Verify user identity
- Authorization - Verify permissions
- Cookie Authentication - Browser-based auth
- Claims - User information collection
- Roles - Permission grouping
- Policy-Based Authorization - Rule-driven access control
- [Authorize] - Access restriction attribute

Middleware vs Filters

- Middleware - Entire HTTP pipeline
- Filters - MVC pipeline only
- Middleware Order - Execution sequence matters
- UseAuthentication() - User validation middleware
- UseAuthorization() - Permission middleware
- Exception Middleware - Global error handling
- Logging Middleware - Request/Response logging

State Management

- Session - Server-side state
- Cookies - Client-side state
- TempData - One-request state
- Query String - URL-based state
- Hidden Fields - Form-based state

View Components

- View Component - Reusable UI + Logic unit
- Similar to Partial View - But supports business logic
- Independent Rendering - Separate execution pipeline