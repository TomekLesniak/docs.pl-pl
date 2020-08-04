---
title: dotnet-Trace Tool-.NET Core
description: Instalowanie i używanie narzędzia wiersza polecenia do śledzenia dotnet.
ms.date: 11/21/2019
ms.openlocfilehash: 25178a0e59ce9edb69d15ee761c1b9e56aa5eb3a
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517311"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="be7d8-103">Narzędzie do analizy wydajności śledzenia dotnet</span><span class="sxs-lookup"><span data-stu-id="be7d8-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="be7d8-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 3,0 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="be7d8-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-trace"></a><span data-ttu-id="be7d8-105">Zainstaluj program dotnet-Trace</span><span class="sxs-lookup"><span data-stu-id="be7d8-105">Install dotnet-trace</span></span>

<span data-ttu-id="be7d8-106">Zainstaluj `dotnet-trace` [pakiet NuGet](https://www.nuget.org/packages/dotnet-trace) za pomocą polecenia [instalacji narzędzia dotnet](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="be7d8-106">Install `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace) with the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a><span data-ttu-id="be7d8-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="be7d8-107">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="be7d8-108">Opis</span><span class="sxs-lookup"><span data-stu-id="be7d8-108">Description</span></span>

<span data-ttu-id="be7d8-109">`dotnet-trace`Narzędzie:</span><span class="sxs-lookup"><span data-stu-id="be7d8-109">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="be7d8-110">Program to międzyplatformowe narzędzie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="be7d8-110">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="be7d8-111">Włącza zbieranie śladów .NET Core działającego procesu bez natywnego profilera.</span><span class="sxs-lookup"><span data-stu-id="be7d8-111">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="be7d8-112">Program jest oparty na technologii międzyplatformowej `EventPipe` środowiska uruchomieniowego platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="be7d8-112">Is built around the cross-platform `EventPipe` technology of the .NET Core runtime.</span></span>
* <span data-ttu-id="be7d8-113">Zapewnia takie samo środowisko w systemach Windows, Linux lub macOS.</span><span class="sxs-lookup"><span data-stu-id="be7d8-113">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="be7d8-114">Opcje</span><span class="sxs-lookup"><span data-stu-id="be7d8-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="be7d8-115">Wyświetla pomoc w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="be7d8-115">Shows command-line help.</span></span>

- **`--version`**

  <span data-ttu-id="be7d8-116">Wyświetla wersję narzędzia do śledzenia dotnet.</span><span class="sxs-lookup"><span data-stu-id="be7d8-116">Displays the version of the dotnet-trace utility.</span></span>

## <a name="commands"></a><span data-ttu-id="be7d8-117">Polecenia</span><span class="sxs-lookup"><span data-stu-id="be7d8-117">Commands</span></span>

| <span data-ttu-id="be7d8-118">Polecenie</span><span class="sxs-lookup"><span data-stu-id="be7d8-118">Command</span></span>                                                   |
|-----------------------------------------------------------|
| [<span data-ttu-id="be7d8-119">zbieranie danych śledzenia dotnet</span><span class="sxs-lookup"><span data-stu-id="be7d8-119">dotnet-trace collect</span></span>](#dotnet-trace-collect)             |
| [<span data-ttu-id="be7d8-120">Konwersja dotnet-Trace</span><span class="sxs-lookup"><span data-stu-id="be7d8-120">dotnet-trace convert</span></span>](#dotnet-trace-convert)             |
| [<span data-ttu-id="be7d8-121">dotnet-Trace — śledzenie</span><span class="sxs-lookup"><span data-stu-id="be7d8-121">dotnet-trace ps</span></span>](#dotnet-trace-ps)                       |
| [<span data-ttu-id="be7d8-122">dotnet-lista śledzenia — profile</span><span class="sxs-lookup"><span data-stu-id="be7d8-122">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="be7d8-123">zbieranie danych śledzenia dotnet</span><span class="sxs-lookup"><span data-stu-id="be7d8-123">dotnet-trace collect</span></span>

<span data-ttu-id="be7d8-124">Zbiera dane śledzenia diagnostycznego z uruchomionego procesu.</span><span class="sxs-lookup"><span data-stu-id="be7d8-124">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="be7d8-125">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="be7d8-125">Synopsis</span></span>

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>]  [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
```

### <a name="options"></a><span data-ttu-id="be7d8-126">Opcje</span><span class="sxs-lookup"><span data-stu-id="be7d8-126">Options</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="be7d8-127">Ustawia rozmiar buforu cyklicznego w pamięci (w megabajtach).</span><span class="sxs-lookup"><span data-stu-id="be7d8-127">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="be7d8-128">Wartość domyślna to 256 MB.</span><span class="sxs-lookup"><span data-stu-id="be7d8-128">Default 256 MB.</span></span>

- **`--clreventlevel <clreventlevel>`**

  <span data-ttu-id="be7d8-129">Poziom szczegółowości zdarzeń CLR do wyemitowania.</span><span class="sxs-lookup"><span data-stu-id="be7d8-129">Verbosity of CLR events to be emitted.</span></span>

- **`--clrevents <clrevents>`**

  <span data-ttu-id="be7d8-130">Lista zdarzeń środowiska uruchomieniowego CLR do emisji.</span><span class="sxs-lookup"><span data-stu-id="be7d8-130">List of CLR runtime events to emit.</span></span>

- **`--format {Chromium|NetTrace|Speedscope}`**

  <span data-ttu-id="be7d8-131">Ustawia format danych wyjściowych dla konwersji pliku śledzenia.</span><span class="sxs-lookup"><span data-stu-id="be7d8-131">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="be7d8-132">Wartość domyślna to `NetTrace`.</span><span class="sxs-lookup"><span data-stu-id="be7d8-132">The default is `NetTrace`.</span></span>

- **`-n, --name <name>`**

  <span data-ttu-id="be7d8-133">Nazwa procesu, z którego ma zostać zebrane śledzenie.</span><span class="sxs-lookup"><span data-stu-id="be7d8-133">The name of the process to collect the trace from.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="be7d8-134">Ścieżka wyjściowa zebranych danych śledzenia.</span><span class="sxs-lookup"><span data-stu-id="be7d8-134">The output path for the collected trace data.</span></span> <span data-ttu-id="be7d8-135">Jeśli nie zostanie określony, jego wartość domyślna to `trace.nettrace` .</span><span class="sxs-lookup"><span data-stu-id="be7d8-135">If not specified, it defaults to `trace.nettrace`.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="be7d8-136">Identyfikator procesu, z którego ma zostać zebrane śledzenie.</span><span class="sxs-lookup"><span data-stu-id="be7d8-136">The process id to collect the trace from.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="be7d8-137">Nazwany wstępnie zdefiniowany zestaw konfiguracji dostawcy, który umożliwia zwięzłe Określanie typowych scenariuszy śledzenia.</span><span class="sxs-lookup"><span data-stu-id="be7d8-137">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span>

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="be7d8-138">Rozdzielana przecinkami lista `EventPipe` dostawców do włączenia.</span><span class="sxs-lookup"><span data-stu-id="be7d8-138">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="be7d8-139">Tacy dostawcy uzupełniają dostawców implikowaną przez `--profile <profile-name>` .</span><span class="sxs-lookup"><span data-stu-id="be7d8-139">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="be7d8-140">W przypadku niespójności określonego dostawcy ta konfiguracja ma pierwszeństwo przed niejawną konfiguracją w profilu.</span><span class="sxs-lookup"><span data-stu-id="be7d8-140">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="be7d8-141">Ta lista dostawców ma postać:</span><span class="sxs-lookup"><span data-stu-id="be7d8-141">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="be7d8-142">`Provider`ma postać: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]` .</span><span class="sxs-lookup"><span data-stu-id="be7d8-142">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="be7d8-143">`KeyValueArgs`ma postać: `[key1=value1][;key2=value2]` .</span><span class="sxs-lookup"><span data-stu-id="be7d8-143">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="be7d8-144">Konwersja dotnet-Trace</span><span class="sxs-lookup"><span data-stu-id="be7d8-144">dotnet-trace convert</span></span>

<span data-ttu-id="be7d8-145">Konwertuje `nettrace` ślady na formaty alternatywne do użycia z alternatywnymi narzędziami do analizy śledzenia.</span><span class="sxs-lookup"><span data-stu-id="be7d8-145">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="be7d8-146">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="be7d8-146">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a><span data-ttu-id="be7d8-147">Argumenty</span><span class="sxs-lookup"><span data-stu-id="be7d8-147">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="be7d8-148">Wejściowy plik śledzenia do przekonwertowania.</span><span class="sxs-lookup"><span data-stu-id="be7d8-148">Input trace file to be converted.</span></span> <span data-ttu-id="be7d8-149">Wartość domyślna to *Trace. Trace*.</span><span class="sxs-lookup"><span data-stu-id="be7d8-149">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="be7d8-150">Opcje</span><span class="sxs-lookup"><span data-stu-id="be7d8-150">Options</span></span>

- **`--format <Chromium|NetTrace|Speedscope>`**

  <span data-ttu-id="be7d8-151">Ustawia format danych wyjściowych dla konwersji pliku śledzenia.</span><span class="sxs-lookup"><span data-stu-id="be7d8-151">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="be7d8-152">Nazwa pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="be7d8-152">Output filename.</span></span> <span data-ttu-id="be7d8-153">Rozszerzenie formatu docelowego zostanie dodane.</span><span class="sxs-lookup"><span data-stu-id="be7d8-153">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="be7d8-154">dotnet-Trace — śledzenie</span><span class="sxs-lookup"><span data-stu-id="be7d8-154">dotnet-trace ps</span></span>

 <span data-ttu-id="be7d8-155">Wyświetla listę procesów dotnet, z których można zbierać dane śledzenia.</span><span class="sxs-lookup"><span data-stu-id="be7d8-155">Lists the dotnet processes that traces can be collected from.</span></span>

### <a name="synopsis"></a><span data-ttu-id="be7d8-156">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="be7d8-156">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="be7d8-157">dotnet-lista śledzenia — profile</span><span class="sxs-lookup"><span data-stu-id="be7d8-157">dotnet-trace list-profiles</span></span>

<span data-ttu-id="be7d8-158">Wyświetla wstępnie skompilowane profile śledzenia z opisem dostawców i filtrów w poszczególnych profilach.</span><span class="sxs-lookup"><span data-stu-id="be7d8-158">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="be7d8-159">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="be7d8-159">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="be7d8-160">Zbieranie śledzenia przy użyciu funkcji monitorowania dotnet</span><span class="sxs-lookup"><span data-stu-id="be7d8-160">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="be7d8-161">Aby zebrać ślady przy użyciu `dotnet-trace` :</span><span class="sxs-lookup"><span data-stu-id="be7d8-161">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="be7d8-162">Pobierz identyfikator procesu (PID) aplikacji .NET Core, aby zebrać ślady z programu.</span><span class="sxs-lookup"><span data-stu-id="be7d8-162">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="be7d8-163">W systemie Windows można użyć Menedżera zadań lub `tasklist` polecenia, na przykład.</span><span class="sxs-lookup"><span data-stu-id="be7d8-163">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="be7d8-164">Na przykład w systemie Linux `ps` polecenie.</span><span class="sxs-lookup"><span data-stu-id="be7d8-164">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="be7d8-165">dotnet-Trace — śledzenie</span><span class="sxs-lookup"><span data-stu-id="be7d8-165">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="be7d8-166">Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="be7d8-166">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="be7d8-167">Poprzednie polecenie generuje dane wyjściowe podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="be7d8-167">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="be7d8-168">Zatrzymaj zbieranie przez naciśnięcie `<Enter>` klawisza.</span><span class="sxs-lookup"><span data-stu-id="be7d8-168">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="be7d8-169">`dotnet-trace`spowoduje zakończenie rejestrowania zdarzeń w pliku *śledzenia.*</span><span class="sxs-lookup"><span data-stu-id="be7d8-169">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="be7d8-170">Wyświetl śledzenie przechwycone przez śledzenie dotnet</span><span class="sxs-lookup"><span data-stu-id="be7d8-170">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="be7d8-171">W systemie Windows można przeglądać pliki *śledzenia* w usłudze [Narzędzia PerfView](https://github.com/microsoft/perfview) for Analysis: w przypadku śladów zebranych na innych platformach plik śledzenia można przenieść na komputer z systemem Windows, który ma być wyświetlany na narzędzia PerfView.</span><span class="sxs-lookup"><span data-stu-id="be7d8-171">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="be7d8-172">W systemie Linux śledzenie można wyświetlić, zmieniając format danych wyjściowych `dotnet-trace` na `speedscope` .</span><span class="sxs-lookup"><span data-stu-id="be7d8-172">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="be7d8-173">Format pliku wyjściowego można zmienić przy użyciu `-f|--format` opcji — `-f speedscope` spowoduje `dotnet-trace` to utworzenie `speedscope` pliku.</span><span class="sxs-lookup"><span data-stu-id="be7d8-173">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="be7d8-174">Można wybrać opcję `nettrace` (opcja domyślna) i `speedscope` .</span><span class="sxs-lookup"><span data-stu-id="be7d8-174">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="be7d8-175">`Speedscope`Pliki można otwierać w lokalizacji <https://www.speedscope.app> .</span><span class="sxs-lookup"><span data-stu-id="be7d8-175">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="be7d8-176">Środowisko uruchomieniowe programu .NET Core generuje ślady w `nettrace` formacie.</span><span class="sxs-lookup"><span data-stu-id="be7d8-176">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="be7d8-177">Ślady są konwertowane na speedscope (jeśli zostaną określone) po zakończeniu śledzenia.</span><span class="sxs-lookup"><span data-stu-id="be7d8-177">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="be7d8-178">Ponieważ niektóre Konwersje mogą spowodować utratę danych, oryginalny `nettrace` plik zostanie zachowany obok skonwertowanego pliku.</span><span class="sxs-lookup"><span data-stu-id="be7d8-178">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="be7d8-179">Używanie funkcji monitorowania dotnet do zbierania wartości licznika w czasie</span><span class="sxs-lookup"><span data-stu-id="be7d8-179">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="be7d8-180">`dotnet-trace`może</span><span class="sxs-lookup"><span data-stu-id="be7d8-180">`dotnet-trace` can:</span></span>

* <span data-ttu-id="be7d8-181">Służy `EventCounter` do podstawowego monitorowania kondycji w środowiskach z uwzględnieniem wydajności.</span><span class="sxs-lookup"><span data-stu-id="be7d8-181">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="be7d8-182">Na przykład w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="be7d8-182">For example, in production.</span></span>
* <span data-ttu-id="be7d8-183">Zbieraj ślady, aby nie trzeba było ich wyświetlać w czasie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="be7d8-183">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="be7d8-184">Na przykład, aby zbierać wartości liczników wydajności środowiska uruchomieniowego, użyj następującego polecenia:</span><span class="sxs-lookup"><span data-stu-id="be7d8-184">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="be7d8-185">Poprzednie polecenie instruuje liczniki środowiska uruchomieniowego do raportowania co sekundę w przypadku uproszczonego monitorowania kondycji.</span><span class="sxs-lookup"><span data-stu-id="be7d8-185">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="be7d8-186">Zastąpienie `EventCounterIntervalSec=1` o wyższej wartości (na przykład 60) umożliwia zbieranie mniejszych śladów o mniejszej szczegółowości danych licznika.</span><span class="sxs-lookup"><span data-stu-id="be7d8-186">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="be7d8-187">Następujące polecenie zmniejsza obciążenie i rozmiar śladu więcej niż poprzedni:</span><span class="sxs-lookup"><span data-stu-id="be7d8-187">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="be7d8-188">Poprzednie polecenie powoduje wyłączenie zdarzeń środowiska uruchomieniowego i zarządzanego profilera stosu.</span><span class="sxs-lookup"><span data-stu-id="be7d8-188">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="net-providers"></a><span data-ttu-id="be7d8-189">Dostawcy .NET</span><span class="sxs-lookup"><span data-stu-id="be7d8-189">.NET Providers</span></span>

<span data-ttu-id="be7d8-190">Środowisko uruchomieniowe platformy .NET Core obsługuje następujących dostawców platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="be7d8-190">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="be7d8-191">.NET Core używa tych samych słów kluczowych do włączenia obu `Event Tracing for Windows (ETW)` i `EventPipe` śladów.</span><span class="sxs-lookup"><span data-stu-id="be7d8-191">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="be7d8-192">Nazwa dostawcy</span><span class="sxs-lookup"><span data-stu-id="be7d8-192">Provider name</span></span>                            | <span data-ttu-id="be7d8-193">Informacje</span><span class="sxs-lookup"><span data-stu-id="be7d8-193">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="be7d8-194">Dostawca środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="be7d8-194">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="be7d8-195">Słowa kluczowe środowiska uruchomieniowego CLR</span><span class="sxs-lookup"><span data-stu-id="be7d8-195">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="be7d8-196">Dostawca uwalniania</span><span class="sxs-lookup"><span data-stu-id="be7d8-196">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="be7d8-197">Słowa kluczowe uwalniania CLR</span><span class="sxs-lookup"><span data-stu-id="be7d8-197">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="be7d8-198">Włącza przykładowy Profiler.</span><span class="sxs-lookup"><span data-stu-id="be7d8-198">Enables the sample profiler.</span></span> |
