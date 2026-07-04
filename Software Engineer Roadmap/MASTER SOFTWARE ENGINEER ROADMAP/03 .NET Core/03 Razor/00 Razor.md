# Razor

## Razor

- Razor is the view engine used in ASP.NET Core MVC.
    
- Combines HTML with C# code.
    
- Files use the `.cshtml` extension.
    
- Used to create dynamic web pages.
    

---

## Razor Syntax

- `@` symbol is used to write C# code inside HTML.
    

```cshtml
<h1>@DateTime.Now</h1>
```

---

## Display Variable

```cshtml
@{
    string name = "Mani";
}

<h2>@name</h2>
```

---

## If Condition

```cshtml
@if (true)
{
    <h2>Welcome</h2>
}
```

---

## Loop

```cshtml
@foreach (var employee in employees)
{
    <p>@employee.Name</p>
}
```

---

## Model

- Passes data from the Controller to the View.
    

**Controller**

```csharp
public IActionResult Index()
{
    Employee employee = new Employee
    {
        Name = "Mani"
    };

    return View(employee);
}
```

**View**

```cshtml
@model Employee

<h2>@Model.Name</h2>
```

---

## ViewData

- Passes data from Controller to View.
    
- Available only for the current request.
    
- Uses a dictionary.
    

**Controller**

```csharp
ViewData["Name"] = "Mani";
```

**View**

```cshtml
<h2>@ViewData["Name"]</h2>
```

---

## ViewBag

- Dynamic wrapper around `ViewData`.
    
- Used to pass small amounts of data.
    

**Controller**

```csharp
ViewBag.Name = "Mani";
```

**View**

```cshtml
<h2>@ViewBag.Name</h2>
```

---

## TempData

- Stores data between requests.
    
- Commonly used after redirects.
    
- Data is removed after it is read.
    

**Controller**

```csharp
TempData["Message"] = "Employee Created";
```

**View**

```cshtml
<h2>@TempData["Message"]</h2>
```

---

## HTML Helpers

- Generate HTML elements using C#.
    

```cshtml
@Html.TextBox("Name")

@Html.TextBoxFor(m => m.Name)

@Html.DisplayFor(m => m.Name)
```

---

## Tag Helpers

- Server-side attributes that generate HTML.
    
- Cleaner and preferred over HTML Helpers.
    

```cshtml
<input asp-for="Name" />

<label asp-for="Name"></label>

<span asp-validation-for="Name"></span>
```

---

## Partial View

- Reusable Razor view.
    
- Used to avoid duplicate UI.
    

```cshtml
<partial name="_EmployeePartial" />
```

---

## Layout Page

- Shared page template.
    
- Commonly contains Header, Footer, and Navigation.
    

```cshtml
@{
    Layout = "_Layout";
}
```

---

## Sections

- Used to inject page-specific content into a layout.
    

```cshtml
@section Scripts
{
    <script>
        console.log("Loaded");
    </script>
}
```

---

## Benefits

- Mixes HTML and C#.
    
- Strongly typed views.
    
- Reusable layouts and partial views.
    
- Supports Tag Helpers.
    
- Easy integration with MVC.
    

---

## Common Interview Comparisons

### ViewData vs ViewBag vs TempData

| ViewData              | ViewBag         | TempData           |
| --------------------- | --------------- | ------------------ |
| Dictionary            | Dynamic Object  | Dictionary         |
| Current Request       | Current Request | Across Redirect    |
| Requires Type Casting | No Type Casting | Removed after Read |

---

### HTML Helper vs Tag Helper

| HTML Helper       | Tag Helper                |
| ----------------- | ------------------------- |
| C# Helper Methods | HTML Attributes           |
| Older Approach    | Preferred in ASP.NET Core |
| Less HTML-like    | More HTML-like            |

---

## Interview Answer

> Razor is the view engine in ASP.NET Core MVC that allows developers to combine HTML with C# code to generate dynamic web pages. It uses the `@` symbol for C# code and files with the `.cshtml` extension.

---

## Memory Trick

```text
Controller
      │
      ▼
Model
      │
      ▼
Razor View (.cshtml)
      │
      ▼
HTML
      │
      ▼
Browser
```