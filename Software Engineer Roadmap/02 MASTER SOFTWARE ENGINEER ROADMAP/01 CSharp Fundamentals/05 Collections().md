## Array

- Fixed size collection.
- Stores same data type.
- Fast index-based access (`O(1)`).
- Size cannot be changed after creation.
- **Syntax:**
  ```csharp
  int[] numbers = { 10, 20, 30 };
  ```
- **When to use:** When the number of elements is fixed and high performance is required.

---

## `List<T>`

- Dynamic size collection.
- Generic and type-safe.
- Supports add, remove and search operations.
- Most commonly used collection.
- **Syntax:**
  ```csharp
  List<int> numbers = new List<int>();

  numbers.Add(10);
  numbers.Add(20);
  numbers.Remove(10);
  ```
- **When to use:** Default choice when collection size changes frequently.

---

## `ArrayList`

- Dynamic size collection.
- Non-generic (stores elements as `object`).
- Can store different data types in the same collection.
- Requires casting when retrieving values.
- Causes boxing/unboxing for value types (`int`, `bool`, etc.).
- Slower than `List<T>` due to casting and boxing.
- **Syntax:**
  ```csharp
  using System.Collections;

  ArrayList items = new ArrayList();

  items.Add(10);
  items.Add("Hello");
  items.Add(true);

  int number = (int)items[0];
  ```
- **When to use:** Mainly for maintaining legacy .NET Framework applications. Prefer `List<T>` in modern C#.

---

## `Dictionary<TKey, TValue>`

- Stores key-value pairs.
- Keys must be unique.
- Fast lookup using key (`O(1)` average).
- Generic and type-safe.
- **Syntax:**
  ```csharp
  Dictionary<int, string> employees = new Dictionary<int, string>();

  employees.Add(1, "Mani");
  employees.Add(2, "Maran");

  Console.WriteLine(employees[1]);
  ```
- **When to use:** Need fast lookup using a unique key (EmployeeId, Email, UserId).

---

## Hashtable

- Stores key-value pairs.
- Non-generic (stores `object`).
- Requires boxing/unboxing for value types.
- Slower than `Dictionary`.
- **Syntax:**
  ```csharp
  Hashtable table = new Hashtable();

  table.Add(1, "Mani");
  table.Add(2, "Maran");
  ```
- **When to use:** Mainly legacy .NET Framework applications. Prefer `Dictionary<TKey, TValue>` in new projects.


### Why is `Dictionary<TKey, TValue>` better?

1. **Generic**
    - `Dictionary<int, string>`
    - Compile-time type safety
2. **No boxing/unboxing**

```
Hashtable table = new Hashtable();
table.Add(1, "Mani");   // key is boxed
```

With `Dictionary`:

```
Dictionary<int, string> dict = new();
dict.Add(1, "Mani");    // no boxing
```

3. **Better performance**
4. **Compile-time type checking**

how dictionary is diff from hashtable?
The surprising answer is:

> **`Dictionary<TKey, TValue>` also uses a hash table internally.**

So the **hashing algorithm is basically the same**. 
The main differences are **type safety, performance, and implementation**, not the hashing concept.


---

## `HashSet<T>`

- Stores unique elements only.
- No duplicate values.
- Unordered collection.
- Fast lookup (`O(1)` average).
- **Syntax:**
  ```csharp
  HashSet<int> numbers = new HashSet<int>();

  numbers.Add(10);
  numbers.Add(20);
  numbers.Add(10); // Ignored
  ```
- **When to use:** Remove duplicates or quickly check if an item exists.

---

## `Queue<T>`

- FIFO (First In, First Out).
- Operations - `Enqueue()`, `Dequeue()`, `Peek()`.
- Fast insertion and removal.
- **Syntax:**
  ```csharp
  Queue<string> queue = new Queue<string>();

  queue.Enqueue("A");
  queue.Enqueue("B");

  queue.Dequeue();
  queue.Peek();
  ```
- **When to use:** Task scheduling, printer queue, message processing.

---

## `Stack<T>`

- LIFO (Last In, First Out).
- Operations - `Push()`, `Pop()`, `Peek()`.
- Fast insertion and removal.
- **Syntax:**
  ```csharp
  Stack<int> stack = new Stack<int>();

  stack.Push(10);
  stack.Push(20);

  stack.Pop();
  stack.Peek();
  ```
- **When to use:** Undo functionality, browser history, recursion.

---

## `LinkedList<T>`

- Doubly linked list.
- Fast insertion and deletion.
- Sequential access.
- Slower random access than `List<T>`.
- **Syntax:**
  ```csharp
  LinkedList<int> list = new LinkedList<int>();

  list.AddLast(10);
  list.AddLast(20);
  list.AddFirst(5);
  ```
- **When to use:** Frequent insertions/deletions in the middle of the collection.

---

## Concurrent Collections

- Thread-safe collections.
- Used in multi-threaded applications.
- No manual locking required.
- Examples:
  - `ConcurrentDictionary<TKey, TValue>`
  - `ConcurrentQueue<T>`
  - `ConcurrentStack<T>`
  - `ConcurrentBag<T>`
- **Syntax:**
  ```csharp
  ConcurrentDictionary<int, string> dict =
      new ConcurrentDictionary<int, string>();

  dict.TryAdd(1, "Mani");
  ```
