---
weight: 7
---

## Switch

Switch statements are used to evaluate multiple conditions and determine the code to execute.

{{< columns >}}

<br/>

This is the basic form of a switch statement.

<--->

```csharp
char op = '*';
int a = 2;
int b = 3;

// output: 6
switch (op) {
    case '+':
        Console.WriteLine(a + b);
        break;
    case '*':
        Console.WriteLine(a * b); 
        break;
    case '-':
        Console.WriteLine(a - b);
        break;
    case '/' :
        Console.WriteLine(a / b);
        break;
    default:
        Console.WriteLine("invalid operator");
        break;
}
```

{{< /columns >}}

{{< columns >}}

<br/>

In C#, pattern matching is supported in switch statements.
<--->

```csharp
char op = '*';
int a = 2;
int b = 3;

int result = op switch {
    '+' => a + b,
    '-' => a - b,
    '*' => a * b,
    '/' => a / b,
    _ => throw new ArgumentException("invalid operator")
};
Console.WriteLine(result); // output: 6
```

{{< /columns >}}

{{< columns >}}

<br/>

Relational operators can be used in switch statements to compare a value to a constant.

<--->

```csharp
double temp = 13.3;

// output: It's cold!
switch (temp) {
    case < 20:
        Console.WriteLine("It's cold!");
        break;
    case > 36:
        Console.WriteLine("it's hot!");
        break;
    default:
        Console.WriteLine("good");
        break;
}
```

{{< /columns >}}

{{< columns >}}

<br/>

Logical operators can also be used in switch statements.

<--->

```csharp
Console.WriteLine(season(new DateTime(2021, 1, 19)));  // output: winter
Console.WriteLine(season(new DateTime(2021, 10, 9)));  // output: autumn
Console.WriteLine(season(new DateTime(2021, 5, 11)));  // output: spring

static string season(DateTime date) => date.Month switch
{
    3 or 4 or 5 => "spring",
    6 or 7 or 8 => "summer",
    9 or 10 or 11 => "autumn",
    12 or 1 or 2 => "winter",
    _ => throw new Exception("invalid"),
};
```

{{< /columns >}}