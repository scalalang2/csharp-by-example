---
weight: 5
---

## Using Locks
Lock is a way to set critical section in a multithreaded environment. It is used to prevent multiple threads from accessing the same code block at the same time. It is used to prevent data corruption.

Usually, when you want to use a lock, you need to create a new object and use it as a lock. 

{{< columns >}}

This example show that the `balance` field is protected from being accessed by multiple threads at the same time.

<--->

```cs
public class Account
{
    private readonly object balanceLock = new object();
    private decimal balance;

    public Account(decimal initialBalance) => balance = initialBalance;

    public decimal Debit(decimal amount)
    {
        if (amount < 0)
        {
            throw new ArgumentOutOfRangeException(nameof(amount), "The debit amount cannot be negative.");
        }

        decimal appliedAmount = 0;
        lock (balanceLock)
        {
            if (balance >= amount)
            {
                balance -= amount;
                appliedAmount = amount;
            }
        }
        return appliedAmount;
    }

    public void Credit(decimal amount)
    {
        if (amount < 0)
        {
            throw new ArgumentOutOfRangeException(nameof(amount), "The credit amount cannot be negative.");
        }

        lock (balanceLock)
        {
            balance += amount;
        }
    }

    public decimal GetBalance()
    {
        lock (balanceLock)
        {
            return balance;
        }
    }
}

```

{{< /columns >}}
