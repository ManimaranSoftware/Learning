# Delegates

### Delegate

- Type-safe function pointer.
- Holds reference to one or more methods.
- Enables passing methods as parameters.
- Used for callbacks and event handling.
##### Syntax

```
public delegate void Notify();
```

---

##### Single-cast Delegate

```
public delegate void Notify();

public void SendEmail()
{
    Console.WriteLine("Email Sent");
}

Notify notify = SendEmail;
notify();
```

**Output**

```
Email Sent
```

---

### Multicast Delegate

- Holds references to multiple methods.
- Invokes all methods in sequence.
- Created using `+` or `+=`.

A multicast delegate holds references to **multiple methods**.

```
Notify notify = SendEmail;
notify += SendSMS;
notify += UpdateInventory;

notify();
```

**Output**

```
Email Sent
SMS Sent
Inventory Updated
```

Remove a method:

```
notify -= SendSMS;
```

---

##### Rules

- All methods must have the **same signature**.
- Use `+=` to add methods.
- Use `-=` to remove methods.
- A single method = **Single-cast Delegate**.
- Multiple methods = **Multicast Delegate**

---

##### Real-Time Example

**Order Placed**

When an order is placed:

- Save Order
- Send Email
- Send SMS
- Update Inventory
Instead of calling each method directly, use a delegate to invoke all registered methods.

---
##### Where Delegates Are Used

- Events
- Callbacks
- Lambda Expressions
- LINQ
- `Action`
- `Func`
- `Predicate`
- Asynchronous programming

---

### Anonymous Method

- Method without a name.
- Declared using `delegate` keyword.
- Commonly replaced by lambda expressions.
## Note : Anonymous Type is difference and Anonymous Method is different
##### 1. Anonymous Type

```
var person = new
{
    Name = "A",
    Age = 25
};
```

Here:

- No class is created by you.
- The compiler automatically creates a class behind the scenes.
- That's why it's called an **anonymous type**.

Equivalent (roughly):

```
class AnonymousType
{
    public string Name { get; set; }
    public int Age { get; set; }
}
```

You can access it like:

```
Console.WriteLine(person.Name);
Console.WriteLine(person.Age);
```

---

##### 2. Anonymous Method

An anonymous method has **no method name** and uses the `delegate` keyword.

```
delegate()
{
    Console.WriteLine("Hello");
}
```

or assigned to a delegate:

```
Action action = delegate()
{
    Console.WriteLine("Hello");
};

action();
```

---

##### 3. Lambda Expression

A shorter version of an anonymous method.

```
Action action = () =>
{
    Console.WriteLine("Hello");
};

action();
```

---

##### Easy way to remember

| Code                           | What is it?           |
| ------------------------------ | --------------------- |
| `new { Name = "A", Age = 25 }` | **Anonymous Type**    |
| `delegate() { ... }`           | **Anonymous Method**  |
| `() => { ... }`                | **Lambda Expression** |

##### Quick interview trick

Ask yourself:

- Does it create an **object** without a class? → **Anonymous Type**
- Does it create a **method** without a name? → **Anonymous Method**
- Is it using `=>`? → **Lambda Expression**

---

### Action

- Built-in generic delegate.
- Returns `void`.
- Accepts 0 to 16 input parameters.

---

### Func

- Built-in generic delegate.
- Returns a value.
- Last type parameter represents return type.

---

### Predicate

- Built-in generic delegate.
- Accepts one parameter.
- Always returns `bool`.
- Commonly used for filtering.

---

# Events 

##### Event

- An **event** is a notification mechanism built on top of a **delegate**
- Mechanism for notifying subscribers when an action occurs.
- Supports Publisher-Subscriber pattern.
- Can only be raised by the declaring class.
##### Syntax

##### Step 1: Create a Delegate

```
public delegate void PaymentSuccessHandler();
```

##### Step 2: Create an Event

```
public event PaymentSuccessHandler PaymentSuccess;
```

##### Step 3: Subscribe to the Event

```
payment.PaymentSuccess += SendEmail;
payment.PaymentSuccess += SendSMS;
```

##### Step 4: Raise the Event

```
PaymentSuccess?.Invoke();
```

---

##### Real-Time Example

**Payment Successful**

When a payment succeeds:

- Send Email
- Send SMS
- Update Inventory
- Save Audit Log

The payment service simply raises the `PaymentSuccess` event, and all subscribed methods are executed.

---

##### Delegate vs Event

|Delegate|Event|
|---|---|
|Stores method references|Built on a delegate|
|Can be invoked by anyone with access|Only the declaring class can raise it|
|General-purpose|Used for notifications|
|Can exist independently|Cannot exist without a delegate|

---

##### Advantages

