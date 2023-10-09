---
weight: 12
---

## List

List is a dynamic size linear data structure. In C#, we use `List<T>` class.

{{< columns >}}

<br />

`Add` function is used to add a value to the list, and `Remove` function is used to remove a specific value.

`FindAll` function can be used to find values that meet certain conditions, and as a language of the **MZ generation**, it supports lambda expressions.

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

Dictionary is a key-value data structure, In some other languages, it's called a map, HashMap, or HashTable.

{{< columns >}}

<br/>

You need to declare a type for the key and the value `Dictionary<Key, Value>`.

You can put a value in the dictionary by using the `Add` function.

You can access the value as same way as an array.

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

You can add and modify data in the form of `dict[key] = value`.

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

An error occurs when you try to access a key that does not exist.

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

Stack is a data structure that follows the rule of First-In Last-Out.

{{< columns >}}

<br/>

The **Push(value)** function adds a value to the top of a stack, and the **Pop()** function removes the value at the top of the stack.

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
Queue is a data structure that follows the rule of First-In First-Out.

{{< columns >}}

<br/>

The queue supports two fundamental operations **Enqueue** and **Dequeue**.

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

Priority Queue is a data structure that the data with higher priority comes out first.

{{< columns >}}

<br/>

There are two fundamental operations **Enqueue** and **Dequeue**.

It's declared in the form of `PriorityQueue<Value, Priority>`, where Value is the value and Priority is the priority.

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