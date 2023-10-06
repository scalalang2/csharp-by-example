---
weight: 12
---

## List

List는 동적인 크기를 가진 선형 자료구조를 말합니다. C#에서는 `List<T>` 클래스를 사용합니다.

{{< columns >}}

<br />

`Add` 함수로 값을 추가하고 `Remove` 함수로 특정 값을 제거합니다.

`FindAll` 함수로 특정 조건에 맞는 값을 찾을 수 있는데, MZ세대의 언어 답게 람다식을 지원합니다.

<--->

```csharp
void debug(List<int> number) {
    Console.WriteLine(string.Join(" ", number));
}

List<int> number = new List<int>() {1, 2, 3};
number.Add(4);
debug(number); // output: 1 2 3 4
debug(number.FindAll(i => i % 2 == 0)); // output: 2 4

number.Remove(3);
debug(number); // output: 1 2 4
```

{{< /columns >}}

---

## Dictionary

Dictionary는 키-밸류 자료구조입니다.

내부적으로 해시테이블로 구현되어 있으며 선언할 때 타입을 명시합니다.

{{< columns >}}

<br/>

객체를 생성할 때 타입을 명시합니다. 

`Add` 함수로 값을 추가합니다.

`<var>[<key>]` 문법으로 키에 저장된 데이터를 불러옵니다.

<--->

```csharp
Dictionary<string, string> dict = new Dictionary<string, string>();
dict.Add("k1", "hello");
dict.Add("k2", "world");

Console.WriteLine(dict["k1"]); // output: hello
```

{{< /columns >}}

{{< columns >}}

<br/>

`<var>[<key>] = <value>` 형태로 데이터를 추가하고 수정할 수 있습니다.

<--->

```csharp
Dictionary<string, string> dict = new Dictionary<string, string>();
dict["k1"] = "hello";
dict["k2"] = "world";
Console.WriteLine(dict["k1"]); // output: hello

dict["k1"] = "halo";
Console.WriteLine(dict["k1"]); // output: halo
```

{{< /columns >}}

{{< columns >}}

<br/>

존재하지 않는 키에 접근하면 예외를 발생합니다.

<--->

```csharp
Dictionary<string, string> phoneNumbers = new Dictionary<string, string>();
phoneNumbers["david"] = "010-XXXX-XXXX";

// Exception occured: The given key 'scalalang' was not present in the dictionary.
try {
    Console.WriteLine($"a phone number of scalalang: {phoneNumbers["scalalang"]}");
} catch (Exception e) {
    Console.WriteLine("Exception occured: {0}", e.Message);
}
```

{{< /columns >}}

---

## Stack
스택은 선입후출(First-In Last-Out)의 자료구조이죠.

가끔 필요할 때가 있습니다.

{{< columns >}}

<br/>

`Push` 함수로 값을 추가하고 `Pop` 함수로 값을 빼옵니다.

<--->

```csharp
Stack<string> names = new Stack<string>();
names.Push("John");
names.Push("Peter");
names.Push("Mark");
Console.WriteLine(names.Peek()); // output: Mark
names.Pop();
Console.WriteLine(names.Peek()); // output: Peter
Console.WriteLine(names.Count);  // output: 2
```

{{< /columns >}}

---

## Queue
큐는 선입선출(First-In First-Out)의 자료구조입니다.

{{< columns >}}

<br/>

`Enqueue` 함수로 값을 추가하고 `Dequeue` 함수로 값을 빼옵니다.

일단, 중요한 건 이런 자료구조를 기본으로 제공한다는 거죠

<--->

```csharp
Queue<int> queue = new Queue<int>();
queue.Enqueue(1);
queue.Enqueue(2);
queue.Enqueue(3);
queue.Enqueue(4);

// output: 1 2 3 4
while (queue.Count > 0) 
    Console.WriteLine(queue.Dequeue()); 
```

{{< /columns >}}

---

## Priority Queue
우선순위 큐는 우선순위가 높은 데이터가 먼저 나오는 자료구조이구요 보통 힙(heap)으로 구현합니다.

{{< columns >}}

<br/>

큐와 비슷하게 `Enqueue`, `Dequeue` 함수를 이용합니다.

Generic 타입의 첫번째로는 값을 두번째로는 우선순위 타입을 결정하고요.

낮은 값을 기준으로 먼저 나옵니다. 힙으로 구현되어서 연산마다 시간복잡도는 O(logN)입니다.

<--->

```csharp
var queue = new PriorityQueue<string, int>();
queue.Enqueue("Task A", 1);
queue.Enqueue("Task B", 4);
queue.Enqueue("Task C", 2);
queue.Enqueue("Task D", 7);
queue.Enqueue("Task E", 3);

while (queue.Count > 0) {
    var task = queue.Dequeue();
    Console.WriteLine($"Task: {task}");
}

```

{{< /columns >}}