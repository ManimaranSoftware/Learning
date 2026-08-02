AWSTemplateFormatVersion: '2010-09-09'

Resources:
  MyLambda:
    Type: AWS::Lambda::Function
    Properties:
      FunctionName: DemoLambda
      Runtime: dotnet8
      Handler: MyApp::Function::FunctionHandler
      Role: arn:aws:iam::123456789012:role/LambdaRole
      Timeout: 30
      MemorySize: 512
      Code:
        S3Bucket: lambda-code
        S3Key: app.zip



**Program.cs**

```
var builder = Host.CreateApplicationBuilder(args);

builder.Services.AddAWSLambdaHosting(LambdaEventSource.RestApi);

var app = builder.Build();

app.Run();
```

**Function.cs**

```
public class Function
{
    public string FunctionHandler(string input)
    {
        return $"Hello {input}";
    }
}
```


In CloudFormation:

```
Handler: MyApp::MyApp.Function::FunctionHandler
```

Format:

```
<Assembly>::<Namespace.Class>::<Method>
```

For interviews, remember:

- `Program.cs` → Startup, DI, configuration.
- `FunctionHandler()` → Entry point executed by AWS Lambda.



from function handler where it will go

From `FunctionHandler()`, it goes to **your business logic**.

Typical flow:

```
API Gateway
      ↓
AWS Lambda
      ↓
FunctionHandler()
      ↓
Service Layer
      ↓
Repository
      ↓
Database / S3 / DynamoDB
      ↓
Return Response
```

Example:

```
public class Function
{
    private readonly EmployeeService _service = new();

    public async Task<string> FunctionHandler(string id)
    {
        return await _service.GetEmployee(id);
    }
}
```

```
public class EmployeeService
{
    public async Task<string> GetEmployee(string id)
    {
        // DB call
    }
}
```

**Interview one-liner:**

> **FunctionHandler() is the Lambda entry point. It receives the request, invokes the business/service layer, which accesses the repository/database, and returns the response.**