# 10-Second Recall

> **Secrets Manager → Store Secrets → IAM Role → Retrieve Secret → Connect to RDS → Rotation**

---

# 60-Second Revision

**Secrets Manager**

- Fully managed service for securely storing sensitive information.

**Stores**

- Database passwords.
- API keys.
- Tokens.
- Other confidential credentials.

**Benefits**

- Secure storage.
- No hardcoded credentials.
- Automatic secret rotation.
- Easy integration with AWS services.

**Access**

- Applications like Lambda retrieve secrets using an IAM Role.

**Why use it?**

- Improves security and simplifies credential management.

**Project Example**

- Use Secrets Manager to securely retrieve the RDS database password at runtime instead of storing it in code.