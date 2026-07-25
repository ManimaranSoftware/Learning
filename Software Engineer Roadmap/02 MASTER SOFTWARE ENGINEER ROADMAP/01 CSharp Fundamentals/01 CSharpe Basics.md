## 1. C# Basics

### Variables

- Variable - Named memory location used to store data.
- var - Compile-time type inference, Strongly typed, Type fixed after compilation.
- dynamic - Runtime type resolution, No compile-time type checking, May throw runtime errors.
- object - Base type of all .NET types, Can hold any type, Requires casting to original type.

---

### Data Types

- Value Type - Stores actual value, Usually allocated on stack, Copied by value (`int`, `bool`, `struct`, `enum`). - exception: defined inside class will be stored on heap
- Reference Type - Stores reference to object, Object usually allocated on heap (`class`, `string`, `array`, `delegate`). - exception: reference it self(the pointer or memory address) will be stored on stack.
- Nullable Type - Allows value types to store `null` (`int?`, `bool?`, `DateTime?`).
- ```
  int? age = null;
	int? salary = 50000;
	Equivalent to:
	  Nullable<int> age = null;
	if (age.HasValue)
	{
	    Console.WriteLine(age.Value);
	}
  ```

---

### Operators

- Arithmetic Operators - `+`, `-`, `*`, `/`, `%`
- Relational Operators - `==`, `!=`, `>`, `<`, `>=`, `<=`
- Logical Operators - `&&`, `||`, `!`
- Assignment Operators - `=`, `+=`, `-=`, `*=`, `/=`

- Null-Coalescing Operator (`??`) - Returns right operand if left operand is `null`.
```
string? name = null;  
  
string result = name ?? "Guest";  
  
Console.WriteLine(result); // Guest
```

- Null-Coalescing Assignment (`??=`) - Assigns value only if variable is `null`.
```
string? name = null;  
  
name ??= "Guest";  
  
Console.WriteLine(name); // Guest
-----------
If `name` already has a value:

string? name = "Manimaran";  
  
name ??= "Guest";  
  
Console.WriteLine(name); // Manimaran
```

- Null-Conditional Operator (`?.`) - Safely accesses members if object is not `null`.
```
 Employee? emp = null;

 // Safely returns null instead of throwing a NullReferenceException 
 int? length = emp?.Name?.Length;

 Console.WriteLine(length == null ? "Null" : length);
-----------------------
If the object exists:

Employee emp = new Employee { Name = "Manimaran" };  
  
int? length = emp?.Name?.Length;  
  
Console.WriteLine(length); // 9
```
- Type Check (`is`) - Checks whether an object is of a specific type.

```
object value = "Hello";  
  
if (value is string)  - we are just checking the type
{  
Console.WriteLine("It is a string.");  
}
---
Pattern matching (recommended):
object value = "Hello";  
  
if (value is string text)  //- text is variable - as we want to access the variable
{  
Console.WriteLine(text.ToUpper()); // HELLO  
}

- Old-school way (`if (value is string) { var s = (string)value; }`) forces the runtime to check the type **twice**—once for the `is` check, and once for the explicit cast.
- Pattern matching (`if (value is string text)`) checks the type **exactly once** and assigns it.

```
- Safe Cast (`as`) - Attempts type conversion, Returns `null` if conversion fails.
```
object obj = "Hello";  
  
string? text = obj as string;  
  
Console.WriteLine(text); // Hello
-------------------
Conversion fails:

object obj = 100;  
  
string? text = obj as string;  
  
Console.WriteLine(text); // null
```

### Quick Interview Summary

| Operator | Purpose                               | Example            |
| -------- | ------------------------------------- | ------------------ |
| `??`     | Return default if `null`              | `name ?? "Guest"`  |
| `??=`    | Assign only if `null`                 | `name ??= "Guest"` |
| `?.`     | Safe member access                    | `emp?.Name`        |
| `is`     | Check type                            | `obj is string`    |
| `as`     | Safe cast (returns `null` on failure) | `obj as string`    |

---

### Control Statements

- if / else - Conditional execution.
- switch - Multi-way branching.
- switch Expression - Simplified switch returning a value.
	```
	int dayNumber = 6;
	
	 // The entire switch expression assigns its result directly to the variable         string dayType = dayNumber switch
	{
	1 or 2 or 3 or 4 or 5 => "Weekday", 
	6 or 7 => "Weekend",
	 _ => "Invalid day number" // The '_' is the default case 
	};
	Console.WriteLine(dayType); // Output: Weekend
	```
