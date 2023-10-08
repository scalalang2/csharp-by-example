---
weight: 4
bookToc: false
---

{{< columns >}}
## Constants

Constant is an immutable variable. 

In C#, constants are only supported for built-in types. You can't use it for user-defined types such as classes, structs, arrays, and etc.

<--->
```csharp
const int Months = 12;
const int Weeks = 52;
const int Days = 365;

Console.WriteLine($"One year is {Days} days, {Weeks} weeks, or {Months} months.");
```

```shell
$ dotnet run
One year is 365 days, 52 weeks, or 12 months.
```
{{< /columns >}}