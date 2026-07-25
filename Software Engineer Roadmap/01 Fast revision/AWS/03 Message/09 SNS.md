# 10-Second Recall

> **SNS → Publish → Topic → Subscribe → One Message → Many Subscribers → Broadcast**

---

# 60-Second Revision

**SNS**

- Fully managed publish-subscribe messaging service.
- Used to broadcast messages to multiple subscribers.

**Publisher**

- Sends a message to an SNS topic.

**Topic**

- Communication channel for messages.

**Subscriber**

- Receives messages from the topic.

**Supported Subscribers**

- Email
- SMS
- Lambda
- SQS
- HTTP/HTTPS

**Why SNS?**

- One message can notify multiple systems simultaneously.

**SNS vs SQS**

- SNS: One-to-many, push-based notifications.
- SQS: One-to-one processing, queue-based.

**Project Example**

- After an invoice is generated, publish an event to SNS so email notifications, logging, and downstream services can all react independently.