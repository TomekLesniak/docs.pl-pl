---
title: polecenie dotnet Run
description: Polecenie dotnet Run udostępnia wygodną opcję uruchamiania aplikacji z kodu źródłowego.
ms.date: 02/19/2020
ms.openlocfilehash: c80f290c75e3bac65ae73fe8edada53db4ce86f8
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634419"
---
# <a name="dotnet-run"></a><span data-ttu-id="bb093-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="bb093-103">dotnet run</span></span>

<span data-ttu-id="bb093-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 2. x SDK i nowszych wersji</span><span class="sxs-lookup"><span data-stu-id="bb093-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="bb093-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="bb093-105">Name</span></span>

<span data-ttu-id="bb093-106">`dotnet run` -Uruchamia kod źródłowy bez żadnych jawnych poleceń kompilacji lub uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="bb093-106">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bb093-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="bb093-107">Synopsis</span></span>

```dotnetcli
dotnet run [-c|--configuration <CONFIGURATION>] [-f|--framework <FRAMEWORK>]
    [--force] [--interactive] [--launch-profile <NAME>] [--no-build]
    [--no-dependencies] [--no-launch-profile] [--no-restore]
    [-p|--project <PATH>] [-r|--runtime <RUNTIME_IDENTIFIER>]
    [-v|--verbosity <LEVEL>] [[--] [application arguments]]

dotnet run -h|--help
```

## <a name="description"></a><span data-ttu-id="bb093-108">Opis</span><span class="sxs-lookup"><span data-stu-id="bb093-108">Description</span></span>

<span data-ttu-id="bb093-109">`dotnet run`Polecenie udostępnia wygodną opcję uruchamiania aplikacji z kodu źródłowego za pomocą jednego polecenia.</span><span class="sxs-lookup"><span data-stu-id="bb093-109">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="bb093-110">Jest to przydatne w przypadku szybkiego iteracyjnego programowania z poziomu wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="bb093-110">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="bb093-111">Polecenie jest zależne od [`dotnet build`](dotnet-build.md) polecenia do kompilowania kodu.</span><span class="sxs-lookup"><span data-stu-id="bb093-111">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="bb093-112">Wszelkie wymagania dotyczące kompilacji, takie jak najpierw należy przywrócić projekt, również zastosować do `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="bb093-112">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="bb093-113">Pliki wyjściowe są zapisywane w lokalizacji domyślnej, czyli `bin/<configuration>/<target>` .</span><span class="sxs-lookup"><span data-stu-id="bb093-113">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="bb093-114">Na przykład jeśli masz `netcoreapp2.1` aplikację i uruchomisz `dotnet run` , dane wyjściowe są umieszczane w `bin/Debug/netcoreapp2.1` .</span><span class="sxs-lookup"><span data-stu-id="bb093-114">For example if you have a `netcoreapp2.1` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp2.1`.</span></span> <span data-ttu-id="bb093-115">Pliki są zastępowane w razie konieczności.</span><span class="sxs-lookup"><span data-stu-id="bb093-115">Files are overwritten as needed.</span></span> <span data-ttu-id="bb093-116">Pliki tymczasowe są umieszczane w `obj` katalogu.</span><span class="sxs-lookup"><span data-stu-id="bb093-116">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="bb093-117">Jeśli projekt określa wiele struktur, wykonanie `dotnet run` powoduje błąd, chyba że `-f|--framework <FRAMEWORK>` opcja jest używana do określenia struktury.</span><span class="sxs-lookup"><span data-stu-id="bb093-117">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="bb093-118">`dotnet run`Polecenie jest używane w kontekście projektów, nieskompilowanych zestawów.</span><span class="sxs-lookup"><span data-stu-id="bb093-118">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="bb093-119">Jeśli próbujesz uruchomić bibliotekę DLL aplikacji zależnej od platformy, musisz użyć [dotnet](dotnet.md) bez polecenia.</span><span class="sxs-lookup"><span data-stu-id="bb093-119">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="bb093-120">Na przykład aby uruchomić `myapp.dll` polecenie, użyj:</span><span class="sxs-lookup"><span data-stu-id="bb093-120">For example, to run `myapp.dll`, use:</span></span>

