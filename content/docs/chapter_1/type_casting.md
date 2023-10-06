---
weight: 9
---

## Type Casting
C#은 컴파일 타임에 타입이 결정되는 정적 타입 언어이기 때문에 동일한 변수를 다른 타입으로 선언하거나
다른 타입의 변수로 할당하는게 제한되어 있습니다. 하지만, 명시적으로 탕비을 변환하는 건 가능하고 이를 캐스팅이라고 합니다.

{{< columns >}}

<br/>

묵시적으로 타입 변환이 허용되는 경우가 있습니다. 

`long`은 `int`보다 더 큰 수의 범위를 표현하기 때문에 이는 항상 타입 변환이 가능합니다.

이 뿐만 아니라 객체 지향쪽으로 넘어가면 자식 클래스는 부모 클래스로 묵시적으로 타입 변환이 가능한 부분이 있는데 이건 나중에 알아보죠.

<--->

```cs
int A = 100;
long B = A;
Console.WriteLine(B); // output: 100
```

{{< /columns >}}

{{< columns >}}

<br/>

`double` 타입을 `int` 형으로 형변환 합니다.

기본 타입 간 형 변환이 가능한 타입이 굳이 궁금하면 [이 표](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/numeric-conversions#explicit-numeric-conversions) 에서 확인할 수 있습니다.

<--->

```cs
double a = 27.3;
int b;
b = (int) a;
Console.WriteLine(b); // output: 27
```

{{< /columns >}}

{{< columns >}}

<br/>

위 문법으로 `string` 타입을 `int` 형으로 형변환 하는 건 안됩니다.

대신, `Parse` 함수를 이용할 수 있습니다.

<--->

```cs
string num = "123";
int a = int.Parse(num);
Console.WriteLine(a); // output: 123
```

{{< /columns >}}

{{< columns >}}

<br/>

숫자가 아닌 값을 변환하면 런타임 에러가 발생합니다.

<--->

```cs
string num = "abc";

// System.FormatException: 
// The input string 'abc' was not in a correct format.
int a = int.Parse(num);
Console.WriteLine(a); 
```

{{< /columns >}}