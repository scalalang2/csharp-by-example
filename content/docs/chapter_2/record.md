---
weight: 4
---

## Record

In kotlin, `data class` is a class used to only hold data, sometimes It's called a **POJO** or **DTO(Domain Transfer Object)**.

C# also provides similar feature with `record` type.

Record type has following characteristics:
- Immutable
- Automatic Constructors
- Automatic Deconstructors
- Automatic `Equals` and `GetHashCode` implementations

{{< columns >}}

<br/>

Here is the basic example of `record` type.

<--->

```csharp
record User(string FirstName, string LastName);

class Program
{
    public static void Main(string[] args)
    {
        var user = new User("John", "Doe");
        var user2 = new User("John", "Doe");
        Console.WriteLine(user.ToString());
        Console.WriteLine(user.GetHashCode());
        Console.WriteLine(user == user2);

        // ERROR!: not allowed to change the value of record type
        // user.FirstName = "David";
    }
}
```

{{< /columns >}}

{{< columns >}}

<br/>

You can deconstruct the fields of record data to assign them to variables.

<--->

```csharp
record User(string UserID, string Email);

class Program
{
    public static void Main(string[] args)
    {
        var user = new User("scalalang", "scalalang2@gmail.com");
        var (userID, _) = user;

        // output:
        // userID: scalalang
        Console.WriteLine($"userID: {userID}");
    }
}

```

{{< /columns >}}