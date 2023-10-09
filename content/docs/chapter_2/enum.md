---
weight: 2
---

## Enums
An enumeration is a set of named integer constants. An enumerated type is declared using the enum keyword.

{{< columns >}}

<br />

You can access the enum values via dot notation.

It can be casted to an integer.

<--->

```csharp
enum Days { Sun, Mon, Tue, Wed, Thu, Fri, Sat };

class Program {
    public static void Main(string[] args)
    {
        var sat = Days.Sat;
        // output: Sat
        Console.WriteLine(sat);
        // output: 1
        Console.WriteLine((int) Days.Mon);
    }
}
```