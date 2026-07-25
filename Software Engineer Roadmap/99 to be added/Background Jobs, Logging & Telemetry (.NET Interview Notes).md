
---

# 1. Background Jobs

## What are Background Jobs?

Background jobs are tasks that run **asynchronously** without blocking the HTTP request.

### Examples

- Send Email
- Generate PDF
- Generate Invoice
- Process Images
- Data Synchronization
- ETL Jobs
- Clean Temporary Files

---

## Ways to Execute Background Jobs

### ❌ Task.Run()

Suitable only for simple fire-and-forget tasks.

```csharp
Task.Run(() =>
{
    DoWork();
});
```

**Limitations**

- Lost if application restarts
- No retry mechanism
- No monitoring
- Not suitable for production recurring jobs

---

### ✅ IHostedService / BackgroundService

Built-in ASP.NET Core solution for long-running background services.

---

### ✅ Hangfire (Most Common Interview Answer)

A popular .NET library used for reliable background job processing.

## Features

- Fire-and-Forget Jobs
- Delayed Jobs
- Recurring Jobs
- Continuation Jobs
- Automatic Retries
- Dashboard
- Persistent Storage

---

## Install

```csharp
using Hangfire;
```

---

## Configure Hangfire

```csharp
builder.Services.AddHangfire(config =>
{
    config.UseSqlServerStorage(connectionString);
});

builder.Services.AddHangfireServer();
```

---

## One Time Job

```csharp
BackgroundJob.Enqueue(() => DoWork());
```

---

## Delayed Job

```csharp
BackgroundJob.Schedule(
    () => DoWork(),
    TimeSpan.FromMinutes(10));
```

---

## Recurring Job

```csharp
RecurringJob.AddOrUpdate(
    "InvoiceJob",
    () => DoWork(),
    Cron.Hourly);
```

---

## Enable Dashboard

```csharp
app.UseHangfireDashboard();
app.UseHangfireServer();
```

Dashboard URL

```
https://localhost:5001/hangfire
```

---

## Why Hangfire?

- Automatic Retry
- Job History
- Dashboard
- Scheduling
- Persistent Storage
- Easy Monitoring

---

# Interview Answer

> For simple tasks, Task.Run() can be used. However, for production applications, I prefer Hangfire because it supports recurring jobs, retries, persistent storage, scheduling, monitoring, and provides a dashboard to track job execution.

---

# 2. Logging

## What is Logging?

Logging is the process of recording application events.

Examples

- User Login
- API Request
- API Response
- Errors
- Exceptions
- Performance Information

---

## ILogger

ASP.NET Core provides a logging abstraction.

```csharp
ILogger<T>
```

It is **not** a logging library.

It is simply an interface (contract).

Multiple logging providers can implement it.

Examples

- Serilog
- NLog
- Log4Net

---

# Logging Flow

```
Application
      │
      ▼
 ILogger Interface
      │
      ▼
 Serilog / NLog
      │
      ▼
File / Database / CloudWatch / Elasticsearch
```

---

# 3. Serilog

## What is Serilog?

Serilog is a **structured logging library** for .NET.

Instead of storing only plain text, it stores logs as **key-value pairs**.

---

## Traditional Logging

```text
User Mani logged in.
```

Cannot easily search

- User = Mani
- LoginTime
- Country

---

## Structured Logging

```csharp
_logger.LogInformation(
    "User {UserName} logged in at {LoginTime}",
    userName,
    DateTime.UtcNow);
```

Output

```text
Message:
User logged in

Properties

UserName = Mani
LoginTime = 2026-07-09
```

---

## JSON Output

```json
{
  "Timestamp":"2026-07-09",
  "Level":"Information",
  "UserName":"Mani",
  "LoginTime":"10:30"
}
```

Now searching becomes easy.

Example

```
UserName = Mani

Level = Error

OrderId = 1001
```

---

## Why Structured Logging?

Because monitoring tools can easily search and filter logs.

---

# Interview Answer

> Serilog is preferred because it supports structured logging. Instead of storing plain text logs, it stores logs as key-value pairs, making logs easier to search, filter, and analyze using tools like Elasticsearch, Kibana, Grafana, and AWS CloudWatch.

