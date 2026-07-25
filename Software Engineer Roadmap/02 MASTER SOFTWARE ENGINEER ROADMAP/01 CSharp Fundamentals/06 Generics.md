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

# Generic Constraints

- Restrict the types that can be used as generic parameters.
    

|Constraint|Meaning|Example|
|---|---|---|
|`where T : class`|Only reference types|`string`, `Employee`|
|`where T : struct`|Only value types|`int`, `bool`|
|`where T : new()`|Must have a public parameterless constructor|`new T()` is allowed|
|`where T : BaseClass`|Must inherit from a specific base class|`Dog : Animal`|
|`where T : IInterface`|Must implement an interface|`Report : IPrintable`|

## Examples

### `new()`

```csharp
class Factory<T> where T : new()
{
    public T Create() => new T();
}
```

### `BaseClass`

```csharp
class Animal { }
class Dog : Animal { }

class Zoo<T> where T : Animal { }
```

### `IInterface`

```csharp
interface IPrintable { }
class Report : IPrintable { }

class Printer<T> where T : IPrintable { }
```

## Interview Tip

> Generic constraints restrict what types can be used with a generic, enabling compile-time validation and safer code.

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