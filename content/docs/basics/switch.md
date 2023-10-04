---
weight: 7
---

## Switch

`switch` 구문은 다수의 조건을 평가하고 실행 구문을 결정하는데 이용합니다.

{{< columns >}}

<br/>
가장 기본적인 `switch` 구문의 형태입니다.

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

함수형 언어에서 자주 나오는 `패턴 매칭(Pattern Matching)` 을 이용할 수 있습니다.

패턴 매칭 종류도 여러개가 있는데, **너가 뭘 좋아할지 몰라서 다 준비했어** 느낌으로 별게 다 구현되어 있습니다.

Java가 기본적으로는 객체 지향 언어이지만 함수형 느낌을 내기 위해 조미료가 추가된 것 처럼 C#도 비슷합니다.

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

관계 연산자 `<`, `>`, `<=`, `>=` 를 사용할 수 있습니다.

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

`or`, `and` 등의 논리 연산자를 사용할 수 있습니다.

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