- Loose coupling
- Supports Publisher–Subscriber pattern
- Safer than exposing delegates directly
- Easy to add or remove subscribers using `+=` and `-=`

---

##### Where Events Are Used?

- Button Click
- Payment Success
- Order Placed
- Login Success
- File Download Completed
- Background Task Completed

---
##### Easy Memory Trick

- **Delegate** → **Who should be called?**
- **Event** → **When should they be called?**

**Delegate = Contact List **

Stores the methods to invoke.

**Event = Trigger**

When something happens, it invokes the delegate, which calls all subscribed methods.

---

### EventHandler

- Built-in delegate for events.
- Standard event pattern in .NET.
- Supports sender and event arguments.

```
using System;

class Program
{
    static void Main()
    {
        Button button = new Button();

        // Subscribe event
        button.Click += OnButtonClick;

        // Raise event
        button.Press();
    }

    // Event Handler
    static void OnButtonClick(object sender, EventArgs e)
    {
        Console.WriteLine("Button Clicked");
    }
}

class Button
{
    public event EventHandler Click;

    public void Press()
    {
        Click?.Invoke(this, EventArgs.Empty);
    }
}
```

---

### EventArgs

- Base class for passing event data.
- Can be inherited to create custom event data.

### Example 1: No data

```
public event EventHandler Click;

Click?.Invoke(this, EventArgs.Empty);
```

The handler receives:

```
void OnClick(object sender, EventArgs e)
{
    Console.WriteLine("Button Clicked");
}
```

Here, `e` doesn't contain any information.

### Example 2: Passing custom data

```
using System;

class PaymentEventArgs : EventArgs
{
    public decimal Amount { get; set; }
}

class Payment
{
    public event EventHandler<PaymentEventArgs> PaymentSuccess;

    public void Process()
    {
        PaymentSuccess?.Invoke(this, new PaymentEventArgs
        {
            Amount = 1000
        });
    }
}

class Program
{
    static void Main()
    {
        Payment payment = new Payment();
        payment.PaymentSuccess += OnPaymentSuccess;

        payment.Process();
    }

    static void OnPaymentSuccess(object sender, PaymentEventArgs e)
    {
        Console.WriteLine($"Payment Amount: {e.Amount}");
    }
}
```

**Output**

```
Payment Amount: 1000
```

### Interview answer

> `EventArgs` is the base class for event data in C#. It is used to pass information from the event source to the event handler. If no data needs to be passed, we use `EventArgs.Empty`. If additional information is required, we create a custom class that inherits from `EventArgs`.

### Memory trick

- `sender` → **Who** raised the event.
- `EventArgs` (`e`) → **What data** is associated with the event.

Example:

- `sender` = Payment service
- `e.Amount` = `1000`
- `e.TransactionId` = `"TXN12345"`
  
---
## Lambda Expression (`=>`)

- An anonymous function (a function without a name).
- Commonly used with **Delegates, LINQ, and Events**.

**Syntax**

```csharp
(parameters) => expression
```

or

```csharp
(parameters) =>
{
    // code
}
```

---

### Expression Lambda

- Contains a single expression.
- Returns the value automatically.

```csharp
Func<int, int, int> add = (a, b) => a + b;

Console.WriteLine(add(10, 20));   // 30
```

---

### Statement Lambda

- Contains multiple statements.
- Uses `{ }` block.
- Can include loops and conditions.

```csharp
Action<string> greet = name =>
{
    Console.WriteLine($"Hello {name}");
    Console.WriteLine("Welcome!");
};

greet("Mani");
```

---

### Lambda with LINQ (Most Asked)

```csharp
List<int> numbers = new List<int> { 10, 20, 30, 40 };

var result = numbers.Where(n => n > 20);

foreach (var number in result)
{
    Console.WriteLine(number);
}
```

**Output**

```text
30
40
```

---

### Lambda with Event

```csharp
button.Click += (sender, e) =>
{
    Console.WriteLine("Button Clicked");
};
```

---

### Closure

- Lambda can access variables from its enclosing scope.
- Variables remain available even after the outer method exits.

```csharp
int bonus = 100;

Func<int, int> calculateSalary = salary => salary + bonus;

Console.WriteLine(calculateSalary(1000));   // 1100
```

---

### Benefits

- Cleaner and concise code.
- Better readability.
- Strong integration with LINQ.
- Simplifies delegate implementation.
- Widely used in modern C#.

---

### Interview Answer

> A lambda expression is an anonymous function represented using the `=>` operator. It provides a concise way to write methods and is commonly used with delegates, LINQ, and events.

---

### Memory Trick

**Normal Method**

```csharp
// 
void Add(int a, int b)
{
    Console.WriteLine(a + b);
}
```

**Lambda**

```csharp
(a, b) => Console.WriteLine(a + b);
```