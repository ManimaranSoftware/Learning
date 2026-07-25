### Subquery

- Subquery - Query written inside another SQL query.
- Can be used in `SELECT`, `FROM`, `WHERE` and `HAVING`.

---

### Nested Subquery

- Subquery inside another subquery.
- Supports multiple levels.

---

### Correlated Subquery

- References columns from the outer query.
- Executes once for each row of the outer query.

---

### Single Row Subquery

- Returns only one row.
- Common Operators - `=`, `>`, `<`, `>=`, `<=`.

---

### Multiple Row Subquery

- Returns multiple rows.
- Common Operators - `IN`, `ANY`, `ALL`, `EXISTS`.

---

### EXISTS

- Returns `TRUE` if subquery returns at least one row.
- Stops searching after first match.

---

### NOT EXISTS

- Returns `TRUE` if subquery returns no rows.

---

### IN

- Checks whether a value exists in a list or subquery.

---

### ANY

- Compares a value with any value returned by the subquery.

---

### ALL

- Compares a value with all values returned by the subquery.

---

### Common Table Expression (CTE)

- CTE - Temporary named result set.
- Declared using `WITH`.
- Improves query readability.

---

### Recursive CTE

- CTE that references itself.
- Commonly used for hierarchical data.

---
### Derived Table

- Derived Table - Temporary result set created inside the `FROM` clause.
- Exists only during query execution.
---
### Benefits

- Simplifies complex queries.
- Improves readability.
- Supports recursive queries.
- Reduces query duplication.

---
