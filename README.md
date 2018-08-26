# TicTacToe
Just following the code in "Learning ASP.NET Core 2"

1. Download visual studio code (not using visual studio)
2. Install .NET Core 2.1 [https://www.microsoft.com/net/download/archives]
3. Make an empty repo and clone it
4. CD into repo
5. type `dotnet new web`
6. type `code .`
7. open `Program.cs` (in code)
8. Choose to download prerquisits when the toast notification appears
9. Hit `F5` to run, see the webpage with "Hello, World!"
10. Change code to look like this (so we don't get IIS, we only listen for localhost and we remember how to do the CaptureStartupErrors thing)
```c#
    public static IWebHostBuilder CreateWebHostBuilder(string[] args) => 
            new WebHostBuilder()
            .UseKestrel()
            .UseContentRoot(Directory.GetCurrentDirectory())
            .UseStartup<Startup>()
            //.CaptureStartupErrors(true)
            .UseUrls("http://localhost:5000");
```
11. You probably want to add `WebHost.CaptureStartupErrors(true)` at some point (`WebHost` is what you get from the `Build` method od `IWebHostBuilder`)
12. Follow the Tut for a while.
13. When it tells you to use Visual Studio to add a layout file, you are stuck. If you create a new project with .NET like this `dotnet new mvc --name AspNetMvc` the result will have a _Layout.cshtml file that you can use.
14. Also get the Home/Index.cshtml
15. Just skip the bower stuff and use the CDN in development and production
