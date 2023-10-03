---
weight: 5
---

## Loop
{{< columns >}}
</br>
while 문은 일단 조건부터 확인하고 반복해서 반복해서 실행할 지 결정 합니다.

먼저, 코드부터 실행하고 다음에 조건을 확인하는 `do ~ while` 문법도 있습니다.

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
for loop 를 이용해서 동일한 출력을 만듭니다.

<--->

```csharp
for (int i = 0; i < 5; i++) {
    Console.WriteLine(i);
}
```

{{< /columns >}}

{{< columns >}}
<br />
C++과 마찬가지로 괄호가 없으면 다음에 나오는 코드 한 줄을 for 구문의 body 로 인식하는군요

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
a부터 z까지 출력하는 것도 됩니다.
<--->
```csharp
for (char c = 'a'; c <= 'z'; c++) {
    Console.Write(c);
}
```
```sh
$ dotnet run 
abcdefghijklmnopqrstuvwxyz
```
{{< /columns >}}

{{< columns >}}
<br/>
foreach 문은 배열이나 리스트의 모든 요소를 순회할 때 사용합니다.

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