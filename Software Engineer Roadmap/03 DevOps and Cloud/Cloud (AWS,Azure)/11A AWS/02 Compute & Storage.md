### Amazon EC2

- EC2 (Elastic Compute Cloud) - Virtual server in AWS.
- Used to host applications.

---

### Amazon Lambda

- Lambda - Serverless compute service.
- Executes code without managing servers.
- Pay only for execution time.

---

### Auto Scaling

- Automatically increases or decreases EC2 instances based on demand.
- Improves availability and cost optimization.

---

### Elastic Load Balancer (ELB)

- Distributes incoming traffic across multiple EC2 instances.
- Improves availability and fault tolerance.

---

### Amazon S3

- S3 (Simple Storage Service) - Object storage service.
- Used for files, images, backups and static content.

---

### S3 Bucket

- Logical container for storing objects in S3.

---

### S3 Object

- File stored inside an S3 bucket.
- Consists of data, metadata and a unique key.

---

### Storage Class

- Defines storage cost and availability.
- Examples - Standard, Intelligent-Tiering, Glacier.

Which S3 storage class would you choose?
- User uploads/photos → **S3 Standard**
- Logs with unpredictable access → **S3 Intelligent-Tiering**
- Monthly reports → **S3 Standard-IA**
- Daily backups → **S3 Glacier Flexible Retrieval**
- Legal/compliance archives → **S3 Glacier Deep Archive**
- High-performance analytics → **S3 Express One Zone**
---

### Amazon EBS

- Elastic Block Store.
- Persistent block storage for EC2 instances.

---

### Amazon EFS

- Elastic File System.
- Shared file storage accessible by multiple EC2 instances.

---

### Serverless

- Executes applications without managing infrastructure.
- AWS automatically handles scaling and server management.

---

### Benefits

- Flexible compute options.
- Scalable storage.
- High availability.
- Cost optimization.
- Managed infrastructure.

---

## Small improvement 💡

Let's also add:

### Use Cases

- **EC2** → Long-running applications.
- **Lambda** → Event-driven and serverless workloads.
- **S3** → File and object storage.
- **EBS** → Storage for a single EC2 instance.
- **EFS** → Shared storage across multiple EC2 instances.