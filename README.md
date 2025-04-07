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

##Tutorial: Create a minimal API with ASP.NET Core
##Tutorial: Create a controller-based web API with ASP.NET Core

