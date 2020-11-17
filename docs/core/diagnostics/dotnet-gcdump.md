---
title: dotnet-gcdump-.NET Core
description: Instalowanie i używanie narzędzia wiersza polecenia dotnet-gcdump.
ms.date: 07/26/2020
ms.openlocfilehash: c73afae9ecdfa907e9655634a0ac355cab4ef558
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687619"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a><span data-ttu-id="8e8a2-103">Narzędzie do analizy sterty (dotnet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="8e8a2-103">Heap analysis tool (dotnet-gcdump)</span></span>

<span data-ttu-id="8e8a2-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 3,1 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="8e8a2-104">**This article applies to:** ✔️ .NET Core 3.1 SDK and later versions</span></span>

## <a name="install-dotnet-gcdump"></a><span data-ttu-id="8e8a2-105">Zainstaluj dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="8e8a2-105">Install dotnet-gcdump</span></span>

<span data-ttu-id="8e8a2-106">Aby zainstalować najnowszą wersję `dotnet-gcdump` [pakietu NuGet](https://www.nuget.org/packages/dotnet-gcdump), użyj polecenia [Narzędzia dotnet Install](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="8e8a2-106">To install the latest release version of the `dotnet-gcdump` [NuGet package](https://www.nuget.org/packages/dotnet-gcdump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-gcdump
```

## <a name="synopsis"></a><span data-ttu-id="8e8a2-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="8e8a2-107">Synopsis</span></span>

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="8e8a2-108">Opis</span><span class="sxs-lookup"><span data-stu-id="8e8a2-108">Description</span></span>

<span data-ttu-id="8e8a2-109">`dotnet-gcdump`Narzędzie globalne zbiera zrzuty procesów .NET na żywo (Moduł wyrzucania elementów bezużytecznych) za pomocą [EventPipe](./eventpipe.md).</span><span class="sxs-lookup"><span data-stu-id="8e8a2-109">The `dotnet-gcdump` global tool collects GC (Garbage Collector) dumps of live .NET processes using [EventPipe](./eventpipe.md).</span></span> <span data-ttu-id="8e8a2-110">Zrzuty GC są tworzone przez wyzwolenie GC w procesie docelowym, włączenie zdarzeń specjalnych i ponowne wygenerowanie grafu obiektów głównych obiektu ze strumienia zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-110">GC dumps are created by triggering a GC in the target process, turning on special events, and regenerating the graph of object roots from the event stream.</span></span> <span data-ttu-id="8e8a2-111">Ten proces umożliwia zbieranie zrzutów GC, gdy proces jest uruchomiony i z minimalnymi kosztami.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-111">This process allows for GC dumps to be collected while the process is running and with minimal overhead.</span></span> <span data-ttu-id="8e8a2-112">Te zrzuty są przydatne w kilku scenariuszach:</span><span class="sxs-lookup"><span data-stu-id="8e8a2-112">These dumps are useful for several scenarios:</span></span>

- <span data-ttu-id="8e8a2-113">Porównanie liczby obiektów w stercie w kilku punktach w czasie.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-113">Comparing the number of objects on the heap at several points in time.</span></span>
- <span data-ttu-id="8e8a2-114">Analizowanie katalogów głównych obiektów (odpowiedzi na pytania, takie jak nadal ma odwołanie do tego typu?).</span><span class="sxs-lookup"><span data-stu-id="8e8a2-114">Analyzing roots of objects (answering questions like, "what still has a reference to this type?").</span></span>
- <span data-ttu-id="8e8a2-115">Zbieranie ogólnych statystyk o liczbie obiektów na stercie.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-115">Collecting general statistics about the counts of objects on the heap.</span></span>

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a><span data-ttu-id="8e8a2-116">Wyświetlanie zrzutu pamięci podręcznej przechwycone z programu dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="8e8a2-116">View the GC dump captured from dotnet-gcdump</span></span>

<span data-ttu-id="8e8a2-117">W systemie Windows `.gcdump` pliki można wyświetlać w [Narzędzia PerfView](https://github.com/microsoft/perfview) na potrzeby analizy lub w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-117">On Windows, `.gcdump` files can be viewed in [PerfView](https://github.com/microsoft/perfview) for analysis or in Visual Studio.</span></span> <span data-ttu-id="8e8a2-118">Obecnie nie ma możliwości otwierania `.gcdump` na platformach innych niż Windows.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-118">Currently, There is no way of opening a `.gcdump` on non-Windows platforms.</span></span>

<span data-ttu-id="8e8a2-119">Można zbierać wiele `.gcdump` i otwierać je jednocześnie w programie Visual Studio w celu uzyskania porównania.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-119">You can collect multiple `.gcdump`s and open them simultaneously in Visual Studio to get a comparison experience.</span></span>

## <a name="options"></a><span data-ttu-id="8e8a2-120">Opcje</span><span class="sxs-lookup"><span data-stu-id="8e8a2-120">Options</span></span>

- **`--version`**

  <span data-ttu-id="8e8a2-121">Wyświetla wersję `dotnet-gcdump` Narzędzia.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-121">Displays the version of the `dotnet-gcdump` utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="8e8a2-122">Wyświetla pomoc w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-122">Shows command-line help.</span></span>

## `dotnet-gcdump collect`

<span data-ttu-id="8e8a2-123">Zbiera zrzut GC z aktualnie uruchomionego procesu.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-123">Collects a GC dump from a currently running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="8e8a2-124">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="8e8a2-124">Synopsis</span></span>

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a><span data-ttu-id="8e8a2-125">Opcje</span><span class="sxs-lookup"><span data-stu-id="8e8a2-125">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="8e8a2-126">Wyświetla pomoc w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-126">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="8e8a2-127">Identyfikator procesu, z którego ma zostać zebrany zrzut GC.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-127">The process ID to collect the GC dump from.</span></span>

- **`-o|--output <gcdump-file-path>`**

  <span data-ttu-id="8e8a2-128">Ścieżka, w której powinny być zapisywane zebrane zrzuty GC.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-128">The path where collected GC dumps should be written.</span></span> <span data-ttu-id="8e8a2-129">Wartość domyślna to *. \\ RRRRMMDD \_ HHMMSS \_ \<pid> . gcdump*.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-129">Defaults to *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*.</span></span>

- **`-v|--verbose`**

  <span data-ttu-id="8e8a2-130">Wyprowadza dziennik podczas zbierania zrzutu GC.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-130">Output the log while collecting the GC dump.</span></span>

- **`-t|--timeout <timeout>`**

  <span data-ttu-id="8e8a2-131">Zastanów się nad zbieraniem zrzutu pamięci podręcznej, jeśli trwa dłużej niż wynosi to wiele sekund.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-131">Give up on collecting the GC dump if it takes longer than this many seconds.</span></span> <span data-ttu-id="8e8a2-132">Wartość domyślna to 30.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-132">The default value is 30.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="8e8a2-133">Nazwa procesu, z którego ma zostać zebrany zrzut GC.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-133">The name of the process to collect the GC dump from.</span></span>

## `dotnet-gcdump ps`

<span data-ttu-id="8e8a2-134">Wyświetla listę procesów dotnet, dla których można zbierać zrzuty GC.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-134">Lists the dotnet processes that GC dumps can be collected for.</span></span>

### <a name="synopsis"></a><span data-ttu-id="8e8a2-135">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="8e8a2-135">Synopsis</span></span>

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

<span data-ttu-id="8e8a2-136">Wygeneruj Raport z wcześniej wygenerowanego zrzutu GC lub z uruchomionego procesu, a następnie wpisz polecenie `stdout` .</span><span class="sxs-lookup"><span data-stu-id="8e8a2-136">Generate a report from a previously generated GC dump or from a running process, and write to `stdout`.</span></span>

### <a name="synopsis"></a><span data-ttu-id="8e8a2-137">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="8e8a2-137">Synopsis</span></span>

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a><span data-ttu-id="8e8a2-138">Opcje</span><span class="sxs-lookup"><span data-stu-id="8e8a2-138">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="8e8a2-139">Wyświetla pomoc w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-139">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="8e8a2-140">Identyfikator procesu, z którego ma zostać zebrany zrzut GC.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-140">The process ID to collect the GC dump from.</span></span>

- **`-t|--report-type <HeapStat>`**

  <span data-ttu-id="8e8a2-141">Typ raportu do wygenerowania.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-141">The type of report to generate.</span></span> <span data-ttu-id="8e8a2-142">Dostępne opcje: heapstat (domyślnie).</span><span class="sxs-lookup"><span data-stu-id="8e8a2-142">Available options: heapstat (default).</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="8e8a2-143">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="8e8a2-143">Troubleshoot</span></span>

- <span data-ttu-id="8e8a2-144">Brak informacji o typie w gcdump.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-144">There is no type information in the gcdump.</span></span>

   <span data-ttu-id="8e8a2-145">Przed platformą .NET Core 3,1 wystąpił problem polegający na tym, że pamięć podręczna typu nie została wyczyszczona między gcdumps, gdy zostały wywołane z EventPipe.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-145">Prior to .NET Core 3.1, there was an issue where a type cache was not cleared between gcdumps when they were invoked with EventPipe.</span></span> <span data-ttu-id="8e8a2-146">Spowodowało to zdarzenia, które trzeba wykonać, aby określić informacje o typie, które nie są wysyłane dla drugiego i kolejnego gcdumps.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-146">This resulted in the events needed for determining type information not being sent for the second and subsequent gcdumps.</span></span> <span data-ttu-id="8e8a2-147">Ten problem został rozwiązany w programie .NET Core 3,1-preview2.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-147">This was fixed in .NET Core 3.1-preview2.</span></span>

- <span data-ttu-id="8e8a2-148">COM i typy statyczne nie znajdują się w zrzucie odzyskiwania pamięci.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-148">COM and static types aren't in the GC dump.</span></span>

   <span data-ttu-id="8e8a2-149">Przed uruchomieniem programu .NET Core 3,1-preview2 wystąpił problem polegający na tym, że typy statyczne i COM nie zostały wysłane, gdy zrzut GC został wywołany za pośrednictwem EventPipe.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-149">Prior to .NET Core 3.1-preview2, there was an issue where static and COM types weren't sent when the GC dump was invoked via EventPipe.</span></span> <span data-ttu-id="8e8a2-150">Ten problem został rozwiązany w programie .NET Core 3,1-preview2.</span><span class="sxs-lookup"><span data-stu-id="8e8a2-150">This has been fixed in .NET Core 3.1-preview2.</span></span>
