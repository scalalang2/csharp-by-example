---
weight: 10
---

## Sealed class

{{< columns >}}

<br/>

Sealed classes prevent other classes from inheriting from them.

<--->

```cs
sealed class A {
    public void Foo() { }
}

// ERROR! Cannot derived from sealed class
public class B : A{}
```

{{< /columns >}}