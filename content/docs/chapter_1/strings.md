---
weight: 10
---

## Strings

In C#, strings are represented by the `string` type, which is actually an abbreviation for the `System.String` object.

Strings are immutable by default, meaning that the value of a string cannot be changed once it is declared.

{{< columns >}}

<br/>

In this example, the `+=` operator is used to append the string "World" to the end of the string "Hello". 

Actually, this creates a new string object, and then the original string object is discarded.

<--->

```cs
string a = "Hello";
a += " World";
Console.WriteLine(a); // output: Hello World
```

{{< /columns >}}

{{< columns >}}

<br/>

This is the same as the previous example, but it uses the full System.String type instead of the abbreviated string type.

<--->

```cs
System.String a = "Hello";
a += " World";
Console.WriteLine(a); // output: Hello World
```

{{< /columns >}}

{{< columns >}}

<br/>

You can use `"""` syntax to create a multiline string.

<--->

```cs
string body = """
{
    "name": "John",
    "age": 30
}
""";
Console.WriteLine(body);
```

{{< /columns >}}