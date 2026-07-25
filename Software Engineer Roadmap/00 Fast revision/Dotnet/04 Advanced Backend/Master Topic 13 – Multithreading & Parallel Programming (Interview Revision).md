
## Process vs Thread
- Process → Independent Program
- Thread → Smallest Unit of Execution
- One Process can have Multiple Threads
- Threads Share Process Memory

> [!tip]
> **Memory Tip:** Process = House | Thread = Family Members

---

## Multithreading
- Concurrent Execution
- Improves Responsiveness
- Better Resource Utilization
- Shared Memory

---

## Task Parallel Library (TPL)
- `Task`
- `Task<T>`
- `Task.Run()`
- `Task.WhenAll()`
- `Task.WhenAny()`

---

## Async vs Multithreading
- `async/await` → Non-Blocking I/O
- Thread → CPU Execution
- Async ≠ New Thread
- `Task` may or may not use another Thread

> [!tip]
> **Memory Tip:** Async = Waiting Efficiently | Thread = Doing Work

---

## Synchronization
- `lock`
- `Monitor`
- `Mutex`
- `SemaphoreSlim`
- `Interlocked`

---

## Deadlock
- Threads Waiting Forever
- Lock Ordering Issues
- Avoid Nested Locks
- Prefer `async/await`

---

## Race Condition
- Multiple Threads Modify Same Data
- Causes Inconsistent Results
- Prevent using Synchronization

---

## Thread-Safe Collections
- `ConcurrentDictionary<TKey, TValue>`
- `ConcurrentQueue<T>`
- `ConcurrentBag<T>`
- `BlockingCollection<T>`

---

## Cancellation
- `CancellationToken`
- Cooperative Cancellation
- Graceful Shutdown

---

## Interview Traps
- Process vs Thread
- Task vs Thread
- Async vs Parallel
- `lock` vs `Monitor`
- Deadlock vs Race Condition
- `Task.WhenAll()` vs `Task.WhenAny()`

---

## 30-Second Revision Formula

Process → Thread → TPL → Async → Synchronization → Deadlock → Race Condition → Concurrent Collections → Cancellation