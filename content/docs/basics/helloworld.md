---
weight: 1
bookToc: false
---

## Hello World

먼저, Hello World를 출력하는 간단한 프로그램을 작성해봅시다.

```csharp
string world = "World";

Console.WriteLine("Hello World");
Console.WriteLine("Hello " + world);
Console.WriteLine($"Hello {world}");
```

## .NET
Java에서 `javac` 컴파일러로 작성한 코드를 컴파일 하고 `java` 명령어로 실행했던 것과 마찬가지로 C#에서는 `csc` 라는 컴파일러를 이용해서 컴파일 할 수 있긴 합니다.

하지만 지금 이 글을 보며 C#을 배우려고 하는 여러분은 아마 [.NET](https://dotnet.microsoft.com/en-us/learn/dotnet/hello-world-tutorial/create)를 배우시게 될 것입니다. 그래서 여기서는 `dotnet` 명령어로 컴파일 및 실행하는 방법을 소개하겠습니다.

## .NET 설치
[이 링크](https://dotnet.microsoft.com/en-us/learn/dotnet/hello-world-tutorial/install)의 가이드를 따라 dotnet을 설치해줍니다.

## 프로젝트 생성, 컴파일, 실행

```bash
$ dotnet new console -o HelloWorld
$ cd HelloWorld
```

위 명령어는 콘솔 명령어를 만들 수 있는 `HelloWorld` 라는 이름의 프로젝트를 생성합니다.

```bash
.
├── HelloWorld.csproj
├── Program.cs
└── obj
```

만들어진 프로젝트 폴더에는 `HelloWorld.csproj`와 `Program.cs` 파일이 있습니다. 

- `HelloWorld.csproj` : 프로젝트의 설정 파일 
- `Program.cs` : 프로그램의 진입점

Program.cs 파일을 수정하여 위으 코드를 작성한 다음, 아래 명령어로 실행시킵니다.

```bash
$ dotnet run
Hello, World!
```

🌎 🎉 새로운 세계에 오신 것을 환영합니다 