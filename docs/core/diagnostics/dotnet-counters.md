---
title: dotnet-liczniki narzędzia diagnostyczne — interfejs wiersza polecenia platformy .NET
description: Dowiedz się, jak zainstalować i używać narzędzia interfejsu wiersza polecenia dotnet-Counter do monitorowania kondycji ad hoc i badania wydajności pierwszego poziomu.
ms.date: 11/17/2020
ms.openlocfilehash: 7dd4c06f3abe423552ba1d3eb82f6d0c35a84d0b
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822220"
---
# <a name="investigate-performance-counters-dotnet-counters"></a><span data-ttu-id="910e0-103">Badanie liczników wydajności (dotnet-Counters)</span><span class="sxs-lookup"><span data-stu-id="910e0-103">Investigate performance counters (dotnet-counters)</span></span>

<span data-ttu-id="910e0-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 3,0 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="910e0-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="910e0-105">Instalowanie</span><span class="sxs-lookup"><span data-stu-id="910e0-105">Install</span></span>

<span data-ttu-id="910e0-106">Istnieją dwa sposoby na pobranie i zainstalowanie `dotnet-counters` :</span><span class="sxs-lookup"><span data-stu-id="910e0-106">There are two ways to download and install `dotnet-counters`:</span></span>

- <span data-ttu-id="910e0-107">**Narzędzie globalne dotnet:**</span><span class="sxs-lookup"><span data-stu-id="910e0-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="910e0-108">Aby zainstalować najnowszą wersję `dotnet-counters` [pakietu NuGet](https://www.nuget.org/packages/dotnet-counters), użyj polecenia [Narzędzia dotnet Install](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="910e0-108">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-counters
  ```

- <span data-ttu-id="910e0-109">**Pobieranie bezpośrednie:**</span><span class="sxs-lookup"><span data-stu-id="910e0-109">**Direct download:**</span></span>

  <span data-ttu-id="910e0-110">Pobierz plik wykonywalny narzędzia, który jest zgodny z platformą:</span><span class="sxs-lookup"><span data-stu-id="910e0-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="910e0-111">System operacyjny</span><span class="sxs-lookup"><span data-stu-id="910e0-111">OS</span></span>  | <span data-ttu-id="910e0-112">Platforma</span><span class="sxs-lookup"><span data-stu-id="910e0-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="910e0-113">Windows</span><span class="sxs-lookup"><span data-stu-id="910e0-113">Windows</span></span> | <span data-ttu-id="910e0-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [ARM](https://aka.ms/dotnet-counters/win-arm) \| [ARM — x64](https://aka.ms/dotnet-counters/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="910e0-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64)</span></span> |
  | <span data-ttu-id="910e0-115">macOS</span><span class="sxs-lookup"><span data-stu-id="910e0-115">macOS</span></span>   | [<span data-ttu-id="910e0-116">x64</span><span class="sxs-lookup"><span data-stu-id="910e0-116">x64</span></span>](https://aka.ms/dotnet-counters/osx-x64) |
  | <span data-ttu-id="910e0-117">Linux</span><span class="sxs-lookup"><span data-stu-id="910e0-117">Linux</span></span>   | <span data-ttu-id="910e0-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [ARM](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [MUSL — x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [MUSL — arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="910e0-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="910e0-119">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="910e0-119">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="910e0-120">Opis</span><span class="sxs-lookup"><span data-stu-id="910e0-120">Description</span></span>

<span data-ttu-id="910e0-121">`dotnet-counters` jest narzędziem do monitorowania wydajności w przypadku monitorowania kondycji ad hoc i badania wydajności pierwszego poziomu.</span><span class="sxs-lookup"><span data-stu-id="910e0-121">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="910e0-122">Może obserwować wartości liczników wydajności, które są publikowane za pośrednictwem <xref:System.Diagnostics.Tracing.EventCounter> interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="910e0-122">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="910e0-123">Można na przykład szybko monitorować elementy, takie jak użycie procesora CPU lub częstotliwość zgłaszania wyjątków w aplikacji .NET Core, aby sprawdzić, czy istnieją jakieś podejrzane informacje przed uzyskaniem bardziej poważnych badań wydajności przy użyciu `PerfView` lub `dotnet-trace` .</span><span class="sxs-lookup"><span data-stu-id="910e0-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="910e0-124">Opcje</span><span class="sxs-lookup"><span data-stu-id="910e0-124">Options</span></span>

- **`--version`**

  <span data-ttu-id="910e0-125">Wyświetla wersję narzędzia dotnet-Counters.</span><span class="sxs-lookup"><span data-stu-id="910e0-125">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="910e0-126">Wyświetla pomoc w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="910e0-126">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="910e0-127">Polecenia</span><span class="sxs-lookup"><span data-stu-id="910e0-127">Commands</span></span>

| <span data-ttu-id="910e0-128">Polecenie</span><span class="sxs-lookup"><span data-stu-id="910e0-128">Command</span></span>                                             |
|-----------------------------------------------------|
| [<span data-ttu-id="910e0-129">dotnet — Zbieranie liczników</span><span class="sxs-lookup"><span data-stu-id="910e0-129">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="910e0-130">dotnet-lista liczników</span><span class="sxs-lookup"><span data-stu-id="910e0-130">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="910e0-131">Monitor dotnet-Counters</span><span class="sxs-lookup"><span data-stu-id="910e0-131">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="910e0-132">dotnet-liczniki PS</span><span class="sxs-lookup"><span data-stu-id="910e0-132">dotnet-counters ps</span></span>](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="910e0-133">dotnet — Zbieranie liczników</span><span class="sxs-lookup"><span data-stu-id="910e0-133">dotnet-counters collect</span></span>

<span data-ttu-id="910e0-134">Okresowo Zbieraj wybrane wartości licznika i Eksportuj je do określonego formatu pliku na potrzeby przetwarzania końcowego.</span><span class="sxs-lookup"><span data-stu-id="910e0-134">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="910e0-135">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="910e0-135">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [-n|--name] [--refresh-interval] [--counters <COUNTERS>] [--format] [-o|--output] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="910e0-136">Opcje</span><span class="sxs-lookup"><span data-stu-id="910e0-136">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="910e0-137">Identyfikator procesu, z którego mają być zbierane dane licznika.</span><span class="sxs-lookup"><span data-stu-id="910e0-137">The ID of the process to be collect counter data from.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="910e0-138">Nazwa procesu, z którego mają być zbierane dane licznika.</span><span class="sxs-lookup"><span data-stu-id="910e0-138">The name of the process to be collect counter data from.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="910e0-139">Liczba sekund opóźnienia między aktualizacją wyświetlanych liczników</span><span class="sxs-lookup"><span data-stu-id="910e0-139">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="910e0-140">Rozdzielana przecinkami lista liczników.</span><span class="sxs-lookup"><span data-stu-id="910e0-140">A comma-separated list of counters.</span></span> <span data-ttu-id="910e0-141">Można określić liczniki `provider_name[:counter_name]` .</span><span class="sxs-lookup"><span data-stu-id="910e0-141">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="910e0-142">Jeśli `provider_name` jest używany bez listy kwalifikującej się liczników, zostaną wyświetlone wszystkie liczniki od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="910e0-142">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="910e0-143">Aby odnaleźć nazwy dostawcy i licznika, użyj polecenia [dotnet-Counters](#dotnet-counters-list) .</span><span class="sxs-lookup"><span data-stu-id="910e0-143">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="910e0-144">Format do wyeksportowania.</span><span class="sxs-lookup"><span data-stu-id="910e0-144">The format to be exported.</span></span> <span data-ttu-id="910e0-145">Obecnie dostępne: CSV, JSON.</span><span class="sxs-lookup"><span data-stu-id="910e0-145">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="910e0-146">Nazwa pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="910e0-146">The name of the output file.</span></span>

- <span data-ttu-id="910e0-147">**`-- <command>` (w przypadku aplikacji docelowych z uruchomionym programem .NET 5,0 lub nowszym)**</span><span class="sxs-lookup"><span data-stu-id="910e0-147">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="910e0-148">Po określeniu parametrów konfiguracji kolekcji użytkownik może dołączyć `--` po nim polecenie, aby uruchomić aplikację .NET z co najmniej 5,0 środowiskiem uruchomieniowym.</span><span class="sxs-lookup"><span data-stu-id="910e0-148">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="910e0-149">`dotnet-counters` uruchomi proces za pomocą podanego polecenia i zbierze żądane metryki.</span><span class="sxs-lookup"><span data-stu-id="910e0-149">`dotnet-counters` will launch a process with the provided command and collect the requested metrics.</span></span> <span data-ttu-id="910e0-150">Jest to często przydatne do zbierania metryk dla ścieżki uruchamiania aplikacji i może służyć do diagnozowania lub monitorowania problemów, które występują wczesne przed lub wkrótce po głównym punkcie wejścia.</span><span class="sxs-lookup"><span data-stu-id="910e0-150">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="910e0-151">Użycie tej opcji monitoruje pierwszy proces programu .NET 5,0, który komunikuje się z powrotem z narzędziem, co oznacza, że polecenie uruchamia wiele aplikacji .NET będzie zbierać tylko pierwszą aplikację.</span><span class="sxs-lookup"><span data-stu-id="910e0-151">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="910e0-152">W związku z tym zaleca się używanie tej opcji w aplikacjach samodzielnych lub przy użyciu `dotnet exec <app.dll>` opcji.</span><span class="sxs-lookup"><span data-stu-id="910e0-152">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

### <a name="examples"></a><span data-ttu-id="910e0-153">Przykłady</span><span class="sxs-lookup"><span data-stu-id="910e0-153">Examples</span></span>

- <span data-ttu-id="910e0-154">Zbieraj wszystkie liczniki z interwałem odświeżania równym 3 sekund i Generuj wolumin CSV jako dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="910e0-154">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

- <span data-ttu-id="910e0-155">Uruchom `dotnet mvc.dll` jako proces podrzędny i Rozpocznij zbieranie liczników środowiska uruchomieniowego oraz ASP.NET Core hostowanie liczników z uruchamiania i Zapisz je jako dane wyjściowe JSON:</span><span class="sxs-lookup"><span data-stu-id="910e0-155">Start `dotnet mvc.dll` as a child process and start collecting runtime counters and ASP.NET Core Hosting counters from startup and save it as a JSON output:</span></span>

  ```console
  > dotnet-counters collect --format json --counters System.Runtime,Microsoft.AspNetCore.Hosting -- dotnet mvc.dll
  Starting a counter session. Press Q to quit.
  File saved to counter.json
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="910e0-156">dotnet-lista liczników</span><span class="sxs-lookup"><span data-stu-id="910e0-156">dotnet-counters list</span></span>

<span data-ttu-id="910e0-157">Wyświetla listę nazw liczników i opisów pogrupowanych według dostawcy.</span><span class="sxs-lookup"><span data-stu-id="910e0-157">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="910e0-158">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="910e0-158">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="910e0-159">Przykład</span><span class="sxs-lookup"><span data-stu-id="910e0-159">Example</span></span>

```console
> dotnet-counters list
Showing well-known counters only. Specific processes may support additional counters.

System.Runtime
    cpu-usage                                    Amount of time the process has utilized the CPU (ms)
    working-set                                  Amount of working set used by the process (MB)
    gc-heap-size                                 Total heap size reported by the GC (MB)
    gen-0-gc-count                               Number of Gen 0 GCs / min
    gen-1-gc-count                               Number of Gen 1 GCs / min
    gen-2-gc-count                               Number of Gen 2 GCs / min
    time-in-gc                                   % time in GC since the last GC
    gen-0-size                                   Gen 0 Heap Size
    gen-1-size                                   Gen 1 Heap Size
    gen-2-size                                   Gen 2 Heap Size
    loh-size                                     LOH Heap Size
    alloc-rate                                   Allocation Rate
    assembly-count                               Number of Assemblies Loaded
    exception-count                              Number of Exceptions / sec
    threadpool-thread-count                      Number of ThreadPool Threads
    monitor-lock-contention-count                Monitor Lock Contention Count
    threadpool-queue-length                      ThreadPool Work Items Queue Length
    threadpool-completed-items-count             ThreadPool Completed Work Items Count
    active-timer-count                           Active Timers Count

Microsoft.AspNetCore.Hosting
    requests-per-second                  Request rate
    total-requests                       Total number of requests
    current-requests                     Current number of requests
    failed-requests                      Failed number of requests
```

> [!NOTE]
> <span data-ttu-id="910e0-160">`Microsoft.AspNetCore.Hosting`Liczniki są wyświetlane, jeśli są zidentyfikowane procesy obsługujące te liczniki, na przykład, gdy aplikacja ASP.NET Core jest uruchomiona na komputerze-hoście.</span><span class="sxs-lookup"><span data-stu-id="910e0-160">The `Microsoft.AspNetCore.Hosting` counters are displayed when there are processes identified that support these counters, for example; when an ASP.NET Core application is running on the host machine.</span></span>

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="910e0-161">Monitor dotnet-Counters</span><span class="sxs-lookup"><span data-stu-id="910e0-161">dotnet-counters monitor</span></span>

<span data-ttu-id="910e0-162">Wyświetla okresowe odświeżanie wartości wybranych liczników.</span><span class="sxs-lookup"><span data-stu-id="910e0-162">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="910e0-163">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="910e0-163">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [-n|--name] [--refresh-interval] [--counters] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="910e0-164">Opcje</span><span class="sxs-lookup"><span data-stu-id="910e0-164">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="910e0-165">Identyfikator procesu, który ma być monitorowany.</span><span class="sxs-lookup"><span data-stu-id="910e0-165">The ID of the process to be monitored.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="910e0-166">Nazwa procesu, który ma być monitorowany.</span><span class="sxs-lookup"><span data-stu-id="910e0-166">The name of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="910e0-167">Liczba sekund opóźnienia między aktualizacją wyświetlanych liczników</span><span class="sxs-lookup"><span data-stu-id="910e0-167">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="910e0-168">Rozdzielana przecinkami lista liczników.</span><span class="sxs-lookup"><span data-stu-id="910e0-168">A comma-separated list of counters.</span></span> <span data-ttu-id="910e0-169">Można określić liczniki `provider_name[:counter_name]` .</span><span class="sxs-lookup"><span data-stu-id="910e0-169">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="910e0-170">Jeśli `provider_name` jest używany bez listy kwalifikującej się liczników, zostaną wyświetlone wszystkie liczniki od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="910e0-170">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="910e0-171">Aby odnaleźć nazwy dostawcy i licznika, użyj polecenia [dotnet-Counters](#dotnet-counters-list) .</span><span class="sxs-lookup"><span data-stu-id="910e0-171">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

 <span data-ttu-id="910e0-172">**`-- <command>` (w przypadku aplikacji docelowych z uruchomionym programem .NET 5,0 lub nowszym)**</span><span class="sxs-lookup"><span data-stu-id="910e0-172">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="910e0-173">Po określeniu parametrów konfiguracji kolekcji użytkownik może dołączyć `--` po nim polecenie, aby uruchomić aplikację .NET z co najmniej 5,0 środowiskiem uruchomieniowym.</span><span class="sxs-lookup"><span data-stu-id="910e0-173">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="910e0-174">`dotnet-counters` uruchomi proces za pomocą podanego polecenia i monitoruje żądane metryki.</span><span class="sxs-lookup"><span data-stu-id="910e0-174">`dotnet-counters` will launch a process with the provided command and monitor the requested metrics.</span></span> <span data-ttu-id="910e0-175">Jest to często przydatne do zbierania metryk dla ścieżki uruchamiania aplikacji i może służyć do diagnozowania lub monitorowania problemów, które występują wczesne przed lub wkrótce po głównym punkcie wejścia.</span><span class="sxs-lookup"><span data-stu-id="910e0-175">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="910e0-176">Użycie tej opcji monitoruje pierwszy proces programu .NET 5,0, który komunikuje się z powrotem z narzędziem, co oznacza, że polecenie uruchamia wiele aplikacji .NET będzie zbierać tylko pierwszą aplikację.</span><span class="sxs-lookup"><span data-stu-id="910e0-176">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="910e0-177">W związku z tym zaleca się używanie tej opcji w aplikacjach samodzielnych lub przy użyciu `dotnet exec <app.dll>` opcji.</span><span class="sxs-lookup"><span data-stu-id="910e0-177">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

### <a name="examples"></a><span data-ttu-id="910e0-178">Przykłady</span><span class="sxs-lookup"><span data-stu-id="910e0-178">Examples</span></span>

- <span data-ttu-id="910e0-179">Monitoruj wszystkie liczniki z poziomu `System.Runtime` interwału odświeżania wynoszącego 3 sekundy:</span><span class="sxs-lookup"><span data-stu-id="910e0-179">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 --counters System.Runtime
  Press p to pause, r to resume, q to quit.
      Status: Running

  [System.Runtime]
      % Time in GC since last GC (%)                                 0
      Allocation Rate (B / 1 sec)                                5,376
      CPU Usage (%)                                                  0
      Exception Count (Count / 1 sec)                                0
      GC Fragmentation (%)                                          48.467
      GC Heap Size (MB)                                              0
      Gen 0 GC Count (Count / 1 sec)                                 1
      Gen 0 Size (B)                                                24
      Gen 1 GC Count (Count / 1 sec)                                 1
      Gen 1 Size (B)                                                24
      Gen 2 GC Count (Count / 1 sec)                                 1
      Gen 2 Size (B)                                           272,000
      IL Bytes Jitted (B)                                       19,449
      LOH Size (B)                                              19,640
      Monitor Lock Contention Count (Count / 1 sec)                  0
      Number of Active Timers                                        0
      Number of Assemblies Loaded                                    7
      Number of Methods Jitted                                     166
      POH (Pinned Object Heap) Size (B)                             24
      ThreadPool Completed Work Item Count (Count / 1 sec)           0
      ThreadPool Queue Length                                        0
      ThreadPool Thread Count                                        2
      Working Set (MB)                                              19
  ```

- <span data-ttu-id="910e0-180">Monitoruj tylko użycie procesora CPU i rozmiar sterty GC z `System.Runtime` :</span><span class="sxs-lookup"><span data-stu-id="910e0-180">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="910e0-181">Monitoruj `EventCounter` wartości ze zdefiniowanych przez użytkownika `EventSource` .</span><span class="sxs-lookup"><span data-stu-id="910e0-181">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="910e0-182">Aby uzyskać więcej informacji, zobacz [Samouczek: pomiar wydajności za pomocą EventCounters w programie .NET Core](event-counter-perf.md).</span><span class="sxs-lookup"><span data-stu-id="910e0-182">For more information, see [Tutorial: Measure performance using EventCounters in .NET Core](event-counter-perf.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```

- <span data-ttu-id="910e0-183">Uruchom `my-aspnet-server.exe` i monitoruj liczbę zestawów załadowanych z jego uruchamiania (tylko .net 5,0 lub nowszy):</span><span class="sxs-lookup"><span data-stu-id="910e0-183">Launch `my-aspnet-server.exe` and monitor the # of assemblies loaded from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="910e0-184">Działa to w przypadku aplikacji z uruchomionym programem .NET 5,0 lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="910e0-184">This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[assembly-count] -- my-aspnet-server.exe

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      Number of Assemblies Loaded                   24
  ```
  
- <span data-ttu-id="910e0-185">Uruchom `my-aspnet-server.exe` z `arg1` i `arg2` jako argumenty wiersza polecenia oraz Monitoruj swój zestaw roboczy i rozmiar sterty GC, korzystając z jego uruchamiania (tylko .NET 5,0 lub nowszy):</span><span class="sxs-lookup"><span data-stu-id="910e0-185">Launch `my-aspnet-server.exe` with `arg1` and `arg2` as command-line arguments and monitor its working set and GC heap size from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="910e0-186">Działa to w przypadku aplikacji z uruchomionym programem .NET 5,0 lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="910e0-186">This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[working-set,gc-heap-size] -- my-aspnet-server.exe arg1 arg2
  ```

  ```console
  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      GC Heap Size (MB)                                 39
      Working Set (MB)                                  59
  ```

## <a name="dotnet-counters-ps"></a><span data-ttu-id="910e0-187">dotnet-liczniki PS</span><span class="sxs-lookup"><span data-stu-id="910e0-187">dotnet-counters ps</span></span>

<span data-ttu-id="910e0-188">Wyświetl listę procesów dotnet, które mogą być monitorowane.</span><span class="sxs-lookup"><span data-stu-id="910e0-188">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="910e0-189">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="910e0-189">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="910e0-190">Przykład</span><span class="sxs-lookup"><span data-stu-id="910e0-190">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
