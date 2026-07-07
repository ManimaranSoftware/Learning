
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
### Purpose of Each Block

- **`try`**: Wraps dangerous code that might cause an error.
- **`catch`**: Intercepts, logs, or handles the error so the app does not crash.
- **`finally`**: Guarantees code execution (usually for cleanup like closing files) even if an error occurs.

### Valid Combinations

- `try` + `catch` (Handle errors)
- `try` + `finally` (Clean up resources, let errors bubble up)
- `try` + `catch` + `finally` (Handle errors and clean up)

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
Think of **Inner Exception** as **"the real/root cause of the error."**

### Example

```csharp
try
{
    try
    {
        int number = int.Parse("Mani");
    }
    catch (Exception ex)
    {
        throw new Exception("Failed to process user input.", ex);
    }
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
    Console.WriteLine(ex.InnerException.Message);
}
```

### Output

```
Failed to process user input.The input string 'Mani' was not in a correct format.
```

### What happened?

1. `int.Parse("Mani")` throws the **original exception**.
2. You catch it.
3. You throw a **new exception** with a user-friendly message.
4. The original exception is stored in **`InnerException`**.

```
Original Exception
        │
        ▼
"The input string 'Mani' was not in a correct format."
        │
Stored in
        ▼
InnerException
        │
New Exception
        ▼
"Failed to process user input."
```
### Interview answer

> **InnerException** stores the original exception that caused the current exception. It helps preserve the root cause while allowing us to throw a new, more meaningful exception.

### Memory trick

- **Exception.Message** → "What went wrong now?"
- **InnerException.Message** → "What was the original reason?"
---

### Exception Filter

- Uses `when` keyword to handle exceptions conditionally.
```
catch (Exception ex) when (condition)
{
    // Handles only if condition is true
}
```

```csharp
try
{
    int number = 10;
    int result = number / 0;
}
catch (DivideByZeroException ex) when (DateTime.Now.DayOfWeek == DayOfWeek.Monday)
{
    Console.WriteLine("Handled only on Monday.");
}
```
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