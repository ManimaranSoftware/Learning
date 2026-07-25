

## Performance Basics
- Reduce Response Time
- Increase Throughput
- Optimize Resource Usage
- Improve Scalability

> [!tip]
> **Memory Tip:** Performance = Faster + Efficient + Scalable

---

## Application Performance
- Write Efficient Code
- Avoid Unnecessary Loops
- Reduce Object Creation
- Prefer Async APIs
- Minimize Blocking Calls

---

## Database Optimization
- Create Proper Indexes
- Avoid `SELECT *`
- Fetch Required Columns Only
- Optimize Joins
- Use Pagination
- Analyze Execution Plan

> [!tip]
> **Memory Tip:** Database is usually the First Bottleneck

---

## Entity Framework Core
- Use `AsNoTracking()`
- Project with `Select()`
- Avoid N+1 Queries
- Use `Include()` Carefully
- Prefer Async Methods

---

## Caching
- `IMemoryCache`
- Redis (`IDistributedCache`)
- Cache Frequently Accessed Data
- Reduce Database Calls
- Configure Appropriate TTL

---

## Async Programming
- `async` / `await`
- Non-Blocking I/O
- `Task.WhenAll()`
- Avoid `.Result` and `.Wait()`
- Improve Server Throughput

---

## Connection Pooling
- Reuse Database Connections
- Reduces Connection Overhead
- Built into ADO.NET
- Improves Performance

---

## API Optimization
- Pagination
- Filtering
- Sorting
- Compression
- Response Caching
- DTO Projection

---

## File Optimization
- Compress Large Files
- Stream Large Files
- Upload Directly to Cloud Storage
- Avoid Loading Entire File into Memory

---

## Logging
- Log Meaningful Information
- Avoid Excessive Logging
- Use Appropriate Log Levels
- Asynchronous Logging

---

## Load Balancing
- Distribute Requests
- Horizontal Scaling
- High Availability
- Fault Tolerance

---

## Monitoring & Profiling
- `CloudWatch`
- `Application Insights`
- `dotnet-counters`
- `dotnet-trace`
- SQL Execution Plan
- Performance Counters

> [!tip]
> **Memory Tip:** You can't optimize what you don't measure.

---

## Common Bottlenecks
- Slow SQL Queries
- Missing Indexes
- Large Payloads
- Excessive API Calls
- Blocking Operations
- Memory Leaks
- Network Latency

---

## Performance Best Practices
- Cache Read-Heavy Data
- Optimize Database Queries
- Use Async APIs
- Minimize Network Calls
- Enable Compression
- Profile Before Optimizing
- Monitor Production

---

## Interview Traps
- `IQueryable<T>` vs `IEnumerable<T>`
- `Include()` vs Lazy Loading
- `AsNoTracking()` vs Tracking
- Async vs Multithreading
- Cache vs Database
- Pagination vs Loading All Records
- Compression vs Encryption
- CPU-Bound vs I/O-Bound
- Vertical vs Horizontal Scaling
- Throughput vs Latency

---

## 30-Second Revision Formula

Performance → Application → Database → EF Core → Caching → Async → Connection Pooling → API Optimization → File Optimization → Logging → Load Balancing → Monitoring → Bottlenecks → Best Practices