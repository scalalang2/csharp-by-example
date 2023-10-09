---
weight: 5
---

## Class
Class is a core building block of object-oriented programming.

An application consists of various classes that interact with each other through objects.

{{< columns >}}

<br/>

A class has two fundamental components, **data** and **behavior**.
- Data is represented by **fields**.
- Behavior is represented by **methods**.

Each fields or methods have an **access modifier** that controls its visibility. It defines whether they can be accessed from other code.

<--->

```csharp
public class Person {
    public string Name;
    public void Greetings() {
        Console.WriteLine($"Hi, I'm {Name}");
    }
}
```

{{< /columns >}}
{{< columns >}}

<br/>

Class is nothing but a blueprint for creating objects.

You need to create an instance of class which is called **object**.

It can be done by using the **new** keyword.

<--->

```csharp
var p1 = new Person();
p1.Name = "John";
// output: Hi, I'm John
p1.Greetings();

Person p2 = new Person();
p2.Name = "David";
// output: Hi, I'm David
p2.Greetings();
```

{{< /columns >}}
{{< columns >}}

<br/>

Static class is used to represents the concept is a singleton object.

The static class is not allowed to create objects, It can only contain static fields and methods.

- Singleton object: an object that can only be instantiated once.
- The `WriteLine` method is a static member of `Console` class.

<--->

```csharp
public static class Console {
    public static void WriteLine(){
        Out.WriteLine();
    }
}
```

{{< /columns >}}