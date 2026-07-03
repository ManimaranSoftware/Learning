# Multithreading & Async Programming

---

## Thread

- Smallest unit of execution.
    
- Managed by the OS.
    
- Expensive to create and switch.
    

```csharp
Thread thread = new Thread(() =>
{
    Console.WriteLine("Thread Started");
});

thread.Start();
```

---

## Process

- Independent running application.
    
- Contains one or more threads.
    
- Has its own memory space.
    

**Example**

```text
Visual Studio
├── Thread 1 (UI)
├── Thread 2
└── Thread 3
```

---

## Task

- Represents an asynchronous operation.
    
- Managed by the .NET Thread Pool.
    
- Lightweight compared to `Thread`.
    
- Recommended for asynchronous programming.
    

```csharp
Task.Run(() => Console.WriteLine("Task Running"));
```

---

## async

- Marks a method as asynchronous.
    
- Usually used with `await`.
    
- Returns `Task` or `Task<T>`.
    

```csharp
async Task GetData()
{
    await Task.Delay(1000);
}
```

---

## await

- Waits asynchronously for a task to complete.
    
- Does **not** block the calling thread.
    

```csharp
await Task.Delay(1000);

Console.WriteLine("Completed");
```

---

## Thread Pool

- Pool of reusable threads managed by .NET.
    
- Reduces thread creation overhead.
    
- Used internally by `Task`.
    

```csharp
Task.Run(() => Console.WriteLine("Uses Thread Pool"));
```

---

## Parallel Programming

- Executes multiple operations simultaneously.
    
- Uses multiple threads.
    
- Suitable for CPU-bound work.
    

```csharp
Parallel.For(1, 5, i =>
{
    Console.WriteLine(i);
});
```

```csharp
Task<string> task1 = Method1();
Task<string> task2 = Method2();

var t1 = await task1;
var t2 = await task2;
```

```csharp
var results = await Task.WhenAll(
    Method1(),
    Method2()
);

var t1 = results[0];
var t2 = results[1];
```
---

## `Task.WhenAll()`

- Executes multiple tasks concurrently.
    
- Waits for **all** tasks to complete.
    

```csharp
await Task.WhenAll(task1, task2, task3);
```

---

## `Task.WhenAny()`

- Returns when the **first** task completes.
    
- Remaining tasks continue running.
    

```csharp
Task first = await Task.WhenAny(task1, task2);
```

---

## `CancellationToken`

- Cancels long-running asynchronous operations.
    
- Supports cooperative cancellation.
    

```csharp
CancellationTokenSource cts = new();

await Task.Delay(5000, cts.Token);

cts.Cancel();
```

---

## `ConfigureAwait(false)`

- Prevents capturing the synchronization context.
    
- Improves performance in library and backend code.
    
- Commonly used in reusable libraries.
    

```csharp
await Task.Delay(1000).ConfigureAwait(false);
```

---

## Deadlock

- Two or more threads wait indefinitely for each other.
    
- Often caused by improper locking or blocking async code.
    

```text
Thread A → Waiting for Thread B
Thread B → Waiting for Thread A
```

---

## Lock

- Prevents multiple threads from accessing shared resources simultaneously.
    
- Ensures thread safety.
    

```csharp
lock (_lock)
{
    count++;
}
```

---

## Race Condition

- Multiple threads modify shared data simultaneously.
    
- Leads to unpredictable results.
    

```csharp
count++;   // Not thread-safe
```

**Solution**

```csharp
lock (_lock)
{
    count++;
}
```

---

## Thread Safety

- Ensures code behaves correctly when accessed by multiple threads.
    

**Example**

```csharp
lock (_lock)
{
    balance += 100;
}
```

---

## Benefits

- Improves application responsiveness.
    
- Better resource utilization.
    
- Supports scalable applications.
    
- Efficient for I/O-bound operations.
    

---

## Common Interview Comparisons

- `Thread` vs `Task`
    
- `Thread` vs `Process`
    
- `async` vs `await`
    
- `Task.WhenAll()` vs `Task.WhenAny()`
    
- `Lock` vs Race Condition
    
- Deadlock vs Race Condition
    
- `I/O-bound` vs `CPU-bound`
    

---

## Memory Tricks

### Thread vs Task

```text
Thread = Actual worker
Task = Work assigned to a worker
```

### async vs await

```text
async = Method can run asynchronously
await = Wait without blocking
```

### `Task.WhenAll()` vs `Task.WhenAny()`

```text
WhenAll() → Wait for ALL
WhenAny() → Wait for FIRST
```

### Race Condition vs Lock

```text
Race Condition → Multiple threads modify data together

Lock → Only one thread can modify data at a time
```