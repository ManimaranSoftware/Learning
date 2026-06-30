
### Exception

- Runtime error that interrupts normal program execution.
- Handled using exception handling mechanism.

---

### try

- Contains code that may throw an exception.

---

### catch

- Handles exceptions thrown from the `try` block.
- Multiple `catch` blocks are supported.

---

### finally

- Executes regardless of whether an exception occurs.
- Used for resource cleanup.

---

### throw

- Throws or rethrows an exception.
- Preserves the original stack trace.

---

### throw ex

- Rethrows an exception.
- Resets the original stack trace (generally avoid).

---

### Custom Exception

- User-defined exception.
- Inherits from `Exception`.
- Used for business-specific errors.

---

### Inner Exception

- Contains the original exception that caused the current exception.
- Helps in debugging chained exceptions.

---

### Exception Filter

- Uses `when` keyword to handle exceptions conditionally.

---

### Benefits

- Improves application stability.
- Enables graceful error handling.
- Simplifies debugging and logging.
- Prevents unexpected application crashes.
---
### Commyes pon Exception Types

- `NullReferenceException` - Accessing members of a `null` object.
- `IndexOutOfRangeException` - Invalid array or collection index.
- `ArgumentException` - Invalid method argument.
- `ArgumentNullException` - `null` argument passed where not allowed.
- `InvalidOperationException` - Invalid operation for current object state.
- `DivideByZeroException` - Division by zero.
- `FormatException` - Invalid data format during conversion.
- `FileNotFoundException` - File does not exist.
- `IOException` - General input/output error.
- `SqlException` - SQL Server-related database error.