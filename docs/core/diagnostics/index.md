---
title: Omówienie narzędzi diagnostycznych — .NET Core
description: Przegląd narzędzi i technik dostępnych do diagnozowania aplikacji .NET Core.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: ae3b9a1961f331c9cdea786bd5fe06b7bfa10927
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558117"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="fdc3f-103">Jakie narzędzia diagnostyczne są dostępne w środowisku .NET Core?</span><span class="sxs-lookup"><span data-stu-id="fdc3f-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="fdc3f-104">Oprogramowanie nie zawsze zachowuje się w oczekiwany sposób, ale .NET Core ma narzędzia i interfejsy API, które ułatwią zdiagnozowanie tych problemów szybko i efektywnie.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="fdc3f-105">Ten artykuł ułatwia znalezienie różnych potrzebnych narzędzi.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="fdc3f-106">Debugery zarządzane</span><span class="sxs-lookup"><span data-stu-id="fdc3f-106">Managed debuggers</span></span>

<span data-ttu-id="fdc3f-107">[Zarządzane debugery](managed-debuggers.md) umożliwiają korzystanie z programu.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="fdc3f-108">Wstrzymywanie, przyrostowe wykonywanie, badanie i wznawianie zawiera szczegółowe informacje o zachowaniu kodu.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="fdc3f-109">Debuger to pierwszy wybór służący do diagnozowania problemów funkcjonalnych, które można łatwo odtworzyć.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="fdc3f-110">Rejestrowanie i śledzenie</span><span class="sxs-lookup"><span data-stu-id="fdc3f-110">Logging and tracing</span></span>

<span data-ttu-id="fdc3f-111">[Rejestrowanie i śledzenie](logging-tracing.md) to powiązane techniki.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="fdc3f-112">Odnoszą się one do kodu instrumentacji do tworzenia plików dziennika.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="fdc3f-113">Pliki rejestrują szczegóły działania programu.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-113">The files record the details of what a program does.</span></span> <span data-ttu-id="fdc3f-114">Te szczegółowe informacje mogą służyć do diagnozowania najbardziej złożonych problemów.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="fdc3f-115">W połączeniu z sygnaturami czasowymi te techniki są również przydatne w badaniach wydajności.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="fdc3f-116">Testowanie jednostek</span><span class="sxs-lookup"><span data-stu-id="fdc3f-116">Unit testing</span></span>

<span data-ttu-id="fdc3f-117">[Testowanie jednostkowe](../testing/index.md) to kluczowy składnik ciągłej integracji i wdrażania wysokiej jakości oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="fdc3f-118">Testy jednostkowe zostały zaprojektowane w celu zapewnienia wczesnego ostrzegania w przypadku wystąpienia elementu.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="net-core-dotnet-diagnostic-global-tools"></a><span data-ttu-id="fdc3f-119">Narzędzia diagnostyczne programu .NET Core dotnet Diagnostic</span><span class="sxs-lookup"><span data-stu-id="fdc3f-119">.NET Core dotnet diagnostic Global Tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="fdc3f-120">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="fdc3f-120">dotnet-counters</span></span>

<span data-ttu-id="fdc3f-121">[dotnet-Counters](dotnet-counters.md) to narzędzie do monitorowania wydajności służące do monitorowania kondycji pierwszego poziomu i badania wydajności.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-121">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="fdc3f-122">Obserwuje wartości liczników wydajności publikowane za pośrednictwem <xref:System.Diagnostics.Tracing.EventCounter> interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-122">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="fdc3f-123">Można na przykład szybko monitorować elementy, takie jak użycie procesora CPU, lub częstotliwość zgłaszania wyjątków w aplikacji .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="fdc3f-124">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="fdc3f-124">dotnet-dump</span></span>

<span data-ttu-id="fdc3f-125">Narzędzie [dotnet-dump](dotnet-dump.md) to sposób zbierania i analizowania zrzutów podstawowych systemów Windows i Linux bez natywnego debugera.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-125">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-gcdump"></a><span data-ttu-id="fdc3f-126">dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="fdc3f-126">dotnet-gcdump</span></span>

<span data-ttu-id="fdc3f-127">Narzędzie [dotnet-gcdump](dotnet-gcdump.md) to sposób zbierania zrzutów pamięci podręcznej (Moduł wyrzucania elementów bezużytecznych) na żywo procesów platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-127">The [dotnet-gcdump](dotnet-gcdump.md) tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="fdc3f-128">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="fdc3f-128">dotnet-trace</span></span>

<span data-ttu-id="fdc3f-129">Program .NET Core zawiera informacje o tym, w jaki sposób są `EventPipe` udostępniane dane diagnostyczne.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-129">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="fdc3f-130">Narzędzie do [śledzenia dotnet](dotnet-trace.md) umożliwia korzystanie z interesujących danych profilowania z poziomu aplikacji, które mogą pomóc w scenariuszach, w których konieczne jest powolne działanie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-130">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="fdc3f-131">Samouczki dotyczące diagnostyki platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="fdc3f-131">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="fdc3f-132">Debugowanie przecieku pamięci</span><span class="sxs-lookup"><span data-stu-id="fdc3f-132">Debug a memory leak</span></span>

<span data-ttu-id="fdc3f-133">[Samouczek: debugowanie przecieku pamięci](debug-memory-leak.md) przeprowadzi przez znalezienie przecieku pamięci.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-133">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="fdc3f-134">Narzędzie [dotnet-Counters](dotnet-counters.md) służy do potwierdzenia przecieku i narzędzia [dotnet-dump](dotnet-dump.md) służy do diagnozowania wycieku.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-134">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>

### <a name="debug-high-cpu-usage"></a><span data-ttu-id="fdc3f-135">Debugowanie wysokiego użycia procesora</span><span class="sxs-lookup"><span data-stu-id="fdc3f-135">Debug high CPU usage</span></span>

<span data-ttu-id="fdc3f-136">[Samouczek: debugowanie dużego użycia procesora CPU](debug-highcpu.md) przeprowadzi Cię przez badanie wysokiego użycia procesora CPU.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-136">[Tutorial: Debug high CPU usage](debug-highcpu.md) walks you through investigating high CPU usage.</span></span> <span data-ttu-id="fdc3f-137">Za pomocą narzędzia [dotnet-Counters](dotnet-counters.md) można potwierdzić duże użycie procesora CPU.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-137">It uses the [dotnet-counters](dotnet-counters.md) tool to confirm the high CPU usage.</span></span> <span data-ttu-id="fdc3f-138">Następnie przeprowadzi Cię przez proces [śledzenia narzędzia do analizy wydajności ( `dotnet-trace` )](dotnet-trace.md) lub systemu Linux `perf` w celu zbierania i wyświetlania profilu użycia procesora CPU.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-138">It then walks you through using [Trace for performance analysis utility (`dotnet-trace`)](dotnet-trace.md) or Linux `perf` to collect and view CPU usage profile.</span></span>

### <a name="debug-deadlock"></a><span data-ttu-id="fdc3f-139">Debugowanie zakleszczenia</span><span class="sxs-lookup"><span data-stu-id="fdc3f-139">Debug deadlock</span></span>

<span data-ttu-id="fdc3f-140">[Samouczek: zakleszczenie debugowania](debug-deadlock.md) pokazuje, w jaki sposób używać narzędzia [dotnet-dump](dotnet-dump.md) do badania wątków i blokad.</span><span class="sxs-lookup"><span data-stu-id="fdc3f-140">[Tutorial: Debug deadlock](debug-deadlock.md) shows you how to use the [dotnet-dump](dotnet-dump.md) tool to investigate threads and locks.</span></span>
