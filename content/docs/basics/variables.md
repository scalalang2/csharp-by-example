---
weight: 3
bookToc: false
---

{{< columns >}}
## Variables

변수 선언은 타입명 다음에 변수명을 적습니다.

출력할 때 `$ sign`을 이용하면 문자열 안에 변수를 사용할 수 있습니다.

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
```

```shell
DoHyeon.
1.8m.
not married.
30
```
{{< /columns >}}