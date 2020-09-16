---
title: Omówienie narzędzi diagnostycznych — .NET Core
description: Przegląd narzędzi i technik dostępnych do diagnozowania aplikacji .NET Core.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: e97acccbe3bdd577ee600cefb9f1f0528d3c1ac0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538530"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="e97e6-103">Jakie narzędzia diagnostyczne są dostępne w środowisku .NET Core?</span><span class="sxs-lookup"><span data-stu-id="e97e6-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="e97e6-104">Oprogramowanie nie zawsze zachowuje się w oczekiwany sposób, ale .NET Core ma narzędzia i interfejsy API, które ułatwią zdiagnozowanie tych problemów szybko i efektywnie.</span><span class="sxs-lookup"><span data-stu-id="e97e6-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="e97e6-105">Ten artykuł ułatwia znalezienie różnych potrzebnych narzędzi.</span><span class="sxs-lookup"><span data-stu-id="e97e6-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="e97e6-106">Debugery zarządzane</span><span class="sxs-lookup"><span data-stu-id="e97e6-106">Managed debuggers</span></span>

<span data-ttu-id="e97e6-107">[Zarządzane debugery](managed-debuggers.md) umożliwiają korzystanie z programu.</span><span class="sxs-lookup"><span data-stu-id="e97e6-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="e97e6-108">Wstrzymywanie, przyrostowe wykonywanie, badanie i wznawianie zawiera szczegółowe informacje o zachowaniu kodu.</span><span class="sxs-lookup"><span data-stu-id="e97e6-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="e97e6-109">Debuger to pierwszy wybór służący do diagnozowania problemów funkcjonalnych, które można łatwo odtworzyć.</span><span class="sxs-lookup"><span data-stu-id="e97e6-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="e97e6-110">Rejestrowanie i śledzenie</span><span class="sxs-lookup"><span data-stu-id="e97e6-110">Logging and tracing</span></span>

<span data-ttu-id="e97e6-111">[Rejestrowanie i śledzenie](logging-tracing.md) to powiązane techniki.</span><span class="sxs-lookup"><span data-stu-id="e97e6-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="e97e6-112">Odnoszą się one do kodu instrumentacji do tworzenia plików dziennika.</span><span class="sxs-lookup"><span data-stu-id="e97e6-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="e97e6-113">Pliki rejestrują szczegóły działania programu.</span><span class="sxs-lookup"><span data-stu-id="e97e6-113">The files record the details of what a program does.</span></span> <span data-ttu-id="e97e6-114">Te szczegółowe informacje mogą służyć do diagnozowania najbardziej złożonych problemów.</span><span class="sxs-lookup"><span data-stu-id="e97e6-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="e97e6-115">W połączeniu z sygnaturami czasowymi te techniki są również przydatne w badaniach wydajności.</span><span class="sxs-lookup"><span data-stu-id="e97e6-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="e97e6-116">Testowanie jednostek</span><span class="sxs-lookup"><span data-stu-id="e97e6-116">Unit testing</span></span>

<span data-ttu-id="e97e6-117">[Testowanie jednostkowe](../testing/index.md) to kluczowy składnik ciągłej integracji i wdrażania wysokiej jakości oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="e97e6-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="e97e6-118">Testy jednostkowe zostały zaprojektowane w celu zapewnienia wczesnego ostrzegania w przypadku wystąpienia elementu.</span><span class="sxs-lookup"><span data-stu-id="e97e6-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="debug-linux-dumps"></a><span data-ttu-id="e97e6-119">Debugowanie zrzutów systemu Linux</span><span class="sxs-lookup"><span data-stu-id="e97e6-119">Debug Linux dumps</span></span>

<span data-ttu-id="e97e6-120">[Debugowanie zrzutów systemu Linux](debug-linux-dumps.md) wyjaśnia, jak zbierać i analizować zrzuty w systemie Linux.</span><span class="sxs-lookup"><span data-stu-id="e97e6-120">[Debug Linux dumps](debug-linux-dumps.md) explains how to collect and analyze dumps on Linux.</span></span>

## <a name="net-core-diagnostic-global-tools"></a><span data-ttu-id="e97e6-121">Narzędzia diagnostyczne programu .NET Core</span><span class="sxs-lookup"><span data-stu-id="e97e6-121">.NET Core diagnostic global tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="e97e6-122">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="e97e6-122">dotnet-counters</span></span>

<span data-ttu-id="e97e6-123">[dotnet-Counters](dotnet-counters.md) to narzędzie do monitorowania wydajności służące do monitorowania kondycji pierwszego poziomu i badania wydajności.</span><span class="sxs-lookup"><span data-stu-id="e97e6-123">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="e97e6-124">Obserwuje wartości liczników wydajności publikowane za pośrednictwem <xref:System.Diagnostics.Tracing.EventCounter> interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="e97e6-124">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="e97e6-125">Można na przykład szybko monitorować elementy, takie jak użycie procesora CPU, lub częstotliwość zgłaszania wyjątków w aplikacji .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e97e6-125">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="e97e6-126">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="e97e6-126">dotnet-dump</span></span>

<span data-ttu-id="e97e6-127">Narzędzie [dotnet-dump](dotnet-dump.md) to sposób zbierania i analizowania zrzutów podstawowych systemów Windows i Linux bez natywnego debugera.</span><span class="sxs-lookup"><span data-stu-id="e97e6-127">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-gcdump"></a><span data-ttu-id="e97e6-128">dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="e97e6-128">dotnet-gcdump</span></span>

