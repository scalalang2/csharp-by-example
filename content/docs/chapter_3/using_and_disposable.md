---
weight: 4
---

## Using and IDisposable Interface

{{< hint info >}}
**Idea**

If you know about `defer` in golang or `with` statement in python, then you'll probably understand what `Disposable` is.
{{< /hint >}}

Classes that inherits IDisposable interface must override the `Dispose` method which is called automatically at the end of scope in which the object is declared.

The primary goal of `IDisposable` interface is to release unmanaged interface. such as open files, stream, or window handles.

{{< columns >}}

<br />

This program prints out following messages.

```
Entering Work
Do Something Here
Leaving Work
```

As shown in the example, the `Dispose` method of Logger class is called automatically.

If the using keyword is removed, the Dispose method will not be called automatically, and the unmanaged resources will not be released until the garbage collector collects the Logger object.

<--->

```cs
using System.Runtime.CompilerServices;

public class Program
{
    class Logger : IDisposable
    {
        private string _method;
        public Logger([CallerMemberName] string method = "")
        {
            _method = method;
            Console.WriteLine($"Entering {_method}");
        }
        
        public void Dispose()
        {
            Console.WriteLine($"Leaving {_method}");   
        }
    }
    
    public static void Main(string[] args)
    {
        Work();
    }

    public static void Work()
    {
        using var logger = new Logger();
        Console.WriteLine("Do Something Here");
    }
}
```

{{< /columns >}}