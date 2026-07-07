# LINQ

- Language feature for querying collections and data sources.
- Supports SQL-like operations in C#.
- Improves readability and reduces code.

---

## Query Syntax

- SQL-like syntax using `from`, `where`, `select`.

```csharp
var result = from n in numbers
             where n > 20
             select n;
```

---

## Method Syntax (Most Used)

- Uses extension methods and lambda expressions.

```csharp
var result = numbers.Where(n => n > 20);
```

---

## Where()

- Filters data.

```csharp
numbers.Where(n => n > 20);
```

---

## Select()

- Projects/transforms data.

```csharp
employees.Select(e => e.Name);
```

---

## SelectMany()

- Flattens nested collections.

```csharp
students.SelectMany(s => s.Subjects);
```

---

## OrderBy()

- Ascending order.

```csharp
employees.OrderBy(e => e.Name);
```

---

## OrderByDescending()

- Descending order.

```csharp
employees.OrderByDescending(e => e.Salary);
```

---

## ThenBy()

- Secondary sorting.

```csharp
employees.OrderBy(e => e.Department)
         .ThenBy(e => e.Name);
```

---

## GroupBy()

- Groups by a key.

```csharp
employees.GroupBy(e => e.Department);
```

---

## Join()

- Joins two collections.

```csharp
employees.Join(departments,
    e => e.DepartmentId,
    d => d.Id,
    (e, d) => new { e.Name, d.DepartmentName });
    
    // e is alias for employees 
    // d is alias for department
```

```SQL
SELECT e.Name, d.DepartmentName
FROM Employee e
JOIN Department d
ON e.DepartmentId = d.Id;
```
---

## Distinct()

- Removes duplicates.

```csharp
numbers.Distinct();
```

---

## Any()

- Returns `true` if at least one element matches.

```csharp
numbers.Any(n => n > 100);
```

---

## All()

- Returns `true` if all elements match.

```csharp
numbers.All(n => n > 0);
```

---

## Count()

- Returns total count.

```csharp
numbers.Count();
```

or

```csharp
numbers.Count(n => n > 20);
```

---

## First()

- Returns first element.
- Throws exception if not found.

```csharp
numbers.First();
```

---

## FirstOrDefault()

- Returns first element or default.

```csharp
numbers.FirstOrDefault();
```

---

## Single()

- Returns exactly one element.
- Throws exception if none or multiple exist.

```csharp
employees.Single(e => e.Id == 1);
```

---

## SingleOrDefault()

- Returns one element or default.
- Throws exception if multiple exist.

```csharp
employees.SingleOrDefault(e => e.Id == 1);
```

---

## Last()

- Returns last element.

```csharp
numbers.Last();
```

---

## LastOrDefault()

- Returns last element or default.

```csharp
numbers.LastOrDefault();
```

---

## Skip()

- Skips specified elements.

```csharp
numbers.Skip(10);
```

---

## Take()

- Takes specified elements.

```csharp
numbers.Take(5);
```

---

## Aggregate()

- Performs custom aggregation.

```csharp
numbers.Aggregate((a, b) => a + b);
```

---

## Deferred Execution

- Query executes only when enumerated.

```csharp
var result = numbers.Where(n => n > 20);

// Executes here
foreach (var n in result)
{
    Console.WriteLine(n);
}
```

---

## Immediate Execution

- Executes immediately using methods like `ToList()`, `ToArray()`, `Count()`.

```csharp
var list = numbers.Where(n => n > 20).ToList();
```

---

## IEnumerable `<T>`

- Executes in memory.
- Used for `List<T>`, arrays, etc.

```csharp
IEnumerable<int> nums = numbers.Where(n => n > 20);
```

---

## IQueryable`<T>`

- Query executed by the database (EF Core).

```csharp
IQueryable<Employee> employees = context.Employees;
```

---

## Benefits

- Readable and concise code.
- Type-safe queries.
- Strong integration with collections and EF Core.
- Reduces manual looping.

---

## Common Interview Comparisons

- Query Syntax vs Method Syntax
- IEnumerable vs IQueryable
- First vs FirstOrDefault
- Single vs SingleOrDefault
- Any vs All
- Deferred Execution vs Immediate Execution


# LINQ Interview Questions

## Q: Find the department with the **second highest employee count** (L&T interview question)

```csharp
var result = employees
    .GroupBy(e => e.Department)
    .Select(g => new
    {
        Department = g.Key,
        EmployeeCount = g.Count()
    })
    .OrderByDescending(x => x.EmployeeCount)
    .Skip(1)
    .FirstOrDefault();
```

**Output**

```text
Department = IT
EmployeeCount = 10
```

**Approach**

- `GroupBy()` → Group employees by department.
    
- `Count()` → Count employees in each department.
    
- `OrderByDescending()` → Sort by employee count (highest first).
    
- `Skip(1)` → Skip the highest.
    
- `FirstOrDefault()` → Return the second highest department.
    

---

## Q: Find only the **department name** with the second highest employee count

```csharp
string departmentName = employees
    .GroupBy(e => e.Department)
    .OrderByDescending(g => g.Count())
    .Skip(1)
    .Select(g => g.Key)
    .FirstOrDefault();
```

**Output**

```text
IT
```

**Memory Trick**

```text
GroupBy → Count → OrderByDescending → Skip(1) → Select(Key) → FirstOrDefault()
```