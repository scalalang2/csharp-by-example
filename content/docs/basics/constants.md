---
weight: 4
---

## Constants
변경할 수 없는(immutable) 변수를 상수라고 합니다.

C#에서 상수는 기본 타입만 지원하며 사용자가 클래스, 구조체, 배열 등으로 정의한 타입은 상수로 이용할 수 없습니다.

```csharp
const int Months = 12;
const int Weeks = 52;
const int Days = 365;

Console.WriteLine($"One year is {Days} days, {Weeks} weeks, or {Months} months.");
```