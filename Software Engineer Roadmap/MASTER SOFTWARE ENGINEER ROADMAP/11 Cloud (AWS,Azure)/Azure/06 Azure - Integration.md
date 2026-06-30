## Topics

- Azure Service Bus
- Event Grid
- Event Hub
- Logic Apps
- API Management (APIM)

---

# Azure Service Bus

- Enterprise messaging service.
- Enables communication between applications.
- Supports Queues and Topics.
- Ensures reliable message delivery.
- AWS Equivalent: Amazon SQS + SNS.
- Example: Order Service sends message → Invoice Service processes later.
- Interview: Used for asynchronous communication between microservices.

---

# Event Grid

- Event routing service.
- Delivers events from one service to multiple subscribers.
- Push-based architecture.
- AWS Equivalent: Amazon EventBridge.
- Example: Blob uploaded → Trigger Azure Function.
- Interview: Best for event-driven architectures.

---

# Event Hub

- Big data streaming platform.
- Processes millions of events per second.
- Used for telemetry, IoT and log ingestion.
- AWS Equivalent: Amazon Kinesis.
- Example: IoT sensors sending live temperature data.

---

# Logic Apps

- Low-code workflow automation service.
- Connects Azure services and third-party applications.
- Supports built-in connectors.
- AWS Equivalent: AWS Step Functions (closest).
- Example: New Email → Save Attachment → Upload to Blob Storage.
- Interview: Used for workflow automation without writing much code.

---

# API Management (APIM)

- Gateway for managing APIs.
- Secures, publishes and monitors APIs.
- Supports Rate Limiting, Authentication, Versioning and Analytics.
- AWS Equivalent: Amazon API Gateway.
- Example: Expose internal APIs securely to external clients.
- Interview: Used as a centralized API gateway.

---

## Difference

|Service|Purpose|
|---|---|
|Service Bus|Messaging|
|Event Grid|Event Routing|
|Event Hub|Event Streaming|
|Logic Apps|Workflow Automation|
|API Management|API Gateway|

---

## Revision (1 Minute)

- Service Bus = Enterprise Messaging
- Event Grid = Event Routing
- Event Hub = Streaming
- Logic Apps = Workflow Automation
- APIM = API Gateway