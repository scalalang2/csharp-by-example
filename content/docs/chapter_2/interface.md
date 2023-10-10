---
weight: 12
---

## Interface
An interface is a blueprint for a class which means that it only must contains abstract methods.

Whereas a class can inherit from only one class, it can implement multiple interfaces.

- Like abstract classes, interfaces cannot be instantiated.
- Unlike abstract classes, interfaces do not contain fields.
- Interface can contain properties and methods.
  - Properties and fields are not the same thing!

{{< columns >}}

<br/>

Here is a classic example of an interface.

Animal interface defines unimplemented `Speak` method.

Interface can't have implemented methods.

<--->

```cs
interface Animal {
    void Speak();
}

class Dog : Animal {
    public void Speak() {
        Console.WriteLine("Woof!");
    }
}

class Cat : Animal {
    public void Speak() {
        Console.WriteLine("Meow!");
    }
}

class Program{
    public static void Main(string[] args){
        var dog = new Dog();
        dog.Speak(); // Woof!

        var cat = new Cat();
        cat.Speak(); // Meow!
    }
}
```

{{< /columns >}}