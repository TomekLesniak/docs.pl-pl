---
title: Tworzenie aplikacji platformy .NET Core za pomocą wtyczek
description: Dowiedz się, jak utworzyć aplikację platformy .NET Core, która obsługuje wtyczki.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 10/16/2019
ms.openlocfilehash: ce7ac826feaf4542307abefde6d40a319d78e423
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247595"
---
# <a name="create-a-net-core-application-with-plugins"></a>Tworzenie aplikacji platformy .NET Core za pomocą wtyczek

W tym samouczku pokazano, jak utworzyć niestandardowe, <xref:System.Runtime.Loader.AssemblyLoadContext> Aby załadować wtyczki. <xref:System.Runtime.Loader.AssemblyDependencyResolver>Służy do rozpoznawania zależności wtyczki. Samouczek prawidłowo izoluje zależności wtyczki od aplikacji hostingowej. Omawiane tematy:

- Tworzenie struktury projektu do obsługi wtyczek.
- Utwórz niestandardową, <xref:System.Runtime.Loader.AssemblyLoadContext> Aby załadować każdą wtyczkę.
- Użyj <xref:System.Runtime.Loader.AssemblyDependencyResolver?displayProperty=fullName> typu, aby zezwolić na wtyczki.
- Tworzenie wtyczek, które można łatwo wdrożyć przez Kopiowanie artefaktów kompilacji.

## <a name="prerequisites"></a>Wymagania wstępne

