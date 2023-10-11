---
weight: 1
---

## Task
The Task is a high-level abstraction of a Thread, it is a unit of work that executes asynchronously.

It's first introduced in the .NET framework 4.

You will be familar If you've experienced the Promise pattern in Javascript.

{{< columns >}}

<br/>

This example create tasks that print out a number and the current thread ID.

Action encapsulates a method that has a single parameter and does not return a value.

When `Task.Start()` method is called, the task is queued for execution by the thread pool.

As you can see at the output, the tasks are executed in another thread rather than the main thread.

<--->

```cs
var rnd = new Random();
for (int i = 1; i <= 10; i++) {
    Action<object> action = (object obj) =>
    {
        Thread.Sleep(rnd.Next(500, 1000));
        Console.WriteLine("obj={1}, ThreadID={2}",
            i, obj, Thread.CurrentThread.ManagedThreadId);
    };

    Task t = new Task(action, $"num={i}");
    t.Start();
}

Console.Read();
// obj=num=9, ThreadID=14
// obj=num=7, ThreadID=12
// obj=num=3, ThreadID=8
// obj=num=4, ThreadID=9
// obj=num=6, ThreadID=11
// obj=num=8, ThreadID=13
// obj=num=10, ThreadID=15
// obj=num=2, ThreadID=7
// obj=num=5, ThreadID=10
// obj=num=1, ThreadID=6
```

{{< /columns >}}

{{< columns >}}

<br/>

`Task.WaitAny` method wait for any of the tasks to complete.

We can track the staus of the task.

<--->

```cs
var tasks = new Task[3];
var rnd = new Random();
for (int i = 0; i <= 2; i++)
    tasks[i] = new Task(() => Thread.Sleep(rnd.Next(500, 3000)));

for(int i = 0; i <= 2; i++)
    tasks[i].Start();

Task.WaitAll(tasks);
foreach(var t in tasks)
    Console.WriteLine("Task #{0}: {1}", t.Id, t.Status);

// Task #1: Running
// Task #2: Running        
// Task #3: RanToCompletion
```

{{< /columns >}}