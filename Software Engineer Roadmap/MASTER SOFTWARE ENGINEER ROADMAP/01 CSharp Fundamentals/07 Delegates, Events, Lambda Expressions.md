# Delegates

### Delegate

- Type-safe function pointer.
- Holds reference to one or more methods.
- Enables passing methods as parameters.
- Used for callbacks and event handling.

---

### Multicast Delegate

- Holds references to multiple methods.
- Invokes all methods in sequence.
- Created using `+` or `+=`.

---

### Anonymous Method

- Method without a name.
- Declared using `delegate` keyword.
- Commonly replaced by lambda expressions.

---

### Action

- Built-in generic delegate.
- Returns `void`.
- Accepts 0 to 16 input parameters.

---

### Func

- Built-in generic delegate.
- Returns a value.
- Last type parameter represents return type.

---

### Predicate

- Built-in generic delegate.
- Accepts one parameter.
- Always returns `bool`.
- Commonly used for filtering.

---

# Events 

### Event

- Mechanism for notifying subscribers when an action occurs.
- Based on delegates.
- Supports Publisher-Subscriber pattern.
- Can only be raised by the declaring class.

---

### EventHandler

- Built-in delegate for events.
- Standard event pattern in .NET.
- Supports sender and event arguments.

---

### EventArgs

- Base class for passing event data.
- Can be inherited to create custom event data.

---

# Lambda Expressions 

### Lambda Expression

- Anonymous function using `=>` operator.
- Shorter alternative to anonymous methods.
- Commonly used with LINQ and delegates.

---

### Expression Lambda

- Contains a single expression.
- Returns value automatically.

---

### Statement Lambda

- Contains multiple statements.
- Uses `{ }` block.
- Can include loops and conditions.

---

### Closure

- Lambda can access variables from its enclosing scope.
- Variables remain available even after the outer method exits.

---

### Benefits

- Cleaner and concise code.
- Better readability.
- Strong integration with LINQ.
- Simplifies delegate implementation.
- Widely used in modern C#.