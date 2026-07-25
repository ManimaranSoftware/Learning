### Stack

- Stores value types and method call information.
- Fast allocation and deallocation.
- Automatically managed using LIFO (Last In, First Out).

---

### Heap

- Stores reference type objects.
- Memory managed by Garbage Collector (GC).
- Slower than stack allocation.

---

### Value Type

- Stores actual value.
- Usually allocated on stack.
- Copy by value.
- Examples - `int`, `bool`, `double`, `struct`, `enum`.
**Exception:**

- **A value type becomes part of a heap object when it's a field of a class.**

```csharp
class Employee
{
    public int Age;   // int is stored inside the heap object
}
```

---

### Reference Type

- Stores reference to an object.
- Object usually allocated on heap.
- Copy by reference.
- Examples - `class`, `string`, `array`, `delegate`.

**Exception:**

- **The reference (variable) is often stored on the stack if it's a local variable; only the object is on the heap.**

```csharp
Employee emp = new Employee();
```

- `emp` (reference) → Stack
- `new Employee()` (object) → Heap

---

### Boxing

- Converts Value Type → Object (Reference Type).
- Implicit conversion.
- Causes heap allocation.

---

### Unboxing

- Converts Object → Value Type.
- Explicit conversion.
- Invalid cast throws exception.

---

### Garbage Collection (GC)

- Automatically releases memory of unused objects.
- Manages heap memory.
- Helps prevent memory leaks.

---

### IDisposable

- Interface used to release unmanaged resources.
- Implements `Dispose()` method.
- Used with files, database connections, streams, etc.

---

### using

- Automatically calls `Dispose()` after object usage.
- Simplifies resource cleanup.
- Recommended with `IDisposable` objects.

```
using var file = new StreamReader("test.txt");

Console.WriteLine(file.ReadLine());
Console.WriteLine(file.ReadLine());
Console.WriteLine(file.ReadLine());
```

This is perfectly valid. You can use `file` as many times as you want.

The compiler transforms it approximately into:

```
var file = new StreamReader("test.txt");

try
{
    Console.WriteLine(file.ReadLine());
    Console.WriteLine(file.ReadLine());
    Console.WriteLine(file.ReadLine());
}
finally
{
    file.Dispose();   // Happens here
}
```

Notice that `Dispose()` is called **after** all the statements that use `file`.

##### Scope example

```
{
    using var file = new StreamReader("test.txt");

    Console.WriteLine(file.ReadLine()); // ✅
    Console.WriteLine(file.ReadLine()); // ✅
} // <-- Dispose() is called here automatically

Console.WriteLine(file.ReadLine()); // ❌ Compile-time error: file doesn't exist here
```

##### Does `Dispose()` free memory?

Not exactly.

`Dispose()` typically:

- ✅ Closes the file handle.
- ✅ Releases unmanaged resources (OS resources like file handles, sockets, database connections).

The **memory** for the `StreamReader` object is **not** immediately freed. The **Garbage Collector** reclaims that memory later when there are no references to the object.

---

### Destructor (Finalizer)

- Executes before object is garbage collected.
- Used to release unmanaged resources.
- Non-deterministic execution (avoid unless necessary).

---

### Benefits

- Automatic memory management.
- Reduced memory leaks.
- Better application stability.
- Efficient resource cleanup.

