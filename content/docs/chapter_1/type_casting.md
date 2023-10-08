---
weight: 9
---

## Type Casting
C# is a statically typed language and the type of variable is determined at compile time.

You cannot assign a variable to other one with different types. But, you can explicitly convert the type of a variable, we calls it **Type Casting**.

{{< columns >}}

<br/>

In some cases, implicit type conversion is allowed. For example, the int type can be implicitly converted to the long type because long has a larger range of values than int.

<--->

```cs
int A = 100;
long B = A;
Console.WriteLine(B); // output: 100
```

{{< /columns >}}

{{< columns >}}

<br/>

You cannot use the () operator to convert a string type to a numeric type. Instead, you can use the **Parse()** method.

<--->

```cs
string num = "123";
int a = int.Parse(num);
Console.WriteLine(a); // output: 123
```

{{< /columns >}}

{{< columns >}}

<br/>

If you try to convert a value that is not a number, a runtime error will occur.

<--->

```cs
string num = "abc";

// System.FormatException: 
// The input string 'abc' was not in a correct format.
int a = int.Parse(num);
Console.WriteLine(a); 
```

{{< /columns >}}