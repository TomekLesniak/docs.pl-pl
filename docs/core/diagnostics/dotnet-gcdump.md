---
title: dotnet-gcdump-.NET Core
description: Instalowanie i używanie narzędzia wiersza polecenia dotnet-gcdump.
ms.date: 07/26/2020
ms.openlocfilehash: a7b19f4d7487677b975621e7267a17894dae2e3a
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656654"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a><span data-ttu-id="ed06e-103">Narzędzie do analizy sterty (dotnet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="ed06e-103">Heap analysis tool (dotnet-gcdump)</span></span>

<span data-ttu-id="ed06e-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 3,1 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="ed06e-104">**This article applies to:** ✔️ .NET Core 3.1 SDK and later versions</span></span>

## <a name="install-dotnet-gcdump"></a><span data-ttu-id="ed06e-105">Zainstaluj dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="ed06e-105">Install dotnet-gcdump</span></span>

<span data-ttu-id="ed06e-106">Aby zainstalować najnowszą wersję `dotnet-gcdump` [pakietu NuGet](https://www.nuget.org/packages/dotnet-gcdump), użyj polecenia [Narzędzia dotnet Install](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="ed06e-106">To install the latest release version of the `dotnet-gcdump` [NuGet package](https://www.nuget.org/packages/dotnet-gcdump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-gcdump
```

## <a name="synopsis"></a><span data-ttu-id="ed06e-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="ed06e-107">Synopsis</span></span>

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="ed06e-108">Opis</span><span class="sxs-lookup"><span data-stu-id="ed06e-108">Description</span></span>

<span data-ttu-id="ed06e-109">`dotnet-gcdump`Globalnym narzędziem jest sposób zbierania zrzutów GC (Moduł wyrzucania elementów bezużytecznych) procesów .NET na żywo.</span><span class="sxs-lookup"><span data-stu-id="ed06e-109">The `dotnet-gcdump` global tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span> <span data-ttu-id="ed06e-110">Używa technologii EventPipe, która jest wieloplatformową alternatywą dla funkcji ETW w systemie Windows.</span><span class="sxs-lookup"><span data-stu-id="ed06e-110">It uses the EventPipe technology, which is a cross-platform alternative to ETW on Windows.</span></span> <span data-ttu-id="ed06e-111">Zrzuty GC są tworzone przez wyzwolenie GC w procesie docelowym, włączenie zdarzeń specjalnych i ponowne wygenerowanie grafu obiektów głównych obiektu ze strumienia zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="ed06e-111">GC dumps are created by triggering a GC in the target process, turning on special events, and regenerating the graph of object roots from the event stream.</span></span> <span data-ttu-id="ed06e-112">Ten proces umożliwia zbieranie zrzutów GC, gdy proces jest uruchomiony i z minimalnymi kosztami.</span><span class="sxs-lookup"><span data-stu-id="ed06e-112">This process allows for GC dumps to be collected while the process is running and with minimal overhead.</span></span> <span data-ttu-id="ed06e-113">Te zrzuty są przydatne w kilku scenariuszach:</span><span class="sxs-lookup"><span data-stu-id="ed06e-113">These dumps are useful for several scenarios:</span></span>

- <span data-ttu-id="ed06e-114">Porównanie liczby obiektów w stercie w kilku punktach w czasie.</span><span class="sxs-lookup"><span data-stu-id="ed06e-114">Comparing the number of objects on the heap at several points in time.</span></span>
- <span data-ttu-id="ed06e-115">Analizowanie katalogów głównych obiektów (odpowiedzi na pytania, takie jak nadal ma odwołanie do tego typu?).</span><span class="sxs-lookup"><span data-stu-id="ed06e-115">Analyzing roots of objects (answering questions like, "what still has a reference to this type?").</span></span>
- <span data-ttu-id="ed06e-116">Zbieranie ogólnych statystyk o liczbie obiektów na stercie.</span><span class="sxs-lookup"><span data-stu-id="ed06e-116">Collecting general statistics about the counts of objects on the heap.</span></span>

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a><span data-ttu-id="ed06e-117">Wyświetlanie zrzutu pamięci podręcznej przechwycone z programu dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="ed06e-117">View the GC dump captured from dotnet-gcdump</span></span>

<span data-ttu-id="ed06e-118">W systemie Windows `.gcdump` pliki można wyświetlać w [Narzędzia PerfView](https://github.com/microsoft/perfview) na potrzeby analizy lub w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ed06e-118">On Windows, `.gcdump` files can be viewed in [PerfView](https://github.com/microsoft/perfview) for analysis or in Visual Studio.</span></span> <span data-ttu-id="ed06e-119">Obecnie nie ma możliwości otwierania `.gcdump` na platformach innych niż Windows.</span><span class="sxs-lookup"><span data-stu-id="ed06e-119">Currently, There is no way of opening a `.gcdump` on non-Windows platforms.</span></span>

<span data-ttu-id="ed06e-120">Można zbierać wiele `.gcdump` i otwierać je jednocześnie w programie Visual Studio w celu uzyskania porównania.</span><span class="sxs-lookup"><span data-stu-id="ed06e-120">You can collect multiple `.gcdump`s and open them simultaneously in Visual Studio to get a comparison experience.</span></span>

## <a name="options"></a><span data-ttu-id="ed06e-121">Opcje</span><span class="sxs-lookup"><span data-stu-id="ed06e-121">Options</span></span>

- **`--version`**

  <span data-ttu-id="ed06e-122">Wyświetla wersję `dotnet-gcdump` Narzędzia.</span><span class="sxs-lookup"><span data-stu-id="ed06e-122">Displays the version of the `dotnet-gcdump` utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="ed06e-123">Wyświetla pomoc w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="ed06e-123">Shows command-line help.</span></span>

## `dotnet-gcdump collect`

<span data-ttu-id="ed06e-124">Zbiera zrzut GC z aktualnie uruchomionego procesu.</span><span class="sxs-lookup"><span data-stu-id="ed06e-124">Collects a GC dump from a currently running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="ed06e-125">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="ed06e-125">Synopsis</span></span>

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a><span data-ttu-id="ed06e-126">Opcje</span><span class="sxs-lookup"><span data-stu-id="ed06e-126">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="ed06e-127">Wyświetla pomoc w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="ed06e-127">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="ed06e-128">Identyfikator procesu, z którego ma zostać zebrany zrzut GC.</span><span class="sxs-lookup"><span data-stu-id="ed06e-128">The process ID to collect the GC dump from.</span></span>

- **`-o|--output <gcdump-file-path>`**

  <span data-ttu-id="ed06e-129">Ścieżka, w której powinny być zapisywane zebrane zrzuty GC.</span><span class="sxs-lookup"><span data-stu-id="ed06e-129">The path where collected GC dumps should be written.</span></span> <span data-ttu-id="ed06e-130">Wartość domyślna to *. \\ RRRRMMDD \_ HHMMSS \_ \<pid> . gcdump*.</span><span class="sxs-lookup"><span data-stu-id="ed06e-130">Defaults to *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*.</span></span>

- **`-v|--verbose`**

  <span data-ttu-id="ed06e-131">Wyprowadza dziennik podczas zbierania zrzutu GC.</span><span class="sxs-lookup"><span data-stu-id="ed06e-131">Output the log while collecting the GC dump.</span></span>

- **`-t|--timeout <timeout>`**

  <span data-ttu-id="ed06e-132">Zastanów się nad zbieraniem zrzutu pamięci podręcznej, jeśli trwa dłużej niż wynosi to wiele sekund.</span><span class="sxs-lookup"><span data-stu-id="ed06e-132">Give up on collecting the GC dump if it takes longer than this many seconds.</span></span> <span data-ttu-id="ed06e-133">Wartość domyślna to 30.</span><span class="sxs-lookup"><span data-stu-id="ed06e-133">The default value is 30.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="ed06e-134">Nazwa procesu, z którego ma zostać zebrany zrzut GC.</span><span class="sxs-lookup"><span data-stu-id="ed06e-134">The name of the process to collect the GC dump from.</span></span>

## `dotnet-gcdump ps`

<span data-ttu-id="ed06e-135">Wyświetla listę procesów dotnet, dla których można zbierać zrzuty GC.</span><span class="sxs-lookup"><span data-stu-id="ed06e-135">Lists the dotnet processes that GC dumps can be collected for.</span></span>

### <a name="synopsis"></a><span data-ttu-id="ed06e-136">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="ed06e-136">Synopsis</span></span>

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

<span data-ttu-id="ed06e-137">Wygeneruj Raport z wcześniej wygenerowanego zrzutu GC lub z uruchomionego procesu, a następnie wpisz polecenie `stdout` .</span><span class="sxs-lookup"><span data-stu-id="ed06e-137">Generate a report from a previously generated GC dump or from a running process, and write to `stdout`.</span></span>

### <a name="synopsis"></a><span data-ttu-id="ed06e-138">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="ed06e-138">Synopsis</span></span>

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a><span data-ttu-id="ed06e-139">Opcje</span><span class="sxs-lookup"><span data-stu-id="ed06e-139">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="ed06e-140">Wyświetla pomoc w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="ed06e-140">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="ed06e-141">Identyfikator procesu, z którego ma zostać zebrany zrzut GC.</span><span class="sxs-lookup"><span data-stu-id="ed06e-141">The process ID to collect the GC dump from.</span></span>

- **`-t|--report-type <HeapStat>`**

  <span data-ttu-id="ed06e-142">Typ raportu do wygenerowania.</span><span class="sxs-lookup"><span data-stu-id="ed06e-142">The type of report to generate.</span></span> <span data-ttu-id="ed06e-143">Dostępne opcje: heapstat (domyślnie).</span><span class="sxs-lookup"><span data-stu-id="ed06e-143">Available options: heapstat (default).</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="ed06e-144">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="ed06e-144">Troubleshoot</span></span>

- <span data-ttu-id="ed06e-145">Brak informacji o typie w gcdump.</span><span class="sxs-lookup"><span data-stu-id="ed06e-145">There is no type information in the gcdump.</span></span>

   <span data-ttu-id="ed06e-146">Przed platformą .NET Core 3,1 wystąpił problem polegający na tym, że pamięć podręczna typu nie została wyczyszczona między gcdumps, gdy zostały wywołane z EventPipe.</span><span class="sxs-lookup"><span data-stu-id="ed06e-146">Prior to .NET Core 3.1, there was an issue where a type cache was not cleared between gcdumps when they were invoked with EventPipe.</span></span> <span data-ttu-id="ed06e-147">Spowodowało to zdarzenia, które trzeba wykonać, aby określić informacje o typie, które nie są wysyłane dla drugiego i kolejnego gcdumps.</span><span class="sxs-lookup"><span data-stu-id="ed06e-147">This resulted in the events needed for determining type information not being sent for the second and subsequent gcdumps.</span></span> <span data-ttu-id="ed06e-148">Ten problem został rozwiązany w programie .NET Core 3,1-preview2.</span><span class="sxs-lookup"><span data-stu-id="ed06e-148">This was fixed in .NET Core 3.1-preview2.</span></span>

- <span data-ttu-id="ed06e-149">COM i typy statyczne nie znajdują się w zrzucie odzyskiwania pamięci.</span><span class="sxs-lookup"><span data-stu-id="ed06e-149">COM and static types aren't in the GC dump.</span></span>

   <span data-ttu-id="ed06e-150">Przed uruchomieniem programu .NET Core 3,1-preview2 wystąpił problem polegający na tym, że typy statyczne i COM nie zostały wysłane, gdy zrzut GC został wywołany za pośrednictwem EventPipe.</span><span class="sxs-lookup"><span data-stu-id="ed06e-150">Prior to .NET Core 3.1-preview2, there was an issue where static and COM types weren't sent when the GC dump was invoked via EventPipe.</span></span> <span data-ttu-id="ed06e-151">Ten problem został rozwiązany w programie .NET Core 3,1-preview2.</span><span class="sxs-lookup"><span data-stu-id="ed06e-151">This has been fixed in .NET Core 3.1-preview2.</span></span>
