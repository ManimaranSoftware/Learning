#### EventBridge

```
Order Created

↓

EventBridge

Rule 1 → Lambda

Rule 2 → SQS

Rule 3 → SNS
```

Only the matching rules trigger.

---

## Memory Tip

> **SNS = Broadcast**

> **EventBridge = Smart Router**



# Architecture Example

```
Invoice Generated
        │
        ▼
   EventBridge
   ├── Lambda (Analytics)
   ├── SQS (Background Processing)
   └── SNS (Notifications)
```


# 10-Second Recall

> **EventBridge → Event → Event Bus → Rules → Targets → Smart Routing**

---

# 60-Second Revision

**EventBridge**

- Fully managed event bus service.
- Routes events to AWS services based on rules.

**Event**

- Something that happened in the application.

**Event Bus**

- Receives events.

**Rules**

- Match events and determine where to send them.

**Targets**

- Lambda, SQS, SNS, Step Functions, and more.

**Why EventBridge?**

- Decouples applications.
- Supports event-driven architectures.
- Routes events intelligently.

**EventBridge vs SNS**

- SNS: Broadcast to all subscribers.
- EventBridge: Route to selected targets based on rules.

**Project Example**

- Publish an `InvoiceGenerated` event and let EventBridge route it to analytics, notifications, or background processing as required.