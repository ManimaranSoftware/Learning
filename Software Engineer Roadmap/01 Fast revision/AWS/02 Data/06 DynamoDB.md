# 10-Second Recall

> **DynamoDB → NoSQL → Table → Item → Partition Key → Sort Key → Query → Scan → GSI → Fast → No Joins**

---

# 60-Second Revision

**DynamoDB**

- Fully managed NoSQL database.
- Stores key-value and document data.
- Designed for low latency and automatic scaling.

**Data Structure**

- Table → Item → Attribute.

**Partition Key**

- Identifies and distributes data.

**Sort Key**

- Orders related items within the same partition.

**Query**

- Uses partition key.
- Fast.

**Scan**

- Reads entire table.
- Slower.

**GSI**

- Alternate index for different query patterns.

**Why DynamoDB?**

- Fast reads/writes.
- Flexible schema.
- No joins.
- Great for operational data like statistics.

**Project Example**

- Stored API statistics and reporting data.
- Lambda updated records after processing requests.