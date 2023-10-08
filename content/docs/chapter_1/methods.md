---
weight: 11
---

## Methods

In object-oriented languages, functions belonging to an object are called **Methods**. You can think of it like a function like other programming language.

{{< columns >}}

<br/>

The method declaration specifies return type, method name, and parameters.

<--->

```csharp
int Add(int x, int y) {
    return x + y;
}

Console.WriteLine(Add(1, 2));
```

{{< /columns >}}

{{< columns >}}

<br/>

리턴할 게 없으면 `void` 타입으로 선언합니다.

<--->

```csharp
void Greeting(string name) {
    Console.WriteLine($"Hello {name}");
}

// output: Hello scalalang2
Greeting("scalalang2");
```

{{< /columns >}}

{{< columns >}}

<br/>

**void** means that the method does not return a value.

<--->

```csharp
void Swap(int a, int b) {
    int temp = a;
    a = b;
    b = temp;
}

int x, y;
x = 10;
y = 25;

Console.WriteLine("x:{0}, y:{1}", x, y); // x:10, y:25
Swap(x, y);
Console.WriteLine("x:{0}, y:{1}", x, y); // x:10, y:25
```

{{< /columns >}}

{{< columns >}}

<br/>

To make it work as call-by-reference, use the **ref** keyword.

<--->

```csharp
void Swap(ref int a, ref int b) {
    int temp = a;
    a = b;
    b = temp;
}

int x, y;
x = 10;
y = 25;

Console.WriteLine("x:{0}, y:{1}", x, y); // x:10, y:25
Swap(ref x, ref y);
Console.WriteLine("x:{0}, y:{1}", x, y); // x:25, y:10
```

{{< /columns >}}