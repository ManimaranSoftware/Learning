### Database Design

- Database Design - Process of organizing data for efficiency, consistency and scalability.

---

### Normalization

- Organizes data to reduce redundancy.
- Improves data consistency.

---

### Denormalization

- Introduces controlled redundancy.
- Improves read performance.

---

### Primary Key

- Uniquely identifies each record in a table.

---

### Foreign Key

- Establishes relationships between tables.

---

### Index

- Improves query performance.
- Speeds up data retrieval.

---

### Sharding

- Splits data across multiple databases or servers.
- Improves scalability.

---

### Partitioning

- Divides large tables into smaller partitions.
- Improves query performance and maintenance.

---

### Replication

- Copies data to multiple database servers.
- Improves availability and read scalability.

---

### Read Replica

- Read-only copy of the primary database.
- Handles read traffic.

---

### ACID

- Ensures reliable database transactions.
- Atomicity, Consistency, Isolation and Durability.

---

### CAP Theorem

- Distributed systems can guarantee only two of:
    - Consistency
    - Availability
    - Partition Tolerance

---

### SQL vs NoSQL

- SQL - Structured, relational data.
- NoSQL - Flexible, scalable document/key-value data.

---

### Benefits

- Better scalability.
- Improved performance.
- Reliable data storage.
- Easier maintenance.

---

## Small improvement 💡

Let's also add:

### Read/Write Separation

- Write operations go to the Primary database.
- Read operations are served by Read Replicas.
- Improves scalability.