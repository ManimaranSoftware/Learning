### Migration

- Migration - Tracks and applies database schema changes.
- Eliminates manual database updates.

---

### Add Migration

- Creates a new migration based on model changes.
- Common Command - `Add-Migration`.

---

### Update Database

- Applies pending migrations to the database.
- Common Command - `Update-Database`.

---

### Remove Migration

- Removes the last migration if not applied.
- Common Command - `Remove-Migration`.

---

### Model Snapshot

- Stores the current model structure.
- Used by EF Core to detect schema changes.

---

### Code First

- Database created from C# entity classes.
- Most commonly used approach.

---

### Database First

- Entity classes generated from an existing database.

---

### Transactions

- Transaction - Ensures multiple operations execute as a single unit.
- Follows ACID principles.

---

### Begin Transaction

- Starts a database transaction.

---

### Commit

- Permanently saves all transaction changes.

---

### Rollback

- Reverts all changes if an error occurs.

---

### SaveChanges()

- Executes all pending changes in a transaction by default.

---

### Seed Data

- Seed Data - Inserts initial or default data into the database.
- Common Usage - Roles, Admin User, Lookup Tables.

---

### Database Ensure Methods

- EnsureCreated() - Creates database if it doesn't exist. Does not use migrations.
- EnsureDeleted() - Deletes the database.
- Common Usage - Testing and development.

---

### Distributed Transaction

- Transaction spanning multiple databases or services.
- Less common in modern microservices.

---

### Benefits

- Version-controlled database schema.
- Easy deployment.
- Safe data updates.
- Reliable data consistency.