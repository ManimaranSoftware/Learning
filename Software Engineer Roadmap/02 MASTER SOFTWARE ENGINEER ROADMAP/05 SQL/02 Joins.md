### Join

- Join - Combines data from two or more tables based on a related column.

---

### INNER JOIN

- Returns only matching records from both tables.

---

### LEFT JOIN (LEFT OUTER JOIN)

- Returns all records from the left table and matching records from the right table.
- Non-matching right-side values become `NULL`.

---

### RIGHT JOIN (RIGHT OUTER JOIN)

- Returns all records from the right table and matching records from the left table.
- Non-matching left-side values become `NULL`.

---

### FULL JOIN (FULL OUTER JOIN)

- Returns all matching and non-matching records from both tables.
- Non-matching values become `NULL`.

---

### CROSS JOIN

- Returns Cartesian product of both tables.
- Every row from the first table is combined with every row from the second table.

---

### SELF JOIN

- Joins a table with itself.
- Commonly used for hierarchical data like Employee–Manager.

---

### Equi Join

- Join using the `=` operator.
- Most common type of join.

---

### Non-Equi Join

- Join using operators like `<`, `>`, `<=`, `>=`, `BETWEEN`.

---

### Join Condition

- Defines how two tables are related.
- Usually based on Primary Key and Foreign Key.

---

### Alias

- Alias - Temporary name for a table or column.
- Improves query readability.
- Commonly used in joins.

---

### Benefits

- Retrieve related data.
- Normalize query results.
- Reduce data duplication.
- Efficient relational queries.