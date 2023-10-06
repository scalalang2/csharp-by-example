---
weight: 15
---

## Date Time

프로그래밍 하면서 시간을 다루는 일이 많죠.

{{< columns >}}

<br/>

`DateTime` 객체를 이용합니다.

비교 연산 및 사칙연산을 지원합니다.

`ToString` 으로 포맷팅을 합니다.

<--->

```csharp
var dt1 = new DateTime(2023, 10, 6);
var dt2 = new DateTime(2023, 1, 1);
Console.WriteLine(dt1 < dt2);     // False
Console.WriteLine(dt1.DayOfWeek); // Friday
Console.WriteLine(DateTime.Now.ToString("yyyy-M-dd hh:mm:ss"));
```

{{< /columns >}}

{{< columns >}}

<br/>

`TimeSpan` 은 시간 간격(Interval)을 표현하는 객체이고, Duration 등을 표현할 때 사용합니다.

사칙연산으로 DateTime 객체에 더하거나 뺄 수 있습니다.

<--->

```csharp
var dt1 = new DateTime(2023, 10, 6);
var dt2 = dt1 + new TimeSpan(days:1, hours:0, minutes:0, seconds: 0);
var dt3 = dt1 - new TimeSpan(days:1, hours:0, minutes:0, seconds: 0);
Console.WriteLine(dt2.DayOfWeek); // Saturday
Console.WriteLine(dt3.DayOfWeek); // Thursday
```

{{< /columns >}}