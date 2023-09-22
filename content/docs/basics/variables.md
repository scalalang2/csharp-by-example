---
weight: 3
---

## Variables

변수 선언은 타입명 다음에 변수명을 적습니다.

```csharp
string id = "DoHyeon";
int age = 29;
double height = 1.8;
bool isMarried = false;
char myFavoriteLetter = 'P';

Console.WriteLine($"My name is {id}.");
Console.WriteLine("My height is " + height + "m.");
Console.WriteLine($"I am {(isMarried ? "married" : "not married")}.");
Console.WriteLine($"Next year, I will be {age + 1} years old.");
```

```bash
My name is DoHyeon.
My height is 1.8m.
I am not married.
Next year, I will be 30 years old.
```

출력할 때 `$ sign`을 이용하면 문자열 안에 변수를 사용할 수 있습니다.

## Types

다음 표는 C#에서 Simple Types 라고 부르는 기본 자료형들입니다.

| Type | Description |
| --- | --- |
| `char` | 16-bit unicode character |
| `bool` | Boolean type |
| `byte` | 8-bit unsigned integer |
| `int` | 32-bit 정수형 타입 |
| `long` | 64-bit 정수형 타입 |
| `double` | 64-bit double-precision 부동 소수점 |
| `float` | 32-bit single-precision 부동 소수점 |
| `decimal` | 128-bit 의 높은 정밀도를 가짐 |
| `string` | 문자열 |

더 자세한 내용은 [.NET 공식 C# 레퍼런스 문서](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/types)에서 확인할 수 있습니다. 

하지만, 지금은 굳이 안보셔도 됩니다.

Next Examples : [Constants](/docs/basics/constants/)