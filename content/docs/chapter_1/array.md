---
weight: 8
---

## Array

Array is a data structure that stores a fixed-size sequential collection of elements of the same type.

{{< columns >}}

<br/>

You can declare an array with the following syntaxs.

The compiler determines the size of the array if you do not specify the size.

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

You can use **multi-dimensional arrays** by using commas to separate the dimensions.

Accessing elements of multi-dimensional array works in the following way.

It looks different from other programming languages.

You need to focus on the form of `map[i,j]`.

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

You cannot use `map[i][j]` to access elements of multi-dimensional array.

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

A **jagged array** is an array whose elements are themselves arrays. 

Jagged arrays are similar to multi-dimensional arrays, but the sizes of the inner arrays can vary.

<--->

```csharp
char[][] map = new char[2][];
map[0] = new char[] { 'H', 'e', 'l', 'l', 'o' };
map[1] = new char[] { 'W', 'o', 'r', 'l', 'd' };

map[0][4] = 'O';

// Output: HellO
Console.WriteLine(string.Join("", map[0]));
```

{{< /columns >}}

{{< columns >}}

<br/>

`System.Linq` namespace provides various useful **Methods** for arrays.

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

{{< columns >}}

<br/>

Fill an array with a specific value.

<--->

```csharp
int[] arr = new int[5];
Array.Fill(arr, int.MaxValue);
// output: 2147483647 2147483647 2147483647 2147483647 2147483647
Console.WriteLine(string.Join(" ", arr));
```

or

```csharp
var arr = Enumerable.Repeat(int.MaxValue, 5).ToArray();
Console.WriteLine(string.Join(" ", arr));
```

{{< /columns >}}