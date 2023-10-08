---
weight: 5
---

## Loop
{{< columns >}}
</br>

The while statement first checks the condition to determine whether to repeat the loop.

There is also the **do ~ while** syntax that first executes the code and then checks the condition.

<--->

```csharp
int count = 0;
while (count < 5) {
    Console.WriteLine(count);
    count++;
}
```
```sh
$ dotnet run
0
1
2
3
4
```

{{< /columns >}}

{{< columns >}}
<br />

for loop is an statement that repeats the code while the condition is true.

<--->

```csharp
for (int i = 0; i < 5; i++) {
    Console.WriteLine(i);
}
```

{{< /columns >}}

{{< columns >}}
<br />

Like C++, if there are no parentheses, the next line of code is recognized as the body of the for statement.

<--->

```csharp
for (int i = 0; i < 5; i++) 
    Console.WriteLine(i);
Console.WriteLine("End");
```
```sh
$ dotnet run
0
1
2
3
4
End
```

{{< /columns >}}

{{< columns >}}
<br/>

This example prints the alphabet from a to z.

<--->

```csharp
// output: abcdefghijklmnopqrstuvwxyz
for (char c = 'a'; c <= 'z'; c++) {
    Console.Write(c);
}
```
{{< /columns >}}

{{< columns >}}
<br/>

The foreach statement is used to iterate over all elements of an array or list.

<--->

```csharp
string[] foods = new string[3]{"🍕", "🌭", "🥪"};
foreach (string f in foods) {
    Console.WriteLine(f);
}
```
```sh
$ dotnet run
🍕
🌭
🥪
```

{{< /columns >}}