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

`_title` field is private and hidden and it can only be accessed through the `Title` property. This is called **encapsulation**.

<--->

```cs
public class Post
{
    private string _title;

    public string Title
    {
        get { return _title; }
        set { _title = value; }
    }
}

public class Program
{
    public static void Main(string[] args)
    {
        var post = new Post();
        post.Title = "Hello World!";
        Console.WriteLine(post.Title);
    }
}
```

{{< /columns >}}