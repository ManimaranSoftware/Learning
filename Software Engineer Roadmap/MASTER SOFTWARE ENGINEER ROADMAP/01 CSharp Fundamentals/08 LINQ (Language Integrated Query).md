### LINQ

- Language feature for querying collections and data sources.
- Supports SQL-like operations in C#.
- Improves readability and reduces code.

---

### Query Syntax

- SQL-like syntax using `from`, `where`, `select`.
- Easier for complex queries.

---

### Method Syntax

- Uses extension methods and lambda expressions.
- Most commonly used in projects.

---

### Where()

- Filters data based on a condition.

---

### Select()

- Projects or transforms data into a new form.

---

### SelectMany()

- Flattens nested collections into a single collection.

---

### OrderBy()

- Sorts data in ascending order.

---

### OrderByDescending()

- Sorts data in descending order.

---

### ThenBy()

- Secondary sorting after `OrderBy()`.

---

### GroupBy()

- Groups data based on a key.

---

### Join()

- Combines two collections based on a matching key.

---

### Distinct()

- Removes duplicate elements.

---

### Any()

- Returns `true` if at least one element matches.

---

### All()

- Returns `true` if all elements satisfy the condition.

---

### Count()

- Returns the number of elements.

---

### First()

- Returns the first matching element.
- Throws exception if no element exists.

---

### FirstOrDefault()

- Returns first matching element or default value.

---

### Single()

- Returns exactly one matching element.
- Throws exception if zero or multiple elements exist.

---

### SingleOrDefault()

- Returns one matching element or default value.
- Throws exception if multiple elements exist.

---

### Last()

- Returns the last matching element.

---

### LastOrDefault()

- Returns last matching element or default value.

---

### Skip()

- Skips specified number of elements.

---

### Take()

- Returns specified number of elements.

---

### Aggregate()

- Performs custom aggregation on a collection.

---

### Deferred Execution

- Query executes only when enumerated.
- Improves performance.

---

### Immediate Execution

- Query executes immediately using methods like `ToList()`, `ToArray()`, `Count()`.

---

### IEnumerable`<T>`

- Executes in memory.
- Suitable for collections like `List<T>` and arrays.

---

### IQueryable`<T>`

- Query executed by data source (e.g., SQL Server via EF Core).
- Improves performance by translating queries.

---

### Benefits

- Readable and concise code.
- Type-safe queries.
- Strong integration with collections and EF Core.
- Reduces manual looping.

---

### Common Interview Comparisons

- Query Syntax vs Method Syntax
- IEnumerable vs IQueryable
- First vs FirstOrDefault
- Single vs SingleOrDefault
- Any vs All
- Deferred Execution vs Immediate Execution