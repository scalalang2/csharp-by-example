---
weight: 10
---

## Inheritance
Inheritance is an important feature of Object Oriented Programming. It enables you to create a new class while reusing the members of other classes. The class whose members are inherited is called the **base class** and the class that inherits those members is called the **derived class**.

{{< columns >}}

<br />

Duck and Penguin classes inherit from Bird class, both have the `Fly` method which is derived from the Bird class.

Note that **we can re-use common methods** in the derived classes without having to rewrite them.

<--->

```cs
public class Bird{
    public void Fly(){
        Console.WriteLine("A bird is flying");
    }
}

public class Duck : Bird{
    public void Quack(){
        Console.WriteLine("A duck is quacking");
    }
}

public class Penguin : Bird{
    public void Swim(){
        Console.WriteLine("A penguin is swimming");
    }
}


public class Program{
    public static void Main(string[] args){
        var bird = new Bird();
        bird.Fly();

        var duck = new Duck();
        duck.Quack();   // output: A duck is quacking
        duck.Fly();     // output: A bird is flying

        var penguin = new Penguin();
        penguin.Swim();
        penguin.Fly();
    }
}
```

{{< /columns >}}

{{< columns >}}

<br/>

The following example shows that Car, Truck, and Bycicle classes inherit the Vehicle class.

- They overrides the `Move` method, overriding is a rewriting of the method in the base class.
- Only `virtual` methods can be overridden.
- we can call members of the base class with `base` keyword. It's equivalent to `super` keyword in Java.

<--->

```cs
public class Vehicle
{
    public int Speed { get; set; }
    public virtual void Move()
    {
        Console.WriteLine($"Vehicle move {Speed} per second");
    }
}

public class Car : Vehicle
{
    public Car()
    {
        Speed = 10;
    }
    public override void Move()
    {
        Console.WriteLine($"Car move {Speed} per second");
        base.Move();
    }
}

public class Truck : Vehicle
{
    public Truck()
    {
        Speed = 5;
    }
    public override void Move()
    {
        Console.WriteLine($"Truck move {Speed} per second");
        base.Move();
    }
}

public class Bycicle : Vehicle
{
    public Bycicle()
    {
        Speed = 2;
    }
    public override void Move()
    {
        Console.WriteLine($"Bycicle move {Speed} per second");
        base.Move();
    }
}
```

{{< /columns >}}

{{< columns >}}

<br/>

They can be treated as `Vehicle` type. 

I hope you already know about **Polymorphism**.

<--->

```cs
List<Vehicle> vehicles = new List<Vehicle>();
vehicles.Add(new Car());
vehicles.Add(new Truck());
vehicles.Add(new Bycicle());

foreach (var vehicle in vehicles) {
    vehicle.Move();
}
// output:
// Car move 10 per second
// Vehicle move is called
// Truck move 5 per second
// Vehicle move is called
// Bycicle move 2 per second
// Vehicle move is called
```

{{< /columns >}}

{{< columns >}}

<br/>

A class can only inherit from one base class.

<--->

```cs
public class A {}
public class B : A {}
public class C : A {}

// ERROR! Multiple inheritance is not allowed
public class D : B, C {}
```

{{< /columns >}}