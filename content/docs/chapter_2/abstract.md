---
weight: 11
---

## Abstract
Abstract class cannot be instantiated as object. It must be inherited by another class to use.

- Abstract class can have abstract methods(without body) and non-abstract methods(with-body).
- abstract methods must be implemented in the derived class.

{{< columns >}}

<br/>

Shape is an abstract class, so that we can't create an object of Shape class.

Rectangle class inherits from Shape class, It must override the `GetArea` method because it has nothing to run in the base class.

<--->

```cs
abstract class Shape {
    // abstract method
    public abstract int GetArea();

    // non-abstract method
    public void Draw() {
        Console.WriteLine($"Area: {GetArea()}");
    }
}

class Rectangle : Shape {
    public int Width;
    public int Height;
    
    public override int GetArea() {
        return Width * Height;
    }
}
```

{{< /columns >}}