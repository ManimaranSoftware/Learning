### Thread

- Smallest unit of execution.
- Managed by OS.
- Expensive to create and switch.

---

### Process

- Independent running application.
- Contains one or more threads.
- Own memory space.

---

### Task

- Represents an asynchronous operation.
- Managed by .NET Thread Pool.
- Lightweight compared to Thread.
- Recommended for async programming.

---

### async

- Marks a method as asynchronous.
- Usually used with `await`.
- Method typically returns `Task` or `Task<T>`.

---

### await

- Waits asynchronously for a task to complete.
- Does not block the calling thread.
- Improves responsiveness.

---

### Thread Pool

- Pool of reusable threads managed by .NET.
- Reduces thread creation overhead.
- Used internally by `Task`.

---

### Parallel Programming

- Executes multiple operations simultaneously.
- Uses multiple threads.
- Example - `Parallel.For()`, `Parallel.ForEach()`.

---

### Task.WhenAll()

- Executes multiple tasks concurrently.
- Waits for all tasks to complete.

---

### Task.WhenAny()

- Returns when the first task completes.
- Does not wait for remaining tasks.

---

### CancellationToken

- Cancels long-running asynchronous operations.
- Supports cooperative cancellation.

---

### ConfigureAwait(false)

- Prevents capturing synchronization context.
- Improves performance in library and backend code.
- Commonly used in ASP.NET Core libraries.

---

### Deadlock

- Two or more threads wait indefinitely for each other.
- Can occur due to improper async usage or locking.

---

### Lock

- Prevents multiple threads from accessing shared resources simultaneously.
- Ensures thread safety.

---

### Race Condition

- Multiple threads modify shared data simultaneously.
- Leads to unpredictable results.

---

### Thread Safety

- Ensures code behaves correctly when accessed by multiple threads.

---

### Benefits

- Improves application responsiveness.
- Better resource utilization.
- Supports scalable applications.
- Efficient handling of I/O-bound operations.