---
title: Omówienie narzędzi diagnostycznych — .NET Core
description: Przegląd narzędzi i technik dostępnych do diagnozowania aplikacji .NET Core.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: c43e661ad8c9f665151e0240bf6b54e61b9acfef
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031920"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="ef55d-103">Jakie narzędzia diagnostyczne są dostępne w środowisku .NET Core?</span><span class="sxs-lookup"><span data-stu-id="ef55d-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="ef55d-104">Oprogramowanie nie zawsze zachowuje się w oczekiwany sposób, ale .NET Core ma narzędzia i interfejsy API, które ułatwią zdiagnozowanie tych problemów szybko i efektywnie.</span><span class="sxs-lookup"><span data-stu-id="ef55d-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="ef55d-105">Ten artykuł ułatwia znalezienie różnych potrzebnych narzędzi.</span><span class="sxs-lookup"><span data-stu-id="ef55d-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="ef55d-106">Debugery zarządzane</span><span class="sxs-lookup"><span data-stu-id="ef55d-106">Managed debuggers</span></span>

<span data-ttu-id="ef55d-107">[Zarządzane debugery](managed-debuggers.md) umożliwiają korzystanie z programu.</span><span class="sxs-lookup"><span data-stu-id="ef55d-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="ef55d-108">Wstrzymywanie, przyrostowe wykonywanie, badanie i wznawianie zawiera szczegółowe informacje o zachowaniu kodu.</span><span class="sxs-lookup"><span data-stu-id="ef55d-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="ef55d-109">Debuger to pierwszy wybór służący do diagnozowania problemów funkcjonalnych, które można łatwo odtworzyć.</span><span class="sxs-lookup"><span data-stu-id="ef55d-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="ef55d-110">Rejestrowanie i śledzenie</span><span class="sxs-lookup"><span data-stu-id="ef55d-110">Logging and tracing</span></span>

<span data-ttu-id="ef55d-111">[Rejestrowanie i śledzenie](logging-tracing.md) to powiązane techniki.</span><span class="sxs-lookup"><span data-stu-id="ef55d-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="ef55d-112">Odnoszą się one do kodu instrumentacji do tworzenia plików dziennika.</span><span class="sxs-lookup"><span data-stu-id="ef55d-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="ef55d-113">Pliki rejestrują szczegóły działania programu.</span><span class="sxs-lookup"><span data-stu-id="ef55d-113">The files record the details of what a program does.</span></span> <span data-ttu-id="ef55d-114">Te szczegółowe informacje mogą służyć do diagnozowania najbardziej złożonych problemów.</span><span class="sxs-lookup"><span data-stu-id="ef55d-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="ef55d-115">W połączeniu z sygnaturami czasowymi te techniki są również przydatne w badaniach wydajności.</span><span class="sxs-lookup"><span data-stu-id="ef55d-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="ef55d-116">Testowanie jednostek</span><span class="sxs-lookup"><span data-stu-id="ef55d-116">Unit testing</span></span>

<span data-ttu-id="ef55d-117">[Testowanie jednostkowe](../testing/index.md) to kluczowy składnik ciągłej integracji i wdrażania wysokiej jakości oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="ef55d-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="ef55d-118">Testy jednostkowe zostały zaprojektowane w celu zapewnienia wczesnego ostrzegania w przypadku wystąpienia elementu.</span><span class="sxs-lookup"><span data-stu-id="ef55d-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="dumps"></a><span data-ttu-id="ef55d-119">Zrzuty</span><span class="sxs-lookup"><span data-stu-id="ef55d-119">Dumps</span></span>

<span data-ttu-id="ef55d-120">[Zrzut](./dumps.md) to plik zawierający migawkę procesu w momencie tworzenia.</span><span class="sxs-lookup"><span data-stu-id="ef55d-120">A [dump](./dumps.md) is a file that contains a snapshot of the process at the time of creation.</span></span> <span data-ttu-id="ef55d-121">Mogą one być przydatne do sprawdzania stanu aplikacji na potrzeby debugowania.</span><span class="sxs-lookup"><span data-stu-id="ef55d-121">These can be useful for examining the state of your application for debugging purposes.</span></span>

## <a name="collect-diagnostics-in-containers"></a><span data-ttu-id="ef55d-122">Zbieranie danych diagnostycznych w kontenerach</span><span class="sxs-lookup"><span data-stu-id="ef55d-122">Collect diagnostics in containers</span></span>

<span data-ttu-id="ef55d-123">Te same narzędzia diagnostyczne, które są używane w środowiskach z systemem Linux, mogą również służyć do [zbierania danych diagnostycznych w kontenerach](diagnostics-in-containers.md).</span><span class="sxs-lookup"><span data-stu-id="ef55d-123">The same diagnostics tools that are used in non-containerized Linux environments can also be used to [collect diagnostics in containers](diagnostics-in-containers.md).</span></span> <span data-ttu-id="ef55d-124">Istnieje tylko kilka zmian użycia wymaganych do upewnienia się, że narzędzia działają w kontenerze platformy Docker.</span><span class="sxs-lookup"><span data-stu-id="ef55d-124">There are just a few usage changes needed to make sure the tools work in a Docker container.</span></span>

