
## Testing Basics
- Ensures Application Quality
- Detects Bugs Early
- Improves Maintainability
- Enables Safe Refactoring

> [!tip]
> **Memory Tip:** Test Early, Fix Early

---

## Types of Testing
- Unit Testing
- Integration Testing
- Functional Testing
- System Testing
- End-to-End (E2E) Testing

---

## Unit Testing
- Tests Individual Method/Class
- Fast Execution
- Independent
- No Database
- No External APIs

---

## Integration Testing
- Tests Multiple Components Together
- Database Integration
- API Integration
- External Service Integration

---

## Unit Test Frameworks
- `xUnit`
- `NUnit`
- `MSTest`

> [!tip]
> **Memory Tip:** `xUnit` is the most common framework in modern .NET projects.

---

## Arrange-Act-Assert (AAA)
- Arrange → Prepare Test Data
- Act → Execute Method
- Assert → Verify Result

---

## Mocking
- Replace External Dependencies
- Isolate Unit Tests
- Test Business Logic Only
- Common Library → `Moq`

---

## Test Doubles
- Dummy
- Stub
- Mock
- Fake
- Spy

---

## Assertions
- `Assert.Equal()`
- `Assert.True()`
- `Assert.False()`
- `Assert.NotNull()`
- `Assert.Throws()`

---

## Dependency Injection & Testing
- Mock Interfaces
- Constructor Injection
- Easier Unit Testing
- Loose Coupling

---

## Code Coverage
- Measures Tested Code
- Higher Coverage ≠ Better Tests
- Focus on Critical Business Logic

---

## API Testing
- `Postman`
- Swagger
- Verify Status Codes
- Verify Response Body
- Verify Validation

---

## Performance Testing
- Load Testing
- Stress Testing
- Spike Testing
- Endurance Testing
- Common Tool → `JMeter`

---

## Best Practices
- One Test → One Scenario
- Keep Tests Independent
- Meaningful Test Names
- Mock External Dependencies
- Avoid Hardcoded Data
- Test Positive & Negative Scenarios

---

## Interview Traps
- Unit Testing vs Integration Testing
- Mock vs Stub
- `xUnit` vs `NUnit`
- Mocking vs Dependency Injection
- Code Coverage vs Test Quality
- Load Testing vs Stress Testing
- Fake vs Mock
- Arrange vs Act vs Assert

---

## 30-Second Revision Formula

Testing Basics → Types → Unit Testing → Integration Testing → Frameworks → AAA → Mocking → Test Doubles → Assertions → DI → Code Coverage → API Testing → Performance Testing → Best Practices