- for - Executes a fixed number of iterations.
- foreach - Iterates through collections.
- while - Executes while condition is true.
- do...while - Executes at least once.
- break - Exits loop or switch.
- continue - Skips current iteration.
- return - Exits method and optionally returns a value.

---

### Methods

- Method - Reusable block of code.
- Method Overloading - Same method name, Different parameter list.
- Optional Parameters - Parameters with default values.
- Named Parameters - Pass arguments by parameter name.
- Expression-bodied Method (`=>`) - Short syntax for single-expression methods.

---

### Parameters

- Value Parameter - Passes a copy of the value.
- ref - Pass by reference, Variable must be initialized.(update value)
- out - Pass by reference, Used to return values, Initialization not required.(get value)
- in - Pass by reference, Read-only inside method.
### `in`

- **`in`** - Passes an argument **by reference** but **does not allow modification** inside the method. It avoids copying large value types (such as `struct`), improving performance while keeping the data read-only. but we can't modify the value(readonly).

```
void Display(in int number)
{    
Console.WriteLine(number);
}
```
- params - Accepts variable number of arguments.

---

### Strings

- String - Immutable, New object created on modification, Reference type.
- StringBuilder - Mutable, Better for frequent modifications (`System.Text`).
	-```
	using System.Text
	StringBuilder sb = new StringBuilder();
	sb.Append("Hello");
	  ```
- String Interpolation - Embed expressions using `$"{}"`.
- String Comparison (`==`) - Compares string values (content), Not object references.
- `.Equals()` - Compares string values, Supports case-sensitive/case-insensitive comparison using `StringComparison`.
	- Use **`StringComparison.OrdinalIgnoreCase`** with `.Equals()` inside switch expressions for the cleanest, safest case-insensitive matching.
	- ```
	   string input = "ADMIN"; 
	   if (string.Equals(input, "admin", StringComparison.OrdinalIgnoreCase))
	  ```
	- Use **`.ToLowerInvariant()`** on the switch variable if you are stuck using old-school traditional switch statements. 
- `ReferenceEquals()` - Checks whether two variables reference the same object.
- `String.Compare()` - Compares two strings and returns `<0`, `0`, or `>0`.
- `String.IsNullOrEmpty()` - Checks if string is `null` or empty.
- `String.IsNullOrWhiteSpace()` - Checks if string is `null`, empty, or only whitespace.

---

### Enums

- Enum - Named set of integral constants, Improves readability and maintainability.
```
enum OrderStatus 
{ 
Pending,
Processing,
Shipped,
Delivered
}

if (currentStatus == OrderStatus.Shipped)
{
Console.WriteLine("Your package is on the way!");
}
```

---

### Struct

- Struct - Value type, Lightweight, Stored by value, Supports interfaces, No class inheritance.
```
// Class example
class Employee
{
    public string Name;
}

Employee e1 = new Employee();
e1.Name = "Mani";

Employee e2 = e1;   // Copies the reference
e2.Name = "Kumar";

Console.WriteLine(e1.Name); // Kumar
Console.WriteLine(e2.Name); // Kumar

//Reason: Both `e1` and `e2` point to the same object
----------------------


//Struct example
struct Employee
{
    public string Name;
}

Employee e1 = new Employee();
e1.Name = "Mani";

Employee e2 = e1;   // Copies the value
e2.Name = "Kumar";

Console.WriteLine(e1.Name); // Mani
Console.WriteLine(e2.Name); // Kumar

//Reason: `e2` gets its own copy.
```

---

### Record

- Record - Reference type with value-based equality, Ideal for immutable data models.
### Class

```
class Employee  
{  
public string Name { get; set; }  
public int Age { get; set; }  
}  
  
var e1 = new Employee { Name = "Mani", Age = 25 };  
var e2 = new Employee { Name = "Mani", Age = 25 };  
  
Console.WriteLine(e1 == e2); // False
```

Even though the data is the same, they are different objects.

---

### Record

```
record Employee(string Name, int Age);

var e1 = new Employee("Mani", 25);
var e2 = new Employee("Mani", 25);

Console.WriteLine(e1 == e2); // True
```

Here, the values are the same, so the records are considered equal.

##### Another useful feature (`with`)

```
record Employee(string Name, int Age);

var e1 = new Employee("Mani", 25);

var e2 = e1 with { Age = 26 };

Console.WriteLine(e1); // Employee { Name = Mani, Age = 25 }
Console.WriteLine(e2); // Employee { Name = Mani, Age = 26 }
```

The `with` expression creates a copy with only the specified changes.

##### Interview answer (30 seconds)

> A **record** is mainly used for immutable data objects. Unlike a class, records use **value-based equality**, so two records with the same property values are considered equal. Records also support concise syntax and the `with` expression to create modified copies.

---

### Type Conversion

- Implicit Conversion - Automatic, No data loss.
- Explicit Conversion - Manual cast, Possible data loss.
- Boxing - Value Type → Object.
- Unboxing - Object → Value Type.

---

### File Handling

- File - Static class for common file operations.
- FileInfo - Instance-based file operations.
- StreamReader - Reads text from files.
- StreamWriter - Writes text to files.
```
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Write
        File.WriteAllText("sample.txt", "Hello World");

        // Read
        string content = File.ReadAllText("sample.txt");
        Console.WriteLine(content);

        // Append
        File.AppendAllText("sample.txt", "\nWelcome to C#");

        // Write multiple lines
        string[] lines = { "Mani", "Kumar", ".NET Developer" };
        File.WriteAllLines("employees.txt", lines);

        // Read multiple lines
        foreach (string line in File.ReadAllLines("employees.txt"))
            Console.WriteLine(line);

        // Check file exists
        if (File.Exists("sample.txt"))
            Console.WriteLine("File Exists");

        // Copy
        File.Copy("sample.txt", "backup.txt", true);

        // Move / Rename
        File.Move("backup.txt", "backup_new.txt");

        // Delete
        if (File.Exists("backup_new.txt"))
            File.Delete("backup_new.txt");

        // Create directory
        Directory.CreateDirectory("Reports");

        // Check directory exists
        if (Directory.Exists("Reports"))
            Console.WriteLine("Directory Exists");

        // StreamWriter - Used to **read** data from a file **line by line** or character by character
        using (StreamWriter writer = new StreamWriter("stream.txt"))
        {
            writer.WriteLine("First Line");
            writer.WriteLine("Second Line");
        }

        // StreamReader - Used to **write** data to a file **line by line**.
        using (StreamReader reader = new StreamReader("stream.txt"))
        {
            string line;
            while ((line = reader.ReadLine()) != null)
                Console.WriteLine(line);
        }
    }
}
```

---

### Serialization

- Serialization - Convert object to JSON/XML/Byte stream.
- Deserialization - Convert JSON/XML/Byte stream back to object.
- System.Text.Json - Built-in JSON serialization library.

##### System.Text.Json
```
using System;
using System.Text.Json;

class Employee
{
    public string Name { get; set; }
    public int Age { get; set; }
}

class Program
{
    static void Main()
    {
        // Create object
        Employee emp = new Employee
        {
            Name = "Mani",
            Age = 25
        };

        // Serialize (Object -> JSON)
        string json = JsonSerializer.Serialize(emp);
        Console.WriteLine(json);
        
        // output
        // {"Name":"Mani","Age":25}

        // Deserialize (JSON -> Object)
        Employee employee = JsonSerializer.Deserialize<Employee>(json);

        Console.WriteLine(employee.Name);
        Console.WriteLine(employee.Age);
        
        //output
        // mani
        // 25
    }
}
```

##### Newtonsoft.Json

```csharp
using System;
using Newtonsoft.Json;

class Employee
{
    public string Name { get; set; }
    public int Age { get; set; }
}

class Program
{
    static void Main()
    {
        // Create object
        Employee emp = new Employee
        {
            Name = "Mani",
            Age = 25
        };

        // Serialize (Object -> JSON)
        string json = JsonConvert.SerializeObject(emp);
        Console.WriteLine(json);

        // Output
        // {"Name":"Mani","Age":25}

        // Deserialize (JSON -> Object)
        Employee employee = JsonConvert.DeserializeObject<Employee>(json);

        Console.WriteLine(employee.Name);
        Console.WriteLine(employee.Age);

        // Output
        // Mani
        // 25
    }
}
```
---

### Reflection - 11 CSharp advanced concepts page

- Reflection - Inspect assemblies, types, methods and properties at runtime (`System.Reflection`).

---

### Attributes

- Attribute - Adds metadata to assemblies, classes, methods or properties.
- Common Attributes - `[Obsolete]`(warning to developer - old method), `[Serializable]`, `[Required]`, `[Authorize]`.