---
weight: 6
---

## Constructor
Constructors are methods with the same name as the class. They are used to initialize the state of an object and they works with the `new` keyword.

{{< columns >}}

<br/>

Post class has a constructor that takes two parameters: `title` and `description`

<--->

```csharp
public class Post
{
    private string title;
    private string description;
    
    public Post(string title, string description)
    {
        this.title = title;
        this.description = description;
    }

    public void Show()
    {
        Console.WriteLine(title);
        Console.WriteLine("-----------------");
        Console.WriteLine(description);
    }
}
```

{{< /columns >}}

{{< columns >}}

<br/>

Let's create an object of Post class with initial values for title and description.

<--->

```csharp
var intro = new Post("Introduction", "This is my first post");
intro.Show();
// output:
// Introduction
// -----------------
// This is my first post
```

{{< /columns >}}

{{< columns >}}

<br/>

Class can have multiple constructors if the signature of the methods are different each other.

<--->

```csharp
public class Post
{
    private string title;
    private string description;

    public Post()
    {
        this.title = "Empty";
        this.description = "Empty";
    }

    public Post(string title)
    {
        this.title = title;
        this.description = "Empty";
    }
    
    public Post(string title, string description)
    {
        this.title = title;
        this.description = description;
    }
}
```

{{< /columns >}}