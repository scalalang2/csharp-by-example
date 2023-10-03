---
weight: 6
---

## If/Else

If/Else 구문은 프로그램의 흐름을 제어하는데 이용합니다.

{{< columns >}}
<br/>
가장 기본적인 If/Else 구문 활용입니다.
<--->
```csharp
double temp = 13.0;
if (temp < 20.0) {
    Console.WriteLine("추워요");
} else {
    Console.WriteLine("살만하군");
}
```
```
$ dotnet run
추워요
```
{{< /columns >}}

{{< columns >}}
<br />

`else if` 로 여러 조건을 동시에 확인합니다. 

요즘 MZ세대의 언어들은 세미콜론`;`, 소괄호`(`,`)`, 중괄호`{`,`}` 를 생략해도 되는 경우가 있는데 C#은 클래식한 늘 먹던 그 맛이군요.

<--->

```csharp
char ch = 'a';
if (char.IsUpper(ch)) {
    Console.WriteLine($"{ch}는 대문자군요");
} else if (char.IsLower(ch))  {
    Console.WriteLine($"{ch}는 소문자군요");
} else if (char.IsDigit(ch)) {
    Console.WriteLine($"{ch}는 숫자군요");
} else {
    Console.WriteLine($"{ch}는 뭐죠?");
}
```
```sh
$ dotnet run
a는 소문자군요
```
{{< /columns >}}