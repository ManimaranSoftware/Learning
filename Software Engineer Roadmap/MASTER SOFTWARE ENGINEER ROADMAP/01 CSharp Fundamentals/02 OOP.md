### Class & Object

- Class - Blueprint for creating objects, Defines properties and methods.
- Object - Instance of a class, Occupies memory at runtime.

---

### Encapsulation

- Encapsulation - Bundles data and methods together, Restricts direct access using access modifiers.
- Benefits - Data hiding, Better maintainability, Improved security.

---

### Abstraction

- Abstraction - Hides implementation details, Exposes only essential functionality.
- Achieved Using - Abstract classes and Interfaces.

---

### Inheritance

- Inheritance - Allows one class to inherit members of another class, Promotes code reuse.
- Types - Single, Multilevel, Hierarchical (C# does not support multiple class inheritance).

---

### Polymorphism

- Polymorphism - Same method behaves differently based on object or parameters.
- Types - Compile-time (Method Overloading), Runtime (Method Overriding).

---

### Interface

- Interface - Defines a contract, Supports multiple interface inheritance.
- Members - Methods, Properties, Events, Indexers (Fields not allowed).
- Default Implementation - Supported from C# 8.

---

### Abstract Class

- Abstract Class - Cannot be instantiated, Can have abstract and concrete methods.
- Constructor - Supported.
- Fields - Supported.
- Access Modifiers - Supported.

---

### Static

- Static Class - Cannot be instantiated, Contains only static members.
- Static Method - Called without creating an object.
- **Static Constructor** - Executes once before first use of the class.

static means the member belongs to the class itself, not to an object (instance).

```
//Example with class
class Employee
{
    public string Name;
}

Employee e1 = new Employee();
Employee e2 = new Employee();
e1.Name = "Mani";
e2.Name = "maran";  
  
each object has its own Name

//Example with static:
class Employee
{
    public static string Company = "SG";
}

//Access directly through the class:
Console.WriteLine(Employee.Company);
//No object needed.

Interview Examples
Math.PI
Console.WriteLine()
DateTime.Now
These are static members.
```

---

### Virtual

- Virtual Method - Allows derived classes to override implementation.

---

### Override

- Override - Provides new implementation for a virtual or abstract method.

---

### Sealed

- Sealed Class - Cannot be inherited.
- Sealed Method - Prevents further overriding.

---

### Access Modifiers

- public - Accessible from anywhere.
- private - Accessible only within the same class.
- protected - Accessible within the same class and derived classes.
- internal - Accessible within the same assembly.
- protected internal - Accessible from same assembly or derived classes.
- private protected - Accessible within same assembly and derived classes only.