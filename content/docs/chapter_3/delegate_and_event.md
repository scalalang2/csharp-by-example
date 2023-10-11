---
weight: 3
---

## Delegate and Event
**A delegate is a variable that holds methods(functions)**.

{{< columns >}}

<br />

Just like defining a class, you can define a method signature with a `delegate`

Instantiating a delegate is similar to definition of variables, you need to specify the type and assign a method to it.

<--->

```cs
public delegate void Handler(string message);

public void ExampleHandler(string messagE) {
    Console.WriteLine(message);
}

...

Handler handler = ExampleHandler;
handler("Hello, World!");
```

{{< /columns >}}

{{< columns >}}

<br />

Interestingly, you can assign multiple methods to it and once we invoke the delegate, all the methods will be called.

<--->

```cs
class Pogram
{
    public delegate void Handler(string message);

    public static void ExampleHandler(string message){
        Console.WriteLine(message);
    }
    
    public static void Main(){
        Handler callback = ExampleHandler;
        callback += (string x) => {
            Console.WriteLine($"anonymous: {x}");
        };
        callback("Hello World");

        // output:
        // example: Hello World
        // anonymous: Hello World
    }
}
```

{{< /columns >}}

{{< columns >}}

<br />

You can use **Action<T>** instead of a delegate, it looks more simple.

<--->

```cs
class Pogram {
    public static void ExampleHandler(string message) {
        Console.WriteLine($"example: {message}");
    }
    
    public static void Main(){
        Action<string> callback = ExampleHandler;
        callback += (string x) => {
            Console.WriteLine($"anonymous: {x}");
        };
        callback("Hello World");
    }
}
```

{{< /columns >}}

{{< columns >}}

<br />

Action is also a delegate type as you can see it from the definition.

<--->

```cs
#nullable enable
namespace System {
  /// <summary>Encapsulates a method that has a single parameter and does not return a value.</summary>
  /// <param name="obj">The parameter of the method that this delegate encapsulates.</param>
  /// <typeparam name="T">The type of the parameter of the method that this delegate encapsulates.</typeparam>
  public delegate void Action<in T>(T obj);
}
```

{{< /columns >}}

## Publish and Subscribe

Publisher and Subscriber model is a common example of using delegate and event.

{{< columns >}}

<br />

When new member is joined to a chat room, it notifies all room members that a new member is joined.

<--->

```cs
class ChatRoom
{
    private List<Member> _members = new List<Member>();
    public event Action<string> Handler;
    
    public void Join(Member member) {
        _members.Add(member);
        Handler += member.MemberJoined;
        Handler.Invoke(member.Name);
    }
}

class Member
{
    private string _name;

    public string Name
    {
        get { return _name; }
        set { _name = value; }
    }

    public Member(string name) {
        _name = name;
    }

    public void MemberJoined(string name) {
        Console.WriteLine($"{_name}: new member '{name}' joined a chat room");
    }
}

class Pogram{
    public static void Main(){
        var alice = new Member("Alice");
        var bob = new Member("Bob");
        var room = new ChatRoom();
        room.Join(alice);
        room.Join(bob);
    }
}
```
```shell
$ dotnet run
Alice: new member 'Alice' joined a chat room
Alice: new member 'Bob' joined a chat room
Bob: new member 'Bob' joined a chat room 
```

{{< /columns >}}