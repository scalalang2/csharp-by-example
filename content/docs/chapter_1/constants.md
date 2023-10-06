---
weight: 4
bookToc: false
---

{{< columns >}}
## Constants
변경할 수 없는(immutable) 변수를 상수라고 합니다.

C#에서 상수는 기본 타입만 지원하며 사용자가 클래스, 구조체, 배열 등으로 정의한 타입은 상수로 이용할 수 없습니다.

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

---

{{< columns >}}
## 기본 타입 (Built-in Types)
상수로 사용할 수 있는 기본 타입은 우측 표와 같습니다. [출처](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types)

<--->

| Keywords | - | - |
| ------- | ------- | -------- |
| bool | byte | sbyte |
| char | decimal | double |
| float | int | uint |
| nint | nuint | long |
| ulong | short | ushort |
| string | | |

{{< /columns >}}