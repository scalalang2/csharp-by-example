---
weight: 8
---

## Initializer
{{< columns >}}

<br/>

Read-only fields can only be initialized in the constructor or init-only setter.

<--->

```csharp
public class User
{
    public readonly int ID = 1; // init-only setter
    public readonly DateTime CreatedAt;

    public User() {
        // initialized in the constructor
        CreatedAt = DateTime.Now;
    }

    public void ChangeDate(DateTime date)
    {
        // ERROR! 'CreatedAt' is read-only
        CreatedAt = date;
    }
}
```

{{< /columns >}}