```dotnetcli
dotnet myapp.dll
```

<span data-ttu-id="bb093-121">Aby uzyskać więcej informacji na temat `dotnet` sterownika, zobacz temat [narzędzia wiersza polecenia (CLI) platformy .NET](index.md) .</span><span class="sxs-lookup"><span data-stu-id="bb093-121">For more information on the `dotnet` driver, see the [.NET Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="bb093-122">Aby uruchomić aplikację, `dotnet run` polecenie rozwiązuje zależności aplikacji, które są poza udostępnionym środowiskiem uruchomieniowym z pamięci podręcznej NuGet.</span><span class="sxs-lookup"><span data-stu-id="bb093-122">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="bb093-123">Ponieważ używa on buforowanych zależności, nie jest zalecane do `dotnet run` uruchamiania aplikacji w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="bb093-123">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="bb093-124">Zamiast tego [Utwórz wdrożenie](../deploying/index.md) przy użyciu [`dotnet publish`](dotnet-publish.md) polecenia i Wdróż opublikowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="bb093-124">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="bb093-125">Przywracanie niejawne</span><span class="sxs-lookup"><span data-stu-id="bb093-125">Implicit restore</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="bb093-126">Opcje</span><span class="sxs-lookup"><span data-stu-id="bb093-126">Options</span></span>

- **`--`**

  <span data-ttu-id="bb093-127">Ogranicza argumenty `dotnet run` od argumentów dla uruchamianej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bb093-127">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="bb093-128">Wszystkie argumenty po tym ograniczniku są przesyłane do uruchomienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bb093-128">All arguments after this delimiter are passed to the application run.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="bb093-129">Definiuje konfigurację kompilacji.</span><span class="sxs-lookup"><span data-stu-id="bb093-129">Defines the build configuration.</span></span> <span data-ttu-id="bb093-130">Wartością domyślną dla większości projektów jest `Debug` , ale można zastąpić ustawienia konfiguracji kompilacji w projekcie.</span><span class="sxs-lookup"><span data-stu-id="bb093-130">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="bb093-131">Kompiluje i uruchamia aplikację przy użyciu określonej [struktury](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="bb093-131">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="bb093-132">Struktura musi być określona w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="bb093-132">The framework must be specified in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="bb093-133">Wymusza rozpoznanie wszystkich zależności, nawet jeśli ostatnie przywracanie zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="bb093-133">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="bb093-134">Określenie tej flagi jest takie samo jak usuwanie *project.assets.jsw* pliku.</span><span class="sxs-lookup"><span data-stu-id="bb093-134">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="bb093-135">Drukuje krótką pomoc dla polecenia.</span><span class="sxs-lookup"><span data-stu-id="bb093-135">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="bb093-136">Zezwala na zatrzymanie polecenia i oczekiwanie na dane wejściowe użytkownika lub akcję (na przykład w celu ukończenia uwierzytelniania).</span><span class="sxs-lookup"><span data-stu-id="bb093-136">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="bb093-137">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="bb093-137">Available since .NET Core 3.0 SDK.</span></span>

- **`--launch-profile <NAME>`**

  <span data-ttu-id="bb093-138">Nazwa profilu uruchamiania (jeśli istnieje) do użycia podczas uruchamiania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bb093-138">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="bb093-139">Profile uruchamiania są zdefiniowane w *launchSettings.js* pliku i są zwykle nazywane `Development` , `Staging` i `Production` .</span><span class="sxs-lookup"><span data-stu-id="bb093-139">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="bb093-140">Aby uzyskać więcej informacji, zobacz [Praca z wieloma środowiskami](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="bb093-140">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

- **`--no-build`**

  <span data-ttu-id="bb093-141">Nie kompiluje projektu przed uruchomieniem.</span><span class="sxs-lookup"><span data-stu-id="bb093-141">Doesn't build the project before running.</span></span> <span data-ttu-id="bb093-142">Również niejawne ustawia `--no-restore` flagę.</span><span class="sxs-lookup"><span data-stu-id="bb093-142">It also implicit sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="bb093-143">W przypadku przywracania projektu z odwołaniami do projektu (P2P) program przywraca projekt główny, a nie odwołania.</span><span class="sxs-lookup"><span data-stu-id="bb093-143">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

- **`--no-launch-profile`**

  <span data-ttu-id="bb093-144">Nie próbuje użyć *launchSettings.jsw* celu skonfigurowania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bb093-144">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

- **`--no-restore`**

  <span data-ttu-id="bb093-145">Nie wykonuje przywracania niejawnego podczas wykonywania polecenia.</span><span class="sxs-lookup"><span data-stu-id="bb093-145">Doesn't execute an implicit restore when running the command.</span></span>

- **`-p|--project <PATH>`**

  <span data-ttu-id="bb093-146">Określa ścieżkę do pliku projektu do uruchomienia (nazwa folderu lub pełna ścieżka).</span><span class="sxs-lookup"><span data-stu-id="bb093-146">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="bb093-147">Jeśli nie zostanie określony, domyślnie jest bieżącym katalogiem.</span><span class="sxs-lookup"><span data-stu-id="bb093-147">If not specified, it defaults to the current directory.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="bb093-148">Określa docelowy środowisko uruchomieniowe, dla którego mają zostać przywrócone pakiety.</span><span class="sxs-lookup"><span data-stu-id="bb093-148">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="bb093-149">Aby uzyskać listę identyfikatorów środowiska uruchomieniowego (RID), zobacz [wykaz identyfikatorów RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="bb093-149">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="bb093-150">`-r` Krótka opcja dostępna od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="bb093-150">`-r` short option available since .NET Core 3.0 SDK.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="bb093-151">Ustawia poziom szczegółowości polecenia.</span><span class="sxs-lookup"><span data-stu-id="bb093-151">Sets the verbosity level of the command.</span></span> <span data-ttu-id="bb093-152">Dozwolone wartości to `q[uiet]` , `m[inimal]` , `n[ormal]` , `d[etailed]` i `diag[nostic]` .</span><span class="sxs-lookup"><span data-stu-id="bb093-152">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="bb093-153">Wartość domyślna to `m`.</span><span class="sxs-lookup"><span data-stu-id="bb093-153">The default value is `m`.</span></span> <span data-ttu-id="bb093-154">Dostępne od wersji .NET Core 2,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="bb093-154">Available since .NET Core 2.1 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="bb093-155">Przykłady</span><span class="sxs-lookup"><span data-stu-id="bb093-155">Examples</span></span>

- <span data-ttu-id="bb093-156">Uruchom projekt w bieżącym katalogu:</span><span class="sxs-lookup"><span data-stu-id="bb093-156">Run the project in the current directory:</span></span>

  ```dotnetcli
  dotnet run
  ```

- <span data-ttu-id="bb093-157">Uruchom określony projekt:</span><span class="sxs-lookup"><span data-stu-id="bb093-157">Run the specified project:</span></span>

  ```dotnetcli
  dotnet run --project ./projects/proj1/proj1.csproj
  ```

- <span data-ttu-id="bb093-158">Uruchom projekt w bieżącym katalogu ( `--help` argument w tym przykładzie jest przesyłany do aplikacji, ponieważ `--` jest używana opcja pusta):</span><span class="sxs-lookup"><span data-stu-id="bb093-158">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

  ```dotnetcli
  dotnet run --configuration Release -- --help
  ```

- <span data-ttu-id="bb093-159">Przywróć zależności i narzędzia dla projektu w bieżącym katalogu, wyświetlając tylko minimalne dane wyjściowe, a następnie Uruchom projekt:</span><span class="sxs-lookup"><span data-stu-id="bb093-159">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project:</span></span>

  ```dotnetcli
  dotnet run --verbosity m
  ```