<span data-ttu-id="e97e6-129">Narzędzie [dotnet-gcdump](dotnet-gcdump.md) to sposób zbierania zrzutów pamięci podręcznej (Moduł wyrzucania elementów bezużytecznych) na żywo procesów platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="e97e6-129">The [dotnet-gcdump](dotnet-gcdump.md) tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="e97e6-130">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="e97e6-130">dotnet-trace</span></span>

<span data-ttu-id="e97e6-131">Program .NET Core zawiera informacje o tym, w jaki sposób są `EventPipe` udostępniane dane diagnostyczne.</span><span class="sxs-lookup"><span data-stu-id="e97e6-131">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="e97e6-132">Narzędzie do [śledzenia dotnet](dotnet-trace.md) umożliwia korzystanie z interesujących danych profilowania z poziomu aplikacji, które mogą pomóc w scenariuszach, w których konieczne jest powolne działanie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e97e6-132">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

### <a name="dotnet-symbol"></a><span data-ttu-id="e97e6-133">dotnet-symbol</span><span class="sxs-lookup"><span data-stu-id="e97e6-133">dotnet-symbol</span></span>

<span data-ttu-id="e97e6-134">polecenie [dotnet-symbol](dotnet-symbol.md) umożliwia pobieranie plików (symboli, DAC/DBI, plików hosta itp.), które są konieczne do otwarcia podstawowego zrzutu lub minizrzutu.</span><span class="sxs-lookup"><span data-stu-id="e97e6-134">[dotnet-symbol](dotnet-symbol.md) downloads files (symbols, DAC/DBI, host files, etc.) needed to open a core dump or minidump.</span></span> <span data-ttu-id="e97e6-135">Użyj tego narzędzia, jeśli potrzebujesz symboli i modułów do debugowania pliku zrzutu przechwytywanego na innym komputerze.</span><span class="sxs-lookup"><span data-stu-id="e97e6-135">Use this tool if you need symbols and modules to debug a dump file captured on a different machine.</span></span>

### <a name="dotnet-sos"></a><span data-ttu-id="e97e6-136">dotnet-sos</span><span class="sxs-lookup"><span data-stu-id="e97e6-136">dotnet-sos</span></span>

<span data-ttu-id="e97e6-137">[dotnet-sos](dotnet-sos.md) służy do instalowania [rozszerzenia debugowania SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) w systemie Linux lub MacOS (lub w systemie Windows, jeśli są używane starsze narzędzia debugowania).</span><span class="sxs-lookup"><span data-stu-id="e97e6-137">[dotnet-sos](dotnet-sos.md) is used to install the [SOS debugging extension](../../framework/tools/sos-dll-sos-debugging-extension.md) on Linux or MacOS (or on Windows if using older debugging tools).</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="e97e6-138">Samouczki dotyczące diagnostyki platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="e97e6-138">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="e97e6-139">Debugowanie przecieku pamięci</span><span class="sxs-lookup"><span data-stu-id="e97e6-139">Debug a memory leak</span></span>

<span data-ttu-id="e97e6-140">[Samouczek: debugowanie przecieku pamięci](debug-memory-leak.md) przeprowadzi przez znalezienie przecieku pamięci.</span><span class="sxs-lookup"><span data-stu-id="e97e6-140">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="e97e6-141">Narzędzie [dotnet-Counters](dotnet-counters.md) służy do potwierdzenia przecieku i narzędzia [dotnet-dump](dotnet-dump.md) służy do diagnozowania wycieku.</span><span class="sxs-lookup"><span data-stu-id="e97e6-141">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>

### <a name="debug-high-cpu-usage"></a><span data-ttu-id="e97e6-142">Debugowanie wysokiego użycia procesora</span><span class="sxs-lookup"><span data-stu-id="e97e6-142">Debug high CPU usage</span></span>

<span data-ttu-id="e97e6-143">[Samouczek: debugowanie dużego użycia procesora CPU](debug-highcpu.md) przeprowadzi Cię przez badanie wysokiego użycia procesora CPU.</span><span class="sxs-lookup"><span data-stu-id="e97e6-143">[Tutorial: Debug high CPU usage](debug-highcpu.md) walks you through investigating high CPU usage.</span></span> <span data-ttu-id="e97e6-144">Za pomocą narzędzia [dotnet-Counters](dotnet-counters.md) można potwierdzić duże użycie procesora CPU.</span><span class="sxs-lookup"><span data-stu-id="e97e6-144">It uses the [dotnet-counters](dotnet-counters.md) tool to confirm the high CPU usage.</span></span> <span data-ttu-id="e97e6-145">Następnie przeprowadzi Cię przez proces [śledzenia narzędzia do analizy wydajności ( `dotnet-trace` )](dotnet-trace.md) lub systemu Linux `perf` w celu zbierania i wyświetlania profilu użycia procesora CPU.</span><span class="sxs-lookup"><span data-stu-id="e97e6-145">It then walks you through using [Trace for performance analysis utility (`dotnet-trace`)](dotnet-trace.md) or Linux `perf` to collect and view CPU usage profile.</span></span>

### <a name="debug-deadlock"></a><span data-ttu-id="e97e6-146">Debugowanie zakleszczenia</span><span class="sxs-lookup"><span data-stu-id="e97e6-146">Debug deadlock</span></span>

<span data-ttu-id="e97e6-147">[Samouczek: zakleszczenie debugowania](debug-deadlock.md) pokazuje, w jaki sposób używać narzędzia [dotnet-dump](dotnet-dump.md) do badania wątków i blokad.</span><span class="sxs-lookup"><span data-stu-id="e97e6-147">[Tutorial: Debug deadlock](debug-deadlock.md) shows you how to use the [dotnet-dump](dotnet-dump.md) tool to investigate threads and locks.</span></span>
