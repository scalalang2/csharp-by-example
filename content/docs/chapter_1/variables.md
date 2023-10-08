---
weight: 3
bookToc: false
---

{{< columns >}}
## Variables

Variable declaration is written with the type name followed by the variable name.

You can use **$ sign** to use variables in a **string**.

<--->
```csharp
string id = "DoHyeon";
int age = 29;
double height = 1.8;
bool isMarried = false;

Console.WriteLine($"{id}.");
Console.WriteLine(height + "m.");
Console.WriteLine($"{(isMarried ? "married" : "not married")}.");
Console.WriteLine($"{age + 1}");
// output:
// DoHyeon.
// 1.8m.
// not married.
// 30
```
{{< /columns >}}

{{< columns >}}

<br/>

The compiler automatically infers the type of the variable with the `var` keyword.
<--->

```csharp
// compiler infers type of greeting as string
var greeting = "Hello World!"; 

// output: Hello, World!
Console.WriteLine(greeting); 
```

{{< /columns >}}