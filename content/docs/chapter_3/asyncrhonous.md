---
weight: 2
---

## Asynchronous
`Async` and `await` made easy to write asynchronous code. It can run without blocking the main thread of execution. It's useful for I/O bound task, and task that require waiting for another task to complete.

- if method is marked with async keyword, It runs asynchronously and returns a Task object.
- await statements suspend execution until the a task is completed.

```cs
class Program {
    public async static Task DoStuff() {
        var rnd = new Random();
        for (int i = 0; i <= 50; i++)
        {
            await Task.Delay(rnd.Next(10, 300));
            Console.WriteLine($"Do Stuff, num: {i}");
        }
    }
    
    public async static Task<bool> DownloadFileAsync(string url)
    {
        // WebClient client = new WebClient();
        // await client.DownloadFileTaskAsync(url, "file.txt");
        await Task.Delay(2000);
        return true;
    }    
    
    public async static Task Main(string[] args)
    {
        DoStuff();
        bool result = await DownloadFileAsync("https://google.come/");
        if (result) {
            Console.WriteLine("successfully downloaded");
        } else {
            Console.WriteLine("failed to download");
        }
    }
}
```
```
Do Stuff, num: 0
Do Stuff, num: 1
Do Stuff, num: 2
Do Stuff, num: 3
Do Stuff, num: 4
Do Stuff, num: 5
Do Stuff, num: 6
Do Stuff, num: 7
Do Stuff, num: 8
Do Stuff, num: 9
Do Stuff, num: 10
Do Stuff, num: 11
successfully downloaded
```