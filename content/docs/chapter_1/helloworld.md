---
weight: 1
bookToc: false
---

## Hello World

This is an entrypoint for your jouney to C#.

```csharp
string world = "World";

Console.WriteLine("Hello World");
Console.WriteLine("Hello " + world);
Console.WriteLine($"Hello {world}");
```

## .NET
Just like in Java, where you can compile code written with the `javac` compiler and run it with the `java` command, you can also compile C# code with the `csc` compiler.

However, you are reading this article and trying to learn C#, you will probably learn [.NET](https://dotnet.microsoft.com/en-us/learn/dotnet/hello-world-tutorial/create) So, I'll introduce how to compile and run with the `dotnet` command.

## .NET Installation
Follow the guide on [this link](https://dotnet.microsoft.com/en-us/learn/dotnet/hello-world-tutorial/install) to install **dotnet** command

## Project Setup

```bash
$ dotnet new console -o HelloWorld
$ cd HelloWorld
```

This command creates a template of a console application named `HelloWorld`.

```bash
.
├── HelloWorld.csproj
├── Program.cs
└── obj
```

- `HelloWorld.csproj` : project configuration file
- `Program.cs` : entrypoint of the program

When you write and run a "Hello, World!" program in Program.cs using the dotnet run command, you will see the following output:

```bash
$ dotnet run
Hello, World!
```