- Zainstaluj [zestaw SDK platformy .NET Core 3,0](https://dotnet.microsoft.com/download) lub nowszą wersję.

## <a name="create-the-application"></a>Tworzenie aplikacji

Pierwszym krokiem jest utworzenie aplikacji:

1. Utwórz nowy folder, a w tym folderze Uruchom następujące polecenie:

    ```dotnetcli
    dotnet new console -o AppWithPlugin
    ```

2. Aby ułatwić Kompilowanie projektu, Utwórz plik rozwiązania programu Visual Studio w tym samym folderze. Uruchom następujące polecenie:

    ```dotnetcli
    dotnet new sln
    ```

3. Uruchom następujące polecenie, aby dodać projekt aplikacji do rozwiązania:

    ```dotnetcli
    dotnet sln add AppWithPlugin/AppWithPlugin.csproj
    ```

Teraz możemy wypełnić szkielet naszej aplikacji. Zastąp kod w pliku *AppWithPlugin/program. cs* następującym kodem:

```csharp
using PluginBase;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Reflection;

namespace AppWithPlugin
{
    class Program
    {
        static void Main(string[] args)
        {
            try
            {
                if (args.Length == 1 && args[0] == "/d")
                {
                    Console.WriteLine("Waiting for any key...");
                    Console.ReadLine();
                }

                // Load commands from plugins.

                if (args.Length == 0)
                {
                    Console.WriteLine("Commands: ");
                    // Output the loaded commands.
                }
                else
                {
                    foreach (string commandName in args)
                    {
                        Console.WriteLine($"-- {commandName} --");

                        // Execute the command with the name passed as an argument.

                        Console.WriteLine();
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex);
            }
        }
    }
}

```

## <a name="create-the-plugin-interfaces"></a>Tworzenie interfejsów wtyczek

Następnym krokiem tworzenia aplikacji z wtyczkami jest zdefiniowanie interfejsu, do którego wtyczki wymagają wdrożenia. Sugerujemy, aby utworzyć bibliotekę klas, która zawiera wszystkie typy, które mają być używane do komunikacji między aplikacją i wtyczkami. Ten oddział umożliwia opublikowanie interfejsu wtyczki jako pakietu bez konieczności dostarczania kompletnej aplikacji.

W folderze głównym projektu uruchom polecenie `dotnet new classlib -o PluginBase` . Ponadto Uruchom polecenie, `dotnet sln add PluginBase/PluginBase.csproj` Aby dodać projekt do pliku rozwiązania. Usuń `PluginBase/Class1.cs` plik i Utwórz nowy plik w `PluginBase` folderze o nazwie `ICommand.cs` przy użyciu następującej definicji interfejsu:

[!code-csharp[the-plugin-interface](~/samples/snippets/core/tutorials/creating-app-with-plugin-support/csharp/PluginBase/ICommand.cs)]

Ten `ICommand` interfejs jest interfejsem, który implementuje wszystkie wtyczki.

Teraz, gdy `ICommand` interfejs jest zdefiniowany, projekt aplikacji może być wypełniony nieco więcej. Dodaj odwołanie z `AppWithPlugin` projektu do `PluginBase` projektu za pomocą `dotnet add AppWithPlugin/AppWithPlugin.csproj reference PluginBase/PluginBase.csproj`  polecenia z folderu głównego.

Zastąp `// Load commands from plugins` komentarz następującym fragmentem kodu, aby umożliwić mu ładowanie wtyczek z danych ścieżek plików:

```csharp
string[] pluginPaths = new string[]
{
    // Paths to plugins to load.
};

IEnumerable<ICommand> commands = pluginPaths.SelectMany(pluginPath =>
{
    Assembly pluginAssembly = LoadPlugin(pluginPath);
    return CreateCommands(pluginAssembly);
}).ToList();
```

Następnie zastąp `// Output the loaded commands` komentarz następującym fragmentem kodu:

```csharp
foreach (ICommand command in commands)
{
    Console.WriteLine($"{command.Name}\t - {command.Description}");
}
```

Zastąp `// Execute the command with the name passed as an argument` komentarz następującym fragmentem kodu:

```csharp
ICommand command = commands.FirstOrDefault(c => c.Name == commandName);
if (command == null)
{
    Console.WriteLine("No such command is known.");
    return;
}

command.Execute();
```

A wreszcie Dodaj metody statyczne do `Program` klasy o nazwie `LoadPlugin` i `CreateCommands` , jak pokazano poniżej:

```csharp
static Assembly LoadPlugin(string relativePath)
{
    throw new NotImplementedException();
}

static IEnumerable<ICommand> CreateCommands(Assembly assembly)
{
    int count = 0;

    foreach (Type type in assembly.GetTypes())
    {
        if (typeof(ICommand).IsAssignableFrom(type))
        {
            ICommand result = Activator.CreateInstance(type) as ICommand;
            if (result != null)
            {
                count++;
                yield return result;
            }
        }
    }

    if (count == 0)
    {
        string availableTypes = string.Join(",", assembly.GetTypes().Select(t => t.FullName));
        throw new ApplicationException(
            $"Can't find any type which implements ICommand in {assembly} from {assembly.Location}.\n" +
            $"Available types: {availableTypes}");
    }
}
```

## <a name="load-plugins"></a>Załaduj wtyczki

Teraz aplikacja może prawidłowo załadować i utworzyć wystąpienia poleceń z załadowanych zestawów wtyczek, ale nadal nie można załadować zestawów wtyczek. Utwórz plik o nazwie *PluginLoadContext.cs* w folderze *AppWithPlugin* o następującej zawartości:

[!code-csharp[loading-plugins](~/samples/snippets/core/tutorials/creating-app-with-plugin-support/csharp/AppWithPlugin/PluginLoadContext.cs)]

`PluginLoadContext`Typ pochodzi od <xref:System.Runtime.Loader.AssemblyLoadContext> . `AssemblyLoadContext`Typ jest specjalnym typem w środowisku uruchomieniowym, który umożliwia deweloperom izolowanie załadowanych zestawów do różnych grup, aby upewnić się, że wersje zestawu nie powodują konfliktu. Ponadto niestandardowe `AssemblyLoadContext` może wybrać różne ścieżki, z których mają zostać załadowane zestawy, i zastąpić zachowanie domyślne. `PluginLoadContext`Używa wystąpienia `AssemblyDependencyResolver` typu wprowadzonego w środowisku .net Core 3,0 w celu rozpoznania nazw zestawów w ścieżkach. `AssemblyDependencyResolver`Obiekt jest skonstruowany ze ścieżką do biblioteki klas .NET. Rozpoznaje zestawy i biblioteki natywne do ich ścieżek względnych na podstawie *.deps.jsw* pliku dla biblioteki klas, której ścieżka została przeniesiona do `AssemblyDependencyResolver` konstruktora. Niestandardowe `AssemblyLoadContext` umożliwiają wtyczki mają własne zależności i `AssemblyDependencyResolver` ułatwiają prawidłowe ładowanie zależności.

Teraz, gdy `AppWithPlugin` projekt ma `PluginLoadContext` Typ, zaktualizuj `Program.LoadPlugin` metodę za pomocą następującej treści:

```csharp
static Assembly LoadPlugin(string relativePath)
{
    // Navigate up to the solution root
    string root = Path.GetFullPath(Path.Combine(
        Path.GetDirectoryName(
            Path.GetDirectoryName(
                Path.GetDirectoryName(
                    Path.GetDirectoryName(
                        Path.GetDirectoryName(typeof(Program).Assembly.Location)))))));

    string pluginLocation = Path.GetFullPath(Path.Combine(root, relativePath.Replace('\\', Path.DirectorySeparatorChar)));
    Console.WriteLine($"Loading commands from: {pluginLocation}");
    PluginLoadContext loadContext = new PluginLoadContext(pluginLocation);
    return loadContext.LoadFromAssemblyName(new AssemblyName(Path.GetFileNameWithoutExtension(pluginLocation)));
}
```

Przy użyciu innego `PluginLoadContext` wystąpienia dla każdej wtyczki wtyczki mogą mieć różne lub nawet zależności powodujące konflikty bez problemu.

## <a name="simple-plugin-with-no-dependencies"></a>Prosta wtyczka bez zależności

W folderze głównym wykonaj następujące czynności:

1. Uruchom następujące polecenie, aby utworzyć nowy projekt biblioteki klas o nazwie `HelloPlugin` :

    ```dotnetcli
    dotnet new classlib -o HelloPlugin
    ```

2. Uruchom następujące polecenie, aby dodać projekt do `AppWithPlugin` rozwiązania:

    ```dotnetcli
    dotnet sln add HelloPlugin/HelloPlugin.csproj
    ```

3. Zastąp plik *HelloPlugin/Class1. cs* plikiem o nazwie *HelloCommand.cs* następującym zawartością:

[!code-csharp[the-hello-plugin](~/samples/snippets/core/tutorials/creating-app-with-plugin-support/csharp/HelloPlugin/HelloCommand.cs)]

Teraz otwórz plik *HelloPlugin. csproj* . Zawartość okna powinna wyglądać mniej więcej tak:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>

```

W obu `<Project>` tagach Dodaj następujące elementy:

```xml
<ItemGroup>
    <ProjectReference Include="..\PluginBase\PluginBase.csproj">
        <Private>false</Private>
        <ExcludeAssets>runtime</ExcludeAssets>
    </ProjectReference>
</ItemGroup>
```

`<Private>false</Private>`Element jest istotny. Spowoduje to, że program MSBuild nie skopiuje *PluginBase.dll* do katalogu wyjściowego dla HelloPlugin. Jeśli zestaw *PluginBase.dll* jest obecny w katalogu danych wyjściowych, `PluginLoadContext` program znajdzie zestaw i załaduje go podczas ładowania zestawu *HelloPlugin.dll* . W tym momencie `HelloPlugin.HelloCommand` Typ spowoduje zaimplementowanie `ICommand` interfejsu z *PluginBase.dll* w katalogu wyjściowym `HelloPlugin` projektu, a nie `ICommand` interfejsu, który jest ładowany do domyślnego kontekstu ładowania. Ponieważ środowisko uruchomieniowe widzi te dwa typy jako różne typy z różnych zestawów, `AppWithPlugin.Program.CreateCommands` Metoda nie znajdzie poleceń. W związku z tym `<Private>false</Private>` metadane są wymagane dla odwołania do zestawu zawierającego interfejsy wtyczki.

Podobnie `<ExcludeAssets>runtime</ExcludeAssets>` element jest również ważny, jeśli `PluginBase` odwołuje się do innych pakietów. To ustawienie ma ten sam efekt, co, `<Private>false</Private>` ale działa w odniesieniu do pakietu, który `PluginBase` może zawierać projekt lub jeden z jego zależności.

Po `HelloPlugin` zakończeniu projektu należy zaktualizować `AppWithPlugin` projekt, aby dowiedzieć się, gdzie `HelloPlugin` można znaleźć wtyczkę. Po `// Paths to plugins to load` komentarzu Dodaj `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` (Ta ścieżka może różnić się w zależności od używanej wersji platformy .NET Core) jako element `pluginPaths` tablicy.

## <a name="plugin-with-library-dependencies"></a>Wtyczka z zależnościami biblioteki

Prawie wszystkie wtyczki są bardziej skomplikowane niż proste "Hello world", a wiele wtyczek ma zależności od innych bibliotek. `JsonPlugin` `OldJson` Projekty wtyczki i w przykładzie pokazują dwa przykłady wtyczek z zależnościami pakietów NuGet `Newtonsoft.Json` . Pliki projektu nie zawierają żadnych specjalnych informacji o odwołaniach do projektu i (po dodaniu ścieżek wtyczki do `pluginPaths` tablicy) wtyczki są wykonywane doskonale, nawet jeśli są uruchamiane w ramach tego samego uruchomienia aplikacji AppWithPlugin. Jednak te projekty nie kopiują przywoływanych zestawów do ich katalogu wyjściowego, więc zestawy muszą być obecne na komputerze użytkownika, aby wtyczki działały. Istnieją dwa sposoby obejścia tego problemu. Pierwszą opcją jest użycie `dotnet publish` polecenia do opublikowania biblioteki klas. Alternatywnie, jeśli chcesz mieć możliwość użycia danych wyjściowych `dotnet build` dla wtyczki, możesz dodać `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` Właściwość między `<PropertyGroup>` tagami w pliku projektu wtyczki. Przykład można znaleźć w `XcopyablePlugin` projekcie wtyczki.

## <a name="other-examples-in-the-sample"></a>Inne przykłady w przykładzie

Pełny kod źródłowy dla tego samouczka można znaleźć w [repozytorium dotnet/Samples](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin). Ukończony przykład zawiera kilka innych przykładowych `AssemblyDependencyResolver` zachowań. Na przykład `AssemblyDependencyResolver` obiekt może również rozpoznać biblioteki natywne oraz zlokalizowane zestawy satelickie zawarte w pakietach NuGet. `UVPlugin` `FrenchPlugin` W repozytorium przykładów przedstawiono te scenariusze.

## <a name="reference-a-plugin-interface-from-a-nuget-package"></a>Odwoływanie się do interfejsu wtyczki z pakietu NuGet

Załóżmy, że istnieje aplikacja A, która ma interfejs wtyczki zdefiniowany w pakiecie NuGet o nazwie `A.PluginBase` . Jak prawidłowo odwołać pakiet w projekcie wtyczki? W przypadku odwołań do projektu użycie `<Private>false</Private>` metadanych w `ProjectReference` elemencie w pliku projektu uniemożliwiło skopiowanie biblioteki DLL do danych wyjściowych.

Aby prawidłowo utworzyć odwołanie do `A.PluginBase` pakietu, należy zmienić `<PackageReference>` element w pliku projektu na następujący:

```xml
<PackageReference Include="A.PluginBase" Version="1.0.0">
    <ExcludeAssets>runtime</ExcludeAssets>
</PackageReference>
```

Zapobiega to `A.PluginBase` kopiowaniu zestawów do katalogu wyjściowego wtyczki i gwarantuje, że wtyczka będzie używać wersji programu `A.PluginBase` .

## <a name="plugin-target-framework-recommendations"></a>Zalecenia dotyczące platformy docelowej wtyczki

Ponieważ ładowanie zależności wtyczki używa *.deps.jsw* pliku, istnieje Gotcha powiązany z platformą docelową wtyczki. W związku z tym wtyczki powinny kierować do środowiska uruchomieniowego, takiego jak .NET Core 3,0, zamiast wersji .NET Standard. *.deps.jsna* pliku jest generowany na podstawie struktury projektu, a ponieważ wiele pakietów zgodnych ze .NET standardem dostarcza zestawy referencyjne do kompilowania względem zestawów .NET Standard i implementacji dla określonych środowisk uruchomieniowych, *.deps.json* może nieprawidłowo zobaczyć zestawy implementacji lub można pobrać .NET Standard wersję zestawu zamiast oczekiwanej wersji programu .NET Core.

## <a name="plugin-framework-references"></a>Odwołania do struktury wtyczki

Obecnie wtyczki nie mogą wprowadzać nowych struktur do procesu. Nie można na przykład załadować wtyczki korzystającej z `Microsoft.AspNetCore.App` struktury do aplikacji, która używa tylko `Microsoft.NETCore.App` platformy głównej. Aplikacja hosta musi deklarować odwołania do wszystkich struktur wymaganych przez wtyczki.
