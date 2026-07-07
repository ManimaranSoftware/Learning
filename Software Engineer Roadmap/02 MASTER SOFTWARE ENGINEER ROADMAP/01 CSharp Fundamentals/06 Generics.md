### Generic

- Enables writing reusable, type-safe code.
- Type specified at compile time.
- Eliminates boxing and unboxing.
- Improves performance and code reusability.

---

### Generic Class

- Class that works with different data types using type parameters.
- Example - `List<T>`, `Dictionary<TKey, TValue>`.

---

### Generic Method

- Method that accepts type parameters.
- Reusable for multiple data types.

---

### Generic Interface

- Interface with type parameters.
- Example - `IEnumerable<T>`, `IList<T>`.

---

### Generic Delegate

- Delegate with type parameters.
- Examples - `Action<T>`, `Func<T>`, `Predicate<T>`.

---

### Generic Constraints

- Restricts the types that can be used.
- Examples:
    - `where T : class`
    - `where T : struct`
    - `where T : new()`
    - `where T : BaseClass`
    - `where T : IInterface`

---

### Type Parameter

- Placeholder representing a data type.
- Common names - `T`, `TKey`, `TValue`, `TResult`.

---

### Benefits

- Type safety.
- Reusable code.
- Better performance.
- Reduces runtime casting errors.
- Eliminates boxing/unboxing for value types.