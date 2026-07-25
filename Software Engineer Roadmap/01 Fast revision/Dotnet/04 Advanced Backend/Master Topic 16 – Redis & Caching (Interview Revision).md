## Caching Basics
- Stores Frequently Accessed Data
- Reduces Database Calls
- Improves Response Time
- Improves Scalability

> [!tip]
> **Memory Tip:** Cache = Fast Memory

---

## Types of Caching
- In-Memory Cache
- Distributed Cache
- Client-Side Cache
- CDN Cache

---

## `IMemoryCache`
- Stored in Application Memory
- Fastest Access
- Single Server Only
- Lost on Application Restart

---

## `IDistributedCache`
- Shared Across Multiple Servers
- Supports Load Balancing
- Common Provider → Redis
- Better for Distributed Systems

> [!tip]
> **Memory Tip:** Memory Cache = One Server | Redis = Multiple Servers

---

## Redis
- In-Memory Key-Value Store
- Distributed Cache
- Extremely Fast
- Supports Persistence
- Open Source

---

## Redis Data Types
- String
- Hash
- List
- Set
- Sorted Set

---

## Cache Strategies
- Cache Aside (Lazy Loading)
- Read Through
- Write Through
- Write Behind

> [!tip]
> **Memory Tip:** Cache Aside = Most Common Pattern

---

## Cache Aside Pattern
- Check Cache
- If Miss → Read Database
- Store Result in Cache
- Return Response

---

## Cache Expiration
- Absolute Expiration
- Sliding Expiration
- Time-To-Live (TTL)

---

## Cache Invalidation
- Remove Stale Data
- Update Cache After Database Update
- TTL-Based Expiration
- Event-Based Invalidation

---

## Distributed Caching Benefits
- Shared Cache
- Better Performance
- Horizontal Scaling
- High Availability

---

## Redis Use Cases
- Session Storage
- API Response Cache
- Frequently Accessed Data
- Rate Limiting
- Distributed Locking
- Leaderboards

---

## Performance Best Practices
- Cache Read-Heavy Data
- Avoid Caching Frequently Updated Data
- Use Appropriate TTL
- Keep Cache Keys Meaningful
- Monitor Cache Hit Ratio

---

## Common Issues
- Cache Miss
- Cache Hit
- Cache Stampede
- Cache Penetration
- Stale Data

---

## Interview Traps
- `IMemoryCache` vs `IDistributedCache`
- Redis vs Database
- Absolute vs Sliding Expiration
- Cache Hit vs Cache Miss
- Cache Aside vs Write Through
- Cache vs Session
- Redis Persistence vs In-Memory
- Cache Invalidation Strategies

---

## 30-Second Revision Formula

Caching → Types → `IMemoryCache` → `IDistributedCache` → Redis → Data Types → Cache Strategies → Cache Aside → Expiration → Invalidation → Distributed Cache → Use Cases → Best Practices → Common Issues