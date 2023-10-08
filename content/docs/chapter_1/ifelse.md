---
weight: 6
---

## If/Else

If/Else statements are used to control the flow of a program.

{{< columns >}}
<br/>

This is the most basic usage of if/else statement.

<--->

```csharp
double temp = 13.0;

// output: It's cold
if (temp < 20.0) {
    Console.WriteLine("It's cold");
} else {
    Console.WriteLine("hmm, not bad.");
}
```
{{< /columns >}}

{{< columns >}}
<br />

The else if statement allows you to check multiple conditions at the same time.

Some modern languages allow you to omit semicolons, parentheses, and curly braces, but C# is a classic language that requires them.

<--->

```csharp
char ch = 'a';
if (char.IsUpper(ch)) {
    Console.WriteLine($"{ch} is an uppercase letter.");
} else if (char.IsLower(ch))  {
    Console.WriteLine($"{ch} is a lowercase letter.");
} else if (char.IsDigit(ch)) {
    Console.WriteLine($"{ch} is a digit.");
} else {
    Console.WriteLine($"{ch}, what is it?");
}
```
```sh
$ dotnet run
a is a lowercase letter.
```
{{< /columns >}}