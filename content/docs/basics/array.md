---
weight: 8
---

## Array

배열은 동일한 타입의 값들을 하나의 변수에 저장하기 위한 자료구조이죠.

고정된 크기를 가지고 있으며, 배열의 크기는 선언할 때 정해줍니다.

{{< columns >}}

<br/>
배열의 선언과 사용 방법입니다.

C++과 비슷한데 배열의 크기를 꼭 고정시킬 필요는 없고 컴파일 타임에 결정됩니다.

<--->

```csharp
string[] weekdays = {"Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"};
int[] arr = new int[5];
arr[0] = 10;

Console.WriteLine(weekdays[1]); // output: Tue
Console.WriteLine(arr[0]); // output: 10
``` 

{{< /columns >}}

{{< columns >}}

<br/>

쉼표를 기준으로 **다차원(Multi-dimensional)** 배열을 선언하고 사용할 수 있습니다.

다차원 배열의 원소에 접근할 때, `map[i, j]` 이렇게 이용함에 유의하세요.

다른 언어의 배열 안의 배열을 선언하는 방식의 2차원 배열과는 컨셉이 다릅니다.

<--->

```csharp
char[,] map = {
    {'.', '.', 'E'},
    {'.', '#', '.'},
    {'S', '#', '#'},
};

for (int i = 0; i < map.GetLength(dimension:0); i++) {
    for (int j = 0; j < map.GetLength(dimension:1); j++) {
        Console.Write($"{map[i, j]}");
    }
    Console.WriteLine();
}

// Output:
// . . E
// . # .
// S # #
```

{{< /columns >}}

{{< columns >}}

<br/>

다차원 배열로 선언한 변수는 C++처럼 `map[i][j]` 의 형태로 사용할 수 없습니다. 

<--->

```csharp
char[,] map = {
    {'.', '.', 'E'},
    {'.', '#', '.'},
    {'S', '#', '#'},
};

// ❌ compile error
map[0][0] = 'X';
```

{{< /columns >}}

{{< columns >}}

<br/>

C++ 처럼 배열의 원소가 배열이 되는 배열을 C#에서는 `Jagged Array` 라고 부르더군요. 

이렇게 선언해서 사용합니다. 다만, 원소가 되는 배열의 크기를 정할 수는 없습니다.

<--->

```csharp
char[][] map = new char[2][];
map[0] = new char[] { 'H', 'e', 'l', 'l', 'o' };
map[1] = new char[] { 'W', 'o', 'r', 'l', 'd' };

map[0][4] = 'O';

// Output: HellO
Console.WriteLine(string.Join("", map[0])); // 이제 여기서는 map[0] 처럼 0번째 원소에 접근해서 배열을 리턴합니다.
```

{{< /columns >}}

{{< columns >}}

<br/>

`System.Linq` 네임스페이스는 배열에 다양한 **메서드**를 제공합니다.

배열이 직접 제공하는 메서드는 아니고 기존 클래스를 확장할 수 있는 기능이 있나봅니다.

<--->

```csharp
using System.Linq;

int[] arr = {1,4,7,3,2,4,1};

Console.WriteLine($"sum: {arr.Sum()}"); // 22
Console.WriteLine($"avg: {arr.Average()}"); // 3.1428..
Console.WriteLine($"min: {arr.Min()}"); // 1
Console.WriteLine($"max: {arr.Max()}"); // 7

// slice 처럼 이용
// output: 7 3 
Console.WriteLine(string.Join(" ", arr.Skip(2).Take(2).ToList())); 
```

{{< /columns >}}