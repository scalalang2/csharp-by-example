---
weight: 15
---

## Date Time
{{< columns >}}

<br/>

`DateTime` object represents a point in time.

It supports comparison and arithmetic operations.

You can format it with `ToString` method.

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

`TimeSpan` object represents a time interval or duration.

You can add or subtract TimeSpan object to DateTime object.

<--->

```csharp
var dt1 = new DateTime(2023, 10, 6);
var dt2 = dt1 + new TimeSpan(days:1, hours:0, minutes:0, seconds: 0);
var dt3 = dt1 - new TimeSpan(days:1, hours:0, minutes:0, seconds: 0);
Console.WriteLine(dt2.DayOfWeek); // Saturday
Console.WriteLine(dt3.DayOfWeek); // Thursday
```

{{< /columns >}}

{{< columns >}}

<br/>

`Parse` function converts a string to a DateTime object.

<--->

```csharp
var dt = DateTime.Parse("2023-10-06 11:24:20");
Console.WriteLine(dt.ToLongDateString());
Console.WriteLine(dt.ToShortDateString());
Console.WriteLine(dt.ToLongTimeString());
Console.WriteLine(dt.ToShortTimeString());
```

{{< /columns >}}