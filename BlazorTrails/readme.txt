10:51 AM 26-Apr-25
Chris Sainty

md daz
cd daz
dotnet new sln

10:56 AM 26-Apr-25
md daz
cd daz
dotnet new sln

dotnet new list bl
These templates matched your input: 'bl'

Template Name                      Short Name    Language  Tags
---------------------------------  ------------  --------  --------------------------
Blazor Server App                  blazorserver  [C#]      Web/Blazor
Blazor Web App                     blazor        [C#]      Web/Blazor/WebAssembly
Blazor WebAssembly Standalone App  blazorwasm    [C#]      Web/Blazor/WebAssembly/PWA

dotnet new blazorwasm -h

Template options:
  -f, --framework <net8.0|netcoreapp3.1>   The target framework for the project.
                                           Type: choice
                                             net8.0         Target net8.0
                                             netcoreapp3.1  Target netcoreapp3.1
                                           Default: net8.0
- so there will be no warning (net 7)

  -e, --empty 
--no-https
--use-program-main
-ho, --hosted

dotnet new blazorwasm -o foo --use-program-main --no-https -ho
dotnet new blazorwasm -o foo --use-program-main --no-https -e

dotnet new blazorwasm [options] [template options]

        var builder = WebAssemblyHostBuilder.CreateDefault(args);

dotnet.wasm
blazor.webassembly.js
blazor.boot.js

11:24 AM 26-Apr-25
Chapter 2
more complex template - 2 modes
hosted vs standalone

    <!-- If you add any scoped CSS files, uncomment the following to load them
    <link href="foo.styles.css" rel="stylesheet" /> -->
    <link href="bar.styles.css" rel="stylesheet" />

Chapter 3.

life-cycle
OnParametersSet (+async) run every time the incoming parameters change
see ngOnChange angular

2:28 PM 29-Apr-25
dotnet new console -o foo --use-program-main
test reactive try implement
ideas:

Observable.Create static method
Observable.Create<T>(fn) <-- pass in a fn (action for now)
do I call action fn() inside create - No - I wait for subscribe()
so I store it

infinite sequences
listens for data inside create
warning - unreacheable code return Disposable.Empty (how to deal?)
Observable.Generate, not Create
inside:
OnNext()
OnNext()
...
OnNext()
OnCompleted();

merge 2 sync observables - executes in sync on one thread (my guess)


Results:
in another thread: [6]
OnNext: -1 [6]
OnNext: -2 [6]
OnNext: 1 [8]
OnNext: 2 [8]
OnNext: 5 [8]
OnCompleted: [8]

.ObserveOn(Scheduler.Default)

in another thread: [6]
OnNext: -1 [9]
OnNext: -2 [9]
OnNext: 1 [9]
OnNext: 2 [9]
OnNext: 5 [9]
OnCompleted: [9]
