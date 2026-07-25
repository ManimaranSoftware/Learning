## **Lambda**

- Serverless compute service.
- Runs code without managing servers.

**Serverless**

- AWS manages servers.
- We only write code.

**Triggers**

- API Gateway
- S3
- SQS
- SNS
- EventBridge
- DynamoDB Streams

**Cold Start**

- New execution environment.
- First request is slower.

**Warm Start**

- Existing environment reused.
- Faster execution.

**Memory**

- More memory = More CPU.

**Timeout**

- Maximum execution: 15 minutes.

**Logs**

- CloudWatch.

**Secrets**

- Secrets Manager.

**Scaling**

- Automatic.

**Billing**

- Requests + Execution Time + Memory.

**Best Use Case**

- Event-driven APIs, file processing, background jobs.

---
## 10-Second Recall

This is what you mentally repeat while waiting outside the interview room.

**Lambda**

> Serverless → Event-driven → Auto Scaling → Cold/Warm Start → CloudWatch Logs → IAM Role → API Gateway Integration