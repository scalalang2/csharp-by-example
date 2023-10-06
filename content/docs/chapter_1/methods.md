---
weight: 11
---

## Methods

객체지향 언어에선 객체에 속한 함수를 `메서드(Method)` 라는 이름으로 부릅니다.

{{< columns >}}

<br/>

리턴할 타입을 선언하고 `메서드명(파라미터)` 형태로 선언합니다.

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

`Value 타입`의 변수를 메서드의 파라미터로 넘기면 Call-by-value로 동작합니다. 

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

Call-by-reference로 동작하게 하려면 `ref` 키워드를 사용합니다.

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