### Transaction

- Transaction - Group of SQL operations executed as a single unit.
- Ensures data consistency and integrity.

---

### ACID Properties

### Atomicity

- All operations succeed or all fail.
- No partial updates.

---

### Consistency

- Database remains in a valid state before and after the transaction.

---

### Isolation

- Concurrent transactions do not interfere with each other.

---

### Durability

- Once committed, changes are permanently saved.

---

### BEGIN TRANSACTION

- Starts a new transaction.

---

### COMMIT

- Permanently saves all transaction changes.

---

### ROLLBACK

- Reverts all changes made during the transaction.

---

### SAVEPOINT

- Creates a checkpoint inside a transaction.
- Allows partial rollback.

---

### Transaction Isolation Level

- Read Uncommitted
- Read Committed
- Repeatable Read
- Serializable
- Snapshot

---

### Dirty Read

- Reads uncommitted data from another transaction.

---

### Non-Repeatable Read

- Same query returns different results within one transaction.

---

### Phantom Read

- Same query returns additional or missing rows due to concurrent changes.

---

### Deadlock

- Two or more transactions wait indefinitely for each other.
- SQL Server automatically selects one transaction as the victim.

---

### Lock

- Mechanism used to maintain data consistency.
- Prevents conflicting operations.

---
### Lock Types

- Shared Lock (S) - Allows multiple reads.
- Exclusive Lock (X) - Required for INSERT, UPDATE and DELETE.
- Update Lock (U) - Prevents deadlocks during updates.
---
### Benefits

- Data consistency.
- Reliable database operations.
- Safe concurrent access.
- Prevents partial updates.