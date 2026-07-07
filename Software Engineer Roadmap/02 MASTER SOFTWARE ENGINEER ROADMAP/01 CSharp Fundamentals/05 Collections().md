### Array

- Fixed size collection.
- Stores same data type.
- Fast index-based access.
- Size cannot be changed after creation.

---

### List `<T>` 

- Dynamic size collection.
- Generic and type-safe.
- Supports add, remove and search operations.
- Most commonly used collection.

---

### Dictionary<TKey, TValue>

- Stores key-value pairs.
- Keys must be unique.
- Fast lookup using key.
- Generic and type-safe.

---

### Hashtable

- Stores key-value pairs.
- Non-generic (stores `object`).
- Requires boxing/unboxing for value types.
- Slower than `Dictionary`.

---

### HashSet`<T>`

- Stores unique elements only.
- No duplicate values.
- Unordered collection.
- Fast lookup.

---

### Queue`<T>`

- FIFO (First In, First Out).
- Operations - `Enqueue()`, `Dequeue()`, `Peek()`.
- Used in task scheduling, message queues.

---

### Stack`<T>`

- LIFO (Last In, First Out).
- Operations - `Push()`, `Pop()`, `Peek()`.
- Used in undo operations, recursion.

---

### LinkedList`<T>`

- Doubly linked list.
- Fast insertion and deletion.
- Slower random access than `List<T>`.

---

### Concurrent Collections

- Thread-safe collections.
- Used in multi-threaded applications.
- Examples - `ConcurrentDictionary`, `ConcurrentQueue`, `ConcurrentBag`.

---

### IEnumerable`<T>`

- Supports forward-only iteration.
- Deferred execution.
- Read-only interface.
- Suitable for in-memory collections.

---

### ICollection`<T>`

- Supports add, remove, count.
- Base interface for generic collections.

---

### IList`<T>`

- Ordered collection.
- Supports index-based access.
- Inherits `ICollection<T>`.

---

### IReadOnlyCollection`<T>`

- Read-only collection.
- Exposes `Count`.
- Prevents modification.

---

### IReadOnlyList`<T>`

- Read-only list.
- Supports index access.
- Prevents modification.

---

### Benefits

- Generic collections are type-safe.
- Better performance than non-generic collections.
- Rich built-in methods.
- Easy integration with LINQ.