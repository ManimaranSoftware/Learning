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

---

### Reference Type

- Stores reference to an object.
- Object usually allocated on heap.
- Copy by reference.
- Examples - `class`, `string`, `array`, `delegate`.

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