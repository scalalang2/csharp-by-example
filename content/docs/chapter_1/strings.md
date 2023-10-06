---
weight: 10
---

## Strings

문자열은 `string` 타입으로 표현하는데 실제로는 `System.String` 객체의 약어입니다.

문자열은 기본적으로 불변 타입이며 선언된 값의 변경이 불가능합니다.

{{< columns >}}

<br/>

이 연산은 내부적으론 새로운 객체를 만들어서 할당하고 기존 레퍼런스를 지웁니다.

<--->

```cs
string a = "Hello";
a += " World";
Console.WriteLine(a); // output: Hello World
```

{{< /columns >}}

{{< columns >}}

<br/>

`string` 대신에 `System.String` 으로 선언해도 됩니다.

<--->

```cs
System.String a = "Hello";
a += " World";
Console.WriteLine(a); // output: Hello World
```

{{< /columns >}}

{{< columns >}}

<br/>

`"""` 로 다중 라인 문자열을 만들 수 있습니다.

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