## <a name="debug-linux-dumps"></a><span data-ttu-id="ef55d-125">Debugowanie zrzutów systemu Linux</span><span class="sxs-lookup"><span data-stu-id="ef55d-125">Debug Linux dumps</span></span>

<span data-ttu-id="ef55d-126">[Debugowanie zrzutów systemu Linux](debug-linux-dumps.md) wyjaśnia, jak zbierać i analizować zrzuty w systemie Linux.</span><span class="sxs-lookup"><span data-stu-id="ef55d-126">[Debug Linux dumps](debug-linux-dumps.md) explains how to collect and analyze dumps on Linux.</span></span>

## <a name="net-core-diagnostic-global-tools"></a><span data-ttu-id="ef55d-127">Narzędzia diagnostyczne programu .NET Core</span><span class="sxs-lookup"><span data-stu-id="ef55d-127">.NET Core diagnostic global tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="ef55d-128">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="ef55d-128">dotnet-counters</span></span>

<span data-ttu-id="ef55d-129">[dotnet-Counters](dotnet-counters.md) to narzędzie do monitorowania wydajności służące do monitorowania kondycji pierwszego poziomu i badania wydajności.</span><span class="sxs-lookup"><span data-stu-id="ef55d-129">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="ef55d-130">Obserwuje wartości liczników wydajności publikowane za pośrednictwem <xref:System.Diagnostics.Tracing.EventCounter> interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="ef55d-130">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="ef55d-131">Można na przykład szybko monitorować elementy, takie jak użycie procesora CPU, lub częstotliwość zgłaszania wyjątków w aplikacji .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ef55d-131">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="ef55d-132">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="ef55d-132">dotnet-dump</span></span>

<span data-ttu-id="ef55d-133">Narzędzie [dotnet-dump](dotnet-dump.md) to sposób zbierania i analizowania zrzutów podstawowych systemów Windows i Linux bez natywnego debugera.</span><span class="sxs-lookup"><span data-stu-id="ef55d-133">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-gcdump"></a><span data-ttu-id="ef55d-134">dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="ef55d-134">dotnet-gcdump</span></span>

<span data-ttu-id="ef55d-135">Narzędzie [dotnet-gcdump](dotnet-gcdump.md) to sposób zbierania zrzutów pamięci podręcznej (Moduł wyrzucania elementów bezużytecznych) na żywo procesów platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="ef55d-135">The [dotnet-gcdump](dotnet-gcdump.md) tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="ef55d-136">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="ef55d-136">dotnet-trace</span></span>

<span data-ttu-id="ef55d-137">Program .NET Core zawiera informacje o tym, w jaki sposób są `EventPipe` udostępniane dane diagnostyczne.</span><span class="sxs-lookup"><span data-stu-id="ef55d-137">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="ef55d-138">Narzędzie do [śledzenia dotnet](dotnet-trace.md) umożliwia korzystanie z interesujących danych profilowania z poziomu aplikacji, które mogą pomóc w scenariuszach, w których konieczne jest powolne działanie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ef55d-138">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

### <a name="dotnet-symbol"></a><span data-ttu-id="ef55d-139">dotnet-symbol</span><span class="sxs-lookup"><span data-stu-id="ef55d-139">dotnet-symbol</span></span>

<span data-ttu-id="ef55d-140">polecenie [dotnet-symbol](dotnet-symbol.md) umożliwia pobieranie plików (symboli, DAC/DBI, plików hosta itp.), które są konieczne do otwarcia podstawowego zrzutu lub minizrzutu.</span><span class="sxs-lookup"><span data-stu-id="ef55d-140">[dotnet-symbol](dotnet-symbol.md) downloads files (symbols, DAC/DBI, host files, etc.) needed to open a core dump or minidump.</span></span> <span data-ttu-id="ef55d-141">Użyj tego narzędzia, jeśli potrzebujesz symboli i modułów do debugowania pliku zrzutu przechwytywanego na innym komputerze.</span><span class="sxs-lookup"><span data-stu-id="ef55d-141">Use this tool if you need symbols and modules to debug a dump file captured on a different machine.</span></span>

### <a name="dotnet-sos"></a><span data-ttu-id="ef55d-142">dotnet-sos</span><span class="sxs-lookup"><span data-stu-id="ef55d-142">dotnet-sos</span></span>

<span data-ttu-id="ef55d-143">[dotnet-sos](dotnet-sos.md) służy do instalowania [rozszerzenia debugowania SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) w systemie Linux lub MacOS (lub w systemie Windows, jeśli są używane starsze narzędzia debugowania).</span><span class="sxs-lookup"><span data-stu-id="ef55d-143">[dotnet-sos](dotnet-sos.md) is used to install the [SOS debugging extension](../../framework/tools/sos-dll-sos-debugging-extension.md) on Linux or MacOS (or on Windows if using older debugging tools).</span></span>

