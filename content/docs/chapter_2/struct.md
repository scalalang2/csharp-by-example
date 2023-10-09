---
weight: 1
---

## Struct

**Struct** is a way to group related data together, and It's a typed collection of fields.

{{< columns >}}

<br />

Let's see it declares **Program** class and **Main** method.

We haven't declared an entrypoint of class and a `Main` method in the previous examples, [because the compiler automatically generates those for us.](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/program-structure/top-level-statements)

In this example, we explicitly declare a `Program` class to define an `Employee` struct at the top-level of a file.

<--->

```csharp
public struct Employee {
    public string name;
    public int id;
    public int age;
};

class Program {
    public static void Main(string[] args) {
        var emp = new Employee();
        emp.name = "John";
        emp.id = 1;
        emp.age = 23;

        Console.WriteLine($"name: {emp.name}"); // name: John
        Console.WriteLine($"id: {emp.id}");     // id: 1
        Console.WriteLine($"age: {emp.age}");   // age: 23
    }
}
```

{{< /columns >}}

{{< columns >}}

<br />

`Employee` struct has three fields: `name`, `id`, and `age`. Each fields has a type, a name and an indicator of its accessibility.

<--->

```csharp
public struct Employee {
    public string name;
    public int id;
    public int age;
};
```

{{< /columns >}}

{{< columns >}}

<br />

We can define a **method** in structs.

<--->

```csharp
public struct Employee {
    public string name;
    public int id;
    public int age;

    public string toString() {
        return $"ID: {id}, name: {name}, age: {age}";
    }
};
```

{{< /columns >}}

{{< columns >}}

<br />

We can use the `new` operator to create an instance of a struct or declare a variable of the struct type. 

<--->

```csharp
// declare with new opperator
var emp1 = new Employee();

// declare a variable with struct type.
Employee emp2;

emp1.name = "John";
emp1.id = 1;
emp1.age = 23;

emp2.name = "Mark";
emp2.id = 2;
emp2.age = 25;

Console.WriteLine(emp1.toString());
Console.WriteLine(emp2.toString());
```

{{< /columns >}}

{{< columns >}}

<br/>

The all fields of created instance with **new** operator is initialized with default values. 

On the other hand, the variable with type doesn't initialize their fields. Therefore, we need to manually put values to each fields.

This example shows that It's not allowed to use a variable without initialization.

<--->

```csharp
public struct Employee {
    public string name;
    public int id;
    public int age;

    public string toString() {
        return $"ID: {id}, name: {name}, age: {age}";
    }
};

Employee emp;

// Local variable 'emp' might not be initialized before accessing
Console.WriteLine(emp.toString());
```

{{< /columns >}}

{{< columns >}}

<br />

You can't access a field of a struct if it has **private** access modifier.

<--->

```csharp
struct Employee {
    public string name;
    public int id;
    private int age;
};

var emp = new Employee();
emp.name = "John";
emp.id = 1;
emp.age = 23; // error: 'Employee.age' is inaccessible due to its protection level
```

{{< /columns >}}

{{< columns >}}

<br />

The private fields are accessible only within the body of the struct in which they  are declared.

<--->

```csharp
struct Employee {
    public string name;
    public int id;
    private int age;

    public void setAge(int age) {
        this.age = age;
    }
};

var emp = new Employee();
emp.name = "John";
emp.id = 1;
emp.setAge(23);
```

{{< /columns >}}

{{< columns >}}

<br />

Let's define a paramiterized **constructor** inside a User struct.

<--->

```csharp
public struct User {
    public string Id;
    public string Name;
    
    public User(string id, string name) {
        this.Id = id;
        this.Name = name;
    }
}

class Program {
    public static void Main(string[] args) {
        var user = new User("scalalang", "David");
        Console.WriteLine(user.Id);
        Console.WriteLine(user.Name);
    }
}
```

{{< /columns >}}

{{< columns >}}
### Struct is a value type.

Structs are a value type, It means that **all values of fields are copied** when the struct is assigned to a new variable or passed as a parameter.

<--->

```csharp
public struct User {...}

var user = new User("scalalang", "David");
var user2 = user;
user.Id = "I-love-csharp";
Console.WriteLine(user.Id);  // I-love-csharp
Console.WriteLine(user2.Id); // scalalang
```

{{< /columns >}}