---
weight: 7
---

## Initializer
{{< columns >}}

<br/>

You can set fields of an object without defining multiple constructors.

<--->

```csharp
public class Post
{
    public string Title;
    public string Description;
}

class Program
{
    public static void Main(string[] args)
    {
        Post post = new Post()
        {
            Title = "My First Post",
            Description = "Hello World!"
        };
        Console.WriteLine(post.Title);
        Console.WriteLine(post.Description);
    }
}
```

{{< /columns >}}
{{< columns >}}

<br/>

It doesn't work with private fields

<--->

```csharp
public class Post
{
    private string Title;
    private string Description;
}

class Program
{
    public static void Main(string[] args)
    {
        Post post = new Post()
        {
            // Oops. compile error
            Title = "My First Post",
            Description = "Hello World!"
        };
    }
}
```

{{< /columns >}}