---

# 4. NLog vs Serilog

| Feature | NLog | Serilog |
|----------|--------|------------|
| Logging Style | Traditional Text Logging | Structured Logging |
| Structured Logging | Supported | Excellent |
| JSON Support | Yes | Built-in |
| Best For | File Logging | Cloud Native Applications |
| Search | Hard | Easy |
| Works with ILogger | ✅ | ✅ |

---

## Important Interview Note

❌ Don't say

> NLog is old.

✅ Say

> Both NLog and Serilog are modern logging libraries. Serilog was designed with structured logging as its primary focus, whereas NLog originally focused more on traditional text logging, although it also supports structured logging.

---

# 5. Telemetry

## What is Telemetry?

Telemetry is the automatic collection of application data for monitoring and diagnostics.

---

Telemetry includes

- Logs
- Metrics
- Traces
- Events

---

## Telemetry Flow

```
Application

     │

Collect Telemetry

     │

CloudWatch
Application Insights
Elastic Stack

     │

Visualization

Grafana
Kibana
```

---

## Types of Telemetry

### Logs

Application events.

Example

```
User Logged In
```

---

### Metrics

Numerical values.

Examples

- CPU Usage
- Memory Usage
- Request Count
- Response Time

---

### Traces

Track one request across multiple microservices.

Example

```
API Gateway

↓

Order Service

↓

Payment Service

↓

Notification Service
```

Each request carries a **Correlation ID**.

---

### Events

Business events.

Example

```
Invoice Generated

Payment Completed

User Registered
```

---

# Interview Definition

> Telemetry is the automatic collection of logs, metrics, traces, and events to monitor application health, diagnose issues, and improve performance.

---

# 6. Correlation ID

## What is Correlation ID?

A unique identifier generated for every request.

Example

```
8dbd-2345-abc-999
```

This ID travels through every microservice.

```
API Gateway

↓

User Service

↓

Order Service

↓

Payment Service

↓

Notification Service
```

Every service logs the same Correlation ID.

This makes debugging much easier.

---

# 7. Elasticsearch

## What is Elasticsearch?

An open-source distributed search and analytics engine developed by **Elastic**.

---

## Uses

- Store Logs
- Full Text Search
- Analytics
- Fast Searching
- Indexing Large Data

---

## Commonly Used With

```
Serilog

↓

Elasticsearch

↓

Kibana
```

---

# 8. Kibana

Visualization tool developed by Elastic.

Works with Elasticsearch.

Used for

- Log Search
- Dashboards
- Error Analysis
- Monitoring

---

# 9. Grafana

Visualization platform.

Can connect to

- Prometheus
- CloudWatch
- Elasticsearch
- SQL
- Azure Monitor

Mostly used for

- Metrics
- Dashboards
- Monitoring

---

# 10. CloudWatch

AWS monitoring service.

Provides

- Logs
- Metrics
- Alarms
- Dashboards
- Traces (via AWS X-Ray integration)

---

# Quick Interview Questions

## What is ILogger?

Built-in logging abstraction (interface) in ASP.NET Core.

---

## What is Serilog?

A structured logging library that stores logs as key-value pairs.

---

## What is Telemetry?

Automatic collection of logs, metrics, traces, and events.

---

## Difference between Logs and Telemetry?

- Logs are one type of telemetry.
- Telemetry includes logs, metrics, traces, and events.

---

## What is Elasticsearch?

A distributed search and analytics engine used to store and search logs.

---

## What is Kibana?

Visualization tool for Elasticsearch.

---

## What is Grafana?

Dashboard and monitoring tool for metrics and logs.

---

## Difference between Kibana and Grafana?

| Kibana | Grafana |
|----------|----------|
| Mainly for Elasticsearch | Supports multiple data sources |
| Log Analysis | Metrics & Dashboards |
| Elastic Stack | Cloud Monitoring |

---

## What is Hangfire?

A .NET library for scheduling and managing background jobs with retries, persistence, and monitoring.

---

## Hangfire Dashboard

```
/hangfire
```

Shows

- Job Status
- Failed Jobs
- Processing Jobs
- Succeeded Jobs
- Scheduled Jobs