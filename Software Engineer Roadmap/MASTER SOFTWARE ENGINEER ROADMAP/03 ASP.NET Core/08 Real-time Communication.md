### SignalR

- SignalR - Framework for real-time communication between server and clients.
- Communication - Two-way communication.
- Common Usage - Chat, Notifications, Live Dashboards.

---

### Hub

- Hub - Central component of SignalR.
- Purpose - Manages communication between clients and server.
- Base Class - `Hub`.

---

### WebSockets

- WebSockets - Full-duplex communication protocol.
- Persistent connection between client and server.
- Used by SignalR when available.

---

### Long Polling

- Client repeatedly sends requests to receive updates.
- Used when WebSockets are unavailable.
- Less efficient than WebSockets.

---

### Server-Sent Events (SSE)

- One-way communication from server to client.
- Server continuously pushes updates.
- Simpler than WebSockets.

---

### Transport Fallback

- SignalR automatically selects the best transport.
- Order - WebSockets → Server-Sent Events → Long Polling.

---

### gRPC

- High-performance RPC framework.
- Uses HTTP/2.
- Uses Protocol Buffers (protobuf) for serialization.
- Faster than REST for service-to-service communication.

---

### Protocol Buffers (Protobuf)

- Efficient binary serialization format.
- Smaller and faster than JSON.
- Used by gRPC.

---

### Hosted Service

- Background service that runs independently of HTTP requests.
- Used for scheduled and long-running tasks.

---

### BackgroundService

- Base class for implementing hosted services.
- Executes background work continuously.

---

### IHostedService

- Interface for creating background services.
- Provides `StartAsync()` and `StopAsync()` methods.

---

### Benefits

- Real-time updates.
- High-performance communication.
- Efficient background processing.
- Suitable for distributed applications.