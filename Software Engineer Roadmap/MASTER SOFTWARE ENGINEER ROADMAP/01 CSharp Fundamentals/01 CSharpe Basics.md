## 1. C# Basics

### Variables

- Variable - Named memory location used to store data.
- var - Compile-time type inference, Strongly typed, Type fixed after compilation.
- dynamic - Runtime type resolution, No compile-time type checking, May throw runtime errors.
- object - Base type of all .NET types, Can hold any type, Requires casting to original type.

---

### Data Types

- Value Type - Stores actual value, Usually allocated on stack, Copied by value (`int`, `bool`, `struct`, `enum`).
- Reference Type - Stores reference to object, Object usually allocated on heap (`class`, `string`, `array`, `delegate`).
- Nullable Type - Allows value types to store `null` (`int?`, `bool?`, `DateTime?`).

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
string? name = "Manimaran";  
  
name ??= "Guest";  
  
Console.WriteLine(name); // Manimaran
-----------------------
If the object exists:

Employee emp = new Employee { Name = "Manimaran" };  
  
int? length = emp?.Name.Length;  
  
Console.WriteLine(length); // 9
```
- Type Check (`is`) - Checks whether an object is of a specific type.

```
object value = "Hello";  
  
if (value is string)  
{  
Console.WriteLine("It is a string.");  
}
---
Pattern matching (recommended):
object value = "Hello";  
  
if (value is string text)  
{  
Console.WriteLine(text.ToUpper()); // HELLO  
}

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
- String Interpolation - Embed expressions using `$"{}"`.
- String Comparison (`==`) - Compares string values (content), Not object references.
- `.Equals()` - Compares string values, Supports case-sensitive/case-insensitive comparison using `StringComparison`.
- `ReferenceEquals()` - Checks whether two variables reference the same object.
- `String.Compare()` - Compares two strings and returns `<0`, `0`, or `>0`.
- `String.IsNullOrEmpty()` - Checks if string is `null` or empty.
- `String.IsNullOrWhiteSpace()` - Checks if string is `null`, empty, or only whitespace.

---

### Enums

- Enum - Named set of integral constants, Improves readability and maintainability.

---

### Struct

- Struct - Value type, Lightweight, Stored by value, Supports interfaces, No class inheritance.

---

### Record

- Record - Reference type with value-based equality, Ideal for immutable data models.

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

---

### Serialization

- Serialization - Convert object to JSON/XML/Byte stream.
- Deserialization - Convert JSON/XML/Byte stream back to object.
- System.Text.Json - Built-in JSON serialization library.

---

### Reflection

- Reflection - Inspect assemblies, types, methods and properties at runtime (`System.Reflection`).

---

### Attributes

- Attribute - Adds metadata to assemblies, classes, methods or properties.
- Common Attributes - `[Obsolete]`(warning to developer - old method), `[Serializable]`, `[Required]`, `[Authorize]`.