### <a name="perfcollect"></a><span data-ttu-id="ef55d-144">PerfCollect</span><span class="sxs-lookup"><span data-stu-id="ef55d-144">PerfCollect</span></span>

<span data-ttu-id="ef55d-145">[PerfCollect](trace-perfcollect-lttng.md) to skrypt bash, którego można użyć do zbierania śladów z `perf` i `LTTng` bardziej szczegółowej analizy wydajności aplikacji .NET działających w ramach dystrybucji systemu Linux.</span><span class="sxs-lookup"><span data-stu-id="ef55d-145">[PerfCollect](trace-perfcollect-lttng.md) is a bash script you can use to collect traces with `perf` and `LTTng` for a more in-depth performance analysis of .NET apps running on Linux distributions.</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="ef55d-146">Samouczki dotyczące diagnostyki platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="ef55d-146">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="ef55d-147">Debugowanie przecieku pamięci</span><span class="sxs-lookup"><span data-stu-id="ef55d-147">Debug a memory leak</span></span>

<span data-ttu-id="ef55d-148">[Samouczek: debugowanie przecieku pamięci](debug-memory-leak.md) przeprowadzi przez znalezienie przecieku pamięci.</span><span class="sxs-lookup"><span data-stu-id="ef55d-148">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="ef55d-149">Narzędzie [dotnet-Counters](dotnet-counters.md) służy do potwierdzenia przecieku i narzędzia [dotnet-dump](dotnet-dump.md) służy do diagnozowania wycieku.</span><span class="sxs-lookup"><span data-stu-id="ef55d-149">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>

### <a name="debug-high-cpu-usage"></a><span data-ttu-id="ef55d-150">Debugowanie wysokiego użycia procesora</span><span class="sxs-lookup"><span data-stu-id="ef55d-150">Debug high CPU usage</span></span>

<span data-ttu-id="ef55d-151">[Samouczek: debugowanie dużego użycia procesora CPU](debug-highcpu.md) przeprowadzi Cię przez badanie wysokiego użycia procesora CPU.</span><span class="sxs-lookup"><span data-stu-id="ef55d-151">[Tutorial: Debug high CPU usage](debug-highcpu.md) walks you through investigating high CPU usage.</span></span> <span data-ttu-id="ef55d-152">Za pomocą narzędzia [dotnet-Counters](dotnet-counters.md) można potwierdzić duże użycie procesora CPU.</span><span class="sxs-lookup"><span data-stu-id="ef55d-152">It uses the [dotnet-counters](dotnet-counters.md) tool to confirm the high CPU usage.</span></span> <span data-ttu-id="ef55d-153">Następnie przeprowadzi Cię przez proces [śledzenia narzędzia do analizy wydajności ( `dotnet-trace` )](dotnet-trace.md) lub systemu Linux `perf` w celu zbierania i wyświetlania profilu użycia procesora CPU.</span><span class="sxs-lookup"><span data-stu-id="ef55d-153">It then walks you through using [Trace for performance analysis utility (`dotnet-trace`)](dotnet-trace.md) or Linux `perf` to collect and view CPU usage profile.</span></span>

### <a name="debug-deadlock"></a><span data-ttu-id="ef55d-154">Debugowanie zakleszczenia</span><span class="sxs-lookup"><span data-stu-id="ef55d-154">Debug deadlock</span></span>

<span data-ttu-id="ef55d-155">[Samouczek: zakleszczenie debugowania](debug-deadlock.md) pokazuje, w jaki sposób używać narzędzia [dotnet-dump](dotnet-dump.md) do badania wątków i blokad.</span><span class="sxs-lookup"><span data-stu-id="ef55d-155">[Tutorial: Debug deadlock](debug-deadlock.md) shows you how to use the [dotnet-dump](dotnet-dump.md) tool to investigate threads and locks.</span></span>

### <a name="measure-performance-using-eventcounters"></a><span data-ttu-id="ef55d-156">Mierzenie wydajności przy użyciu EventCounters</span><span class="sxs-lookup"><span data-stu-id="ef55d-156">Measure performance using EventCounters</span></span>

<span data-ttu-id="ef55d-157">[Samouczek: pomiar wydajności za pomocą EventCounters w programie .NET](event-counter-perf.md) pokazuje, jak używać <xref:System.Diagnostics.Tracing.EventCounter> interfejsu API do mierzenia wydajności aplikacji .NET.</span><span class="sxs-lookup"><span data-stu-id="ef55d-157">[Tutorial: Measure performance using EventCounters in .NET](event-counter-perf.md) shows you how to use the <xref:System.Diagnostics.Tracing.EventCounter> API to measure performance in your .NET app.</span></span>
