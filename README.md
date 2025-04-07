# blog
1:06 PM 30-Mar-25
blazor train

md cca
cd cca
dotnet new sln
 The template "Solution File" was created successfully.
md foo
cd foo
dotnet new blazorserver
 The template "Console App" was created successfully.
cd ..
dotnet sln add foo
 Project `foo\foo.csproj` added to the solution.

dotnet new blazor -o bar
dotnet sln add bar
dotnet sln remove bar

dotnet new blazor -o bar --use-program-main

dotnet new blazorwasm -o baz --use-program-main

\cca\foo\Pages\_Host.cshtml
turn off prerendering
render-mode="Server"

server side
8:36 AM 31-Mar-25 ep 6
services.AddServerSideBlazor();

Tip getbootstrap click customize, deselect options

>dotnet new classlib -o gaz
The template "Class Library" was created successfully.
>dotnet sln add gaz

web asm -> scoped = singleton
only scoped and transient exist

remove telemetry
DOTNET_CLI_TELEMETRY_OPTOUT=1
wss failed
      "hotReloadEnabled": false,

10:59 AM 07-Apr-25

## Tutorial: Create a minimal API with ASP.NET Core
## Tutorial: Create a controller-based web API with ASP.NET Core
links
[https://learn.microsoft.com/en-us/aspnet/core/tutorials/min-web-api?view=aspnetcore-9.0&tabs=visual-studio]
[https://learn.microsoft.com/en-us/aspnet/core/tutorials/first-web-api?view=aspnetcore-9.0&tabs=visual-studio]
[https://learn.microsoft.com/en-us/aspnet/core/fundamentals/apis?view=aspnetcore-9.0]

two approaches to creating APIs:
a controller-based approach
minimal APIs

WebApplication and WebApplication builder (introduced in .NET 6)
[chapter Andrew Lock]
### Listing 3.1 Creating a new minimal API application
dotnet new sln -n abc
dotnet new web -o baz --use-program-main --no test
dotnet sln add baz

A controller based
dotnet new webapi --use-controllers -o TodoApi

namespace APIWithControllers;

public class Program
{
    public static void Main(string[] args)
    {
        var builder = WebApplication.CreateBuilder(args);

        builder.Services.AddControllers();
        var app = builder.Build();

        app.UseHttpsRedirection();

        app.MapControllers();

        app.Run();
    }
}

1. Create a WebApplicationBuilder instance
2. Register the required services
3. Call Build() to create a WebApplication instance
4. Add middleware (to the instance)
5. Map the endpoints
6. Call Run()