- **When to use:** Multiple threads read/write the same collection.

---

## `IEnumerable<T>`

- Supports forward-only iteration.
- Read-only interface.
- Deferred execution with LINQ.
- Cannot add or remove items.
- **Syntax:**
  ```csharp
  IEnumerable<int> numbers = new List<int> { 1, 2, 3 };
  ```
- **When to use:** Only need to iterate over a collection.

---

## `ICollection<T>`

- Supports Add, Remove and Count.
- Base interface for generic collections.
- No index-based access.
- **Syntax:**
  ```csharp
  ICollection<int> numbers = new List<int>();

  numbers.Add(10);
  numbers.Remove(10);
  ```
- **When to use:** Need basic collection operations without indexing.

---

## `IList<T>`

- Ordered collection.
- Supports index-based access.
- Supports add, remove and update.
- Inherits `ICollection<T>`.
- **Syntax:**
  ```csharp
  IList<int> numbers = new List<int>();

  numbers.Add(10);
  Console.WriteLine(numbers[0]);
  ```
- **When to use:** Need index access and modification.

---

## `IReadOnlyCollection<T>`

- Read-only collection.
- Exposes `Count`.
- Prevents modification.
- **Syntax:**
  ```csharp
  IReadOnlyCollection<int> numbers =
      new List<int> { 1, 2, 3 };
  ```
- **When to use:** Expose collection without allowing add/remove.

---

## `IReadOnlyList<T>`

- Read-only list.
- Supports index access.
- Prevents modification.
- Inherits `IReadOnlyCollection<T>`.
- **Syntax:**
  ```csharp
  IReadOnlyList<int> numbers =
      new List<int> { 10, 20, 30 };

  Console.WriteLine(numbers[0]);
  ```
- **When to use:** Need index access but want to prevent modifications.

---

## Benefits

- Generic collections are type-safe.
- Better performance than non-generic collections.
- Rich built-in methods.
- Easy integration with LINQ.
- Prefer interfaces (`IEnumerable<T>`, `ICollection<T>`, `IList<T>`) over concrete implementations for loose coupling.

---

## Interview Quick Selection

| Requirement                 | Collection                 |
| --------------------------- | -------------------------- |
| Fixed size                  | Array                      |
| Dynamic collection          | `List<T>`                  |
| Key-Value lookup            | `Dictionary<TKey, TValue>` |
| Legacy key-value            | Hashtable                  |
| Unique values               | `HashSet<T>`               |
| FIFO                        | `Queue<T>`                 |
| LIFO                        | `Stack<T>`                 |
| Frequent insert/delete      | `LinkedList<T>`            |
| Multi-threaded              | Concurrent Collections     |
| Read-only iteration         | `IEnumerable<T>`           |
| Basic collection operations | `ICollection<T>`           |
| Index-based access          | `IList<T>`                 |
| Read-only collection        | `IReadOnlyCollection<T>`   |
| Read-only list with index   | `IReadOnlyList<T>`         |


---
# Collection Interfaces vs Classes

## Key Idea

- **Interface (`I...`)** → Defines **what operations are available** (contract).
    
- **Class** → Provides the **implementation** and may include additional methods.
    

---

## Common Collection Interfaces

|Interface|Implementation|Purpose|
|---|---|---|
|`IEnumerable<T>`|`List<T>`, `Array`, etc.|Only iteration (`foreach`)|
|`ICollection<T>`|`List<T>`, `HashSet<T>`|Basic collection operations (`Add`, `Remove`, `Count`)|
|`IList<T>`|`List<T>`|Ordered collection with indexing|
|`IReadOnlyCollection<T>`|`List<T>`|Read-only access with `Count`|
|`IReadOnlyList<T>`|`List<T>`|Read-only indexed access|
|`IDictionary<TKey, TValue>`|`Dictionary<TKey, TValue>`|Key-value operations|
|`IReadOnlyDictionary<TKey, TValue>`|`Dictionary<TKey, TValue>`|Read-only key-value access|

---

## Example 1: `IList<T>` vs `List<T>`

```csharp
List<int> list1 = new List<int>();

list1.Add(10);
list1.Sort();          // ✅ Available
list1.BinarySearch(10);// ✅ Available
```

```csharp
IList<int> list2 = new List<int>();

list2.Add(10);
// list2.Sort();         // ❌ Not available
// list2.BinarySearch(); // ❌ Not available
```

> **Note:** The object is still a `List<int>`, but the reference type (`IList<int>`) exposes only the interface members.

---

## Example 2: `IReadOnlyList<T>`

```csharp
IReadOnlyList<int> numbers = new List<int> { 10, 20, 30 };

Console.WriteLine(numbers[0]); // ✅ Read

// numbers.Add(40);            // ❌ Not allowed
// numbers.Remove(10);         // ❌ Not allowed
```

> **Note:** `IReadOnlyList<T>` allows reading but prevents modification through that reference.

---

## Interview Tip

- Use **`IEnumerable<T>`** → Only iterate.
    
- Use **`IReadOnlyList<T>`** → Read-only access.
    
- Use **`IList<T>`** → Read and modify.
    
- Use **`List<T>`** → Need `List<T>`-specific methods like `Sort()`, `BinarySearch()`, `Find()`, etc.