---
title: dotnet-Counters — .NET Core
description: Dowiedz się, jak zainstalować i użyć narzędzia wiersza polecenia programu dotnet-Counter.
ms.date: 02/26/2020
ms.openlocfilehash: 6a4fd92540dbc16173dfa3a10ff9dfaa1f31f7d0
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062902"
---
# <a name="dotnet-counters"></a><span data-ttu-id="3e5d8-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="3e5d8-103">dotnet-counters</span></span>

<span data-ttu-id="3e5d8-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 3,0 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="3e5d8-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="3e5d8-105">Zainstaluj dotnet-Counters</span><span class="sxs-lookup"><span data-stu-id="3e5d8-105">Install dotnet-counters</span></span>

<span data-ttu-id="3e5d8-106">Aby zainstalować najnowszą wersję `dotnet-counters` [pakietu NuGet](https://www.nuget.org/packages/dotnet-counters), użyj polecenia [Narzędzia dotnet Install](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="3e5d8-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="3e5d8-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="3e5d8-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="3e5d8-108">Opis</span><span class="sxs-lookup"><span data-stu-id="3e5d8-108">Description</span></span>

<span data-ttu-id="3e5d8-109">`dotnet-counters`jest narzędziem do monitorowania wydajności w przypadku monitorowania kondycji ad hoc i badania wydajności pierwszego poziomu.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="3e5d8-110">Może obserwować wartości liczników wydajności, które są publikowane za pośrednictwem <xref:System.Diagnostics.Tracing.EventCounter> interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="3e5d8-111">Można na przykład szybko monitorować elementy, takie jak użycie procesora CPU lub częstotliwość zgłaszania wyjątków w aplikacji .NET Core, aby sprawdzić, czy istnieją jakieś podejrzane informacje przed uzyskaniem bardziej poważnych badań wydajności przy użyciu `PerfView` lub `dotnet-trace` .</span><span class="sxs-lookup"><span data-stu-id="3e5d8-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="3e5d8-112">Opcje</span><span class="sxs-lookup"><span data-stu-id="3e5d8-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="3e5d8-113">Wyświetla wersję narzędzia dotnet-Counters.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="3e5d8-114">Wyświetla pomoc w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="3e5d8-115">Polecenia</span><span class="sxs-lookup"><span data-stu-id="3e5d8-115">Commands</span></span>

| <span data-ttu-id="3e5d8-116">Polecenie</span><span class="sxs-lookup"><span data-stu-id="3e5d8-116">Command</span></span>                                             |
|-----------------------------------------------------|
| [<span data-ttu-id="3e5d8-117">dotnet — Zbieranie liczników</span><span class="sxs-lookup"><span data-stu-id="3e5d8-117">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="3e5d8-118">dotnet-lista liczników</span><span class="sxs-lookup"><span data-stu-id="3e5d8-118">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="3e5d8-119">Monitor dotnet-Counters</span><span class="sxs-lookup"><span data-stu-id="3e5d8-119">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="3e5d8-120">dotnet-liczniki PS</span><span class="sxs-lookup"><span data-stu-id="3e5d8-120">dotnet-counters ps</span></span>](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="3e5d8-121">dotnet — Zbieranie liczników</span><span class="sxs-lookup"><span data-stu-id="3e5d8-121">dotnet-counters collect</span></span>

<span data-ttu-id="3e5d8-122">Okresowo Zbieraj wybrane wartości licznika i Eksportuj je do określonego formatu pliku na potrzeby przetwarzania końcowego.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-122">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="3e5d8-123">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="3e5d8-123">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list] [--format] [-o|--output]
```

### <a name="options"></a><span data-ttu-id="3e5d8-124">Opcje</span><span class="sxs-lookup"><span data-stu-id="3e5d8-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="3e5d8-125">Identyfikator procesu, który ma być monitorowany.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-125">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="3e5d8-126">Liczba sekund opóźnienia między aktualizacją wyświetlanych liczników</span><span class="sxs-lookup"><span data-stu-id="3e5d8-126">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="3e5d8-127">Rozdzielana spacjami lista liczników.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-127">A space separated list of counters.</span></span> <span data-ttu-id="3e5d8-128">Można określić liczniki `provider_name[:counter_name]` .</span><span class="sxs-lookup"><span data-stu-id="3e5d8-128">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="3e5d8-129">Jeśli `provider_name` jest używany bez kwalifikacji `counter_name` , wyświetlane są wszystkie liczniki.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-129">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="3e5d8-130">Aby odnaleźć nazwy dostawcy i licznika, użyj polecenia [dotnet-Counters](#dotnet-counters-list) .</span><span class="sxs-lookup"><span data-stu-id="3e5d8-130">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="3e5d8-131">Format do wyeksportowania.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-131">The format to be exported.</span></span> <span data-ttu-id="3e5d8-132">Obecnie dostępne: CSV, JSON.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-132">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="3e5d8-133">Nazwa pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-133">The name of the output file.</span></span>

### <a name="examples"></a><span data-ttu-id="3e5d8-134">Przykłady</span><span class="sxs-lookup"><span data-stu-id="3e5d8-134">Examples</span></span>

- <span data-ttu-id="3e5d8-135">Zbieraj wszystkie liczniki z interwałem odświeżania równym 3 sekund i Generuj wolumin CSV jako dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="3e5d8-135">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="3e5d8-136">dotnet-lista liczników</span><span class="sxs-lookup"><span data-stu-id="3e5d8-136">dotnet-counters list</span></span>

<span data-ttu-id="3e5d8-137">Wyświetla listę nazw liczników i opisów pogrupowanych według dostawcy.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-137">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="3e5d8-138">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="3e5d8-138">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="3e5d8-139">Przykład</span><span class="sxs-lookup"><span data-stu-id="3e5d8-139">Example</span></span>

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
> <span data-ttu-id="3e5d8-140">`Microsoft.AspNetCore.Hosting`Liczniki są wyświetlane, jeśli są zidentyfikowane procesy obsługujące te liczniki, na przykład, gdy aplikacja ASP.NET Core jest uruchomiona na komputerze-hoście.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-140">The `Microsoft.AspNetCore.Hosting` counters are displayed when there are processes identified that support these counters, for example; when an ASP.NET Core application is running on the host machine.</span></span>

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="3e5d8-141">Monitor dotnet-Counters</span><span class="sxs-lookup"><span data-stu-id="3e5d8-141">dotnet-counters monitor</span></span>

<span data-ttu-id="3e5d8-142">Wyświetla okresowe odświeżanie wartości wybranych liczników.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-142">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="3e5d8-143">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="3e5d8-143">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="3e5d8-144">Opcje</span><span class="sxs-lookup"><span data-stu-id="3e5d8-144">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="3e5d8-145">Identyfikator procesu, który ma być monitorowany.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-145">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="3e5d8-146">Liczba sekund opóźnienia między aktualizacją wyświetlanych liczników</span><span class="sxs-lookup"><span data-stu-id="3e5d8-146">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="3e5d8-147">Rozdzielana spacjami lista liczników.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-147">A space separated list of counters.</span></span> <span data-ttu-id="3e5d8-148">Można określić liczniki `provider_name[:counter_name]` .</span><span class="sxs-lookup"><span data-stu-id="3e5d8-148">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="3e5d8-149">Jeśli `provider_name` jest używany bez kwalifikacji `counter_name` , wyświetlane są wszystkie liczniki.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-149">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="3e5d8-150">Aby odnaleźć nazwy dostawcy i licznika, użyj polecenia [dotnet-Counters](#dotnet-counters-list) .</span><span class="sxs-lookup"><span data-stu-id="3e5d8-150">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="3e5d8-151">Przykłady</span><span class="sxs-lookup"><span data-stu-id="3e5d8-151">Examples</span></span>

- <span data-ttu-id="3e5d8-152">Monitoruj wszystkie liczniki z poziomu `System.Runtime` interwału odświeżania wynoszącego 3 sekundy:</span><span class="sxs-lookup"><span data-stu-id="3e5d8-152">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 System.Runtime

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      Working Set (MB)                            1982
      GC Heap Size (MB)                            811
      Gen 0 GC / second                             20
      Gen 1 GC / second                              4
      Gen 2 GC / second                              1
      Number of Exceptions / sec                     4
  ```

- <span data-ttu-id="3e5d8-153">Monitoruj tylko użycie procesora CPU i rozmiar sterty GC z `System.Runtime` :</span><span class="sxs-lookup"><span data-stu-id="3e5d8-153">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="3e5d8-154">Monitoruj `EventCounter` wartości ze zdefiniowanych przez użytkownika `EventSource` .</span><span class="sxs-lookup"><span data-stu-id="3e5d8-154">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="3e5d8-155">Aby uzyskać więcej informacji, zobacz [Samouczek: pomiar wydajności za pomocą EventCounters w programie .NET Core](event-counter-perf.md).</span><span class="sxs-lookup"><span data-stu-id="3e5d8-155">For more information, see [Tutorial: Measure performance using EventCounters in .NET Core](event-counter-perf.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
  
## <a name="dotnet-counters-ps"></a><span data-ttu-id="3e5d8-156">dotnet-liczniki PS</span><span class="sxs-lookup"><span data-stu-id="3e5d8-156">dotnet-counters ps</span></span>

<span data-ttu-id="3e5d8-157">Wyświetl listę procesów dotnet, które mogą być monitorowane.</span><span class="sxs-lookup"><span data-stu-id="3e5d8-157">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="3e5d8-158">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="3e5d8-158">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="3e5d8-159">Przykład</span><span class="sxs-lookup"><span data-stu-id="3e5d8-159">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
