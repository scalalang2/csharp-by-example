---
weight: 9
---

## Properties
Properties make sure that data is hidden from other classes. 
       
Properties can be used to achieve **encapsulation**, which is the hiding of sensitive data from users and providing a controlled way to access it.

More specifically, the other classes cannot directly access the members of an object, but must use the geeter and setter that are provided.

{{< columns >}}

<br/>

Vehicle class enables users to read position data, but does not allow them to update it directly.

The position can only be updated by the Move method.

<--->

```cs
public class Vehicle
{
    public int X { get; private set; }
    public int Y { get; private set; }
    
    public Vehicle(int x, int y)
    {
        X = x;
        Y = y;
    }
    
    public void Move(int x, int y)
    {
        X += x;
        Y += y;
    }
}

class Program
{
    public static void Main(string[] args)
    {
        var car = new Vehicle(0, 0);
        // ERROR - you can't update the `X` field directly.
        car.X = 10;
        // you can only update the position by Move method
        car.Move(10, 10);
    }
}
```

{{< /columns >}}

{{< columns >}}

<br/>

The `_x` and `_y` fields are private and hidden and they can only be accessed through the `X` and `Y` properties. This is called **encapsulation**.

Moreover, When invalid value is given to update the position, an exception is thrown.

<--->

```cs
public class Vehicle
{
    private int _x = 0;
    private int _y = 0;

    public int X
    {
        get => _x;
        set
        {
            if (value < 0)
                throw new ArgumentException("invalid position");
            _x = value;
        }
    }
    
    public int Y
    {
        get => _y;
        set
        {
            if (value < 0)
                throw new ArgumentException("invalid position");
            _y = value;
        }
    }
}
public class Program
{
    public static void Main(string[] args)
    {
        var car = new Vehicle();
        car.X = 10;
        Console.WriteLine(car.X);
        Console.WriteLine(car.Y);

        // this will throw an exception
        car.X = -1;
    }
}
```

{{< /columns >}}