---
title: Debuguj zrzuty systemu Linux
description: W tym artykule dowiesz się, jak zbierać i analizować zrzuty ze środowisk systemu Linux.
ms.date: 08/27/2020
ms.openlocfilehash: d62295e165f56e32ef73ab628ca9ebd77a4435d1
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598356"
---
# <a name="debug-linux-dumps"></a><span data-ttu-id="320a0-103">Debuguj zrzuty systemu Linux</span><span class="sxs-lookup"><span data-stu-id="320a0-103">Debug Linux dumps</span></span>

<span data-ttu-id="320a0-104">**Ten artykuł ma zastosowanie do: ✔️** .net Core 3,0 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="320a0-104">**This article applies to: ✔️** .NET Core 3.0 SDK and later versions</span></span>

## <a name="collect-dumps-on-linux"></a><span data-ttu-id="320a0-105">Zbieraj zrzuty w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="320a0-105">Collect dumps on Linux</span></span>

<span data-ttu-id="320a0-106">Dwa zalecane sposoby zbierania zrzutów w systemie Linux to [`dotnet-dump`](dotnet-dump.md) [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) Narzędzia lub.</span><span class="sxs-lookup"><span data-stu-id="320a0-106">The two recommended ways of collecting dumps on Linux are the [`dotnet-dump`](dotnet-dump.md) or [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) tools.</span></span>

### <a name="managed-dumps-with-dotnet-dump"></a><span data-ttu-id="320a0-107">Zarządzane zrzuty z `dotnet-dump`</span><span class="sxs-lookup"><span data-stu-id="320a0-107">Managed dumps with `dotnet-dump`</span></span>

<span data-ttu-id="320a0-108">[`dotnet-dump`](dotnet-dump.md)Narzędzie jest proste w użyciu i nie jest zależne od żadnych natywnych debugerów.</span><span class="sxs-lookup"><span data-stu-id="320a0-108">The [`dotnet-dump`](dotnet-dump.md) tool is simple to use, and does not have a dependency on any native debuggers.</span></span> <span data-ttu-id="320a0-109">`dotnet-dump` działa na wielu platformach systemu Linux (takich jak Alpine lub ARM32/ARM64), gdzie tradycyjne narzędzia debugowania mogą być niedostępne.</span><span class="sxs-lookup"><span data-stu-id="320a0-109">`dotnet-dump` works on a wide variety of Linux platforms (like Alpine or ARM32/ARM64) where traditional debugging tools may not be available.</span></span> <span data-ttu-id="320a0-110">Jednak `dotnet-dump` tylko przechwytuje stan zarządzany, dlatego nie można go używać do debugowania w kodzie natywnym.</span><span class="sxs-lookup"><span data-stu-id="320a0-110">However, `dotnet-dump` only captures managed state so it can't be used for debugging issues in native code.</span></span> <span data-ttu-id="320a0-111">Zrzuty zbierane przez program `dotnet-dump` są analizowane w środowisku z tym samym systemem operacyjnym i architekturą, w której został utworzony zrzut.</span><span class="sxs-lookup"><span data-stu-id="320a0-111">Dumps collected by `dotnet-dump` are analyzed in an environment with the the same OS and architecture the dump was created on.</span></span> <span data-ttu-id="320a0-112">[`dotnet-gcdump`](dotnet-gcdump.md)Narzędzie może służyć jako alternatywa, która przechwytuje informacje o stercie GC, ale tworzy zrzuty, które można analizować w systemie Windows.</span><span class="sxs-lookup"><span data-stu-id="320a0-112">The [`dotnet-gcdump`](dotnet-gcdump.md) tool can be used as an alternative that only captures GC heap information but produces dumps that can be analyzed on Windows.</span></span>

### <a name="core-dumps-with-createdump"></a><span data-ttu-id="320a0-113">Zrzuty rdzeniowe z `createdump`</span><span class="sxs-lookup"><span data-stu-id="320a0-113">Core dumps with `createdump`</span></span>

<span data-ttu-id="320a0-114">Alternatywnym rozwiązaniem `dotnet-dump` jest utworzenie zrzutów, które [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) są przeznaczone tylko do zarządzania, jest zalecanym narzędziem do tworzenia podstawowych zrzutów w systemie Linux zawierających zarówno dane natywne, jak i zarządzane.</span><span class="sxs-lookup"><span data-stu-id="320a0-114">Alternative to `dotnet-dump` which creates managed-only dumps, [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) is the recommended tool for creating core dumps on Linux containing both native and managed information.</span></span> <span data-ttu-id="320a0-115">Można również użyć innych narzędzi, takich jak GDB lub gcore, w celu utworzenia zrzutów podstawowych, ale może brakować stanu wymaganego do debugowania zarządzanego, co powoduje "Nieznane" nazwy typu lub funkcji podczas analizy.</span><span class="sxs-lookup"><span data-stu-id="320a0-115">Other tools like gdb or gcore can also be used to create core dumps but may miss state needed for managed debugging, resulting in "UNKNOWN" type or function names during analysis.</span></span>

<span data-ttu-id="320a0-116">`createdump`Narzędzia są instalowane przy użyciu środowiska uruchomieniowego .NET Core i można je znaleźć obok libcoreclr.so (zazwyczaj w "/usr/share/dotnet/Shared/Microsoft.NETCore.App/[wersja]").</span><span class="sxs-lookup"><span data-stu-id="320a0-116">The `createdump` tools is installed with the .NET Core runtime and can be found next to libcoreclr.so (typically in "/usr/share/dotnet/shared/Microsoft.NETCore.App/[version]").</span></span> <span data-ttu-id="320a0-117">Narzędzie Pobiera identyfikator procesu w celu zebrania zrzutu z jako argumentu podstawowego i może również przyjmować parametry opcjonalne określające rodzaj zrzutu do zebrania (wartość domyślna to minizrzutu z stertą).</span><span class="sxs-lookup"><span data-stu-id="320a0-117">The tool takes a process ID to collect a dump from as its primary argument and can also take optional parameters specifying what kind of dump to collect (a minidump with heap is the default).</span></span> <span data-ttu-id="320a0-118">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="320a0-118">Options include:</span></span>

- **`<input-filename>`**

  <span data-ttu-id="320a0-119">Wejściowy plik śledzenia do przekonwertowania.</span><span class="sxs-lookup"><span data-stu-id="320a0-119">Input trace file to be converted.</span></span> <span data-ttu-id="320a0-120">Wartość domyślna to *Trace. Trace*.</span><span class="sxs-lookup"><span data-stu-id="320a0-120">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="320a0-121">Opcje</span><span class="sxs-lookup"><span data-stu-id="320a0-121">Options</span></span>

- **`-f|--name <output-filename>`**

  <span data-ttu-id="320a0-122">Plik, w którym ma zostać zapisany zrzut.</span><span class="sxs-lookup"><span data-stu-id="320a0-122">The file to write the dump to.</span></span> <span data-ttu-id="320a0-123">Wartość domyślna to "/tmp/CoreDump.%p", gdzie% p jest IDENTYFIKATORem procesu docelowego.</span><span class="sxs-lookup"><span data-stu-id="320a0-123">Default is '/tmp/coredump.%p' where %p is the process ID of the target process.</span></span>

- **`-n|--normal`**

  <span data-ttu-id="320a0-124">Utwórz element minizrzutu.</span><span class="sxs-lookup"><span data-stu-id="320a0-124">Create a minidump.</span></span>

- **`-h|--withheap`**

  <span data-ttu-id="320a0-125">Utwórz element minizrzutu z stertą (domyślnie).</span><span class="sxs-lookup"><span data-stu-id="320a0-125">Create a minidump with heap (default).</span></span>

- **`-t|--triage`**

  <span data-ttu-id="320a0-126">Utwórz element Klasyfikacja minizrzutu.</span><span class="sxs-lookup"><span data-stu-id="320a0-126">Create a triage minidump.</span></span>

- **`-u|--full`**

  <span data-ttu-id="320a0-127">Utwórz pełny zrzut rdzenia.</span><span class="sxs-lookup"><span data-stu-id="320a0-127">Create a full core dump.</span></span>

- **`-d|--diag`**

  <span data-ttu-id="320a0-128">Włącz komunikaty diagnostyczne.</span><span class="sxs-lookup"><span data-stu-id="320a0-128">Enable diagnostic messages.</span></span>

<span data-ttu-id="320a0-129">Należy pamiętać, że zbieranie podstawowych zrzutów wymaga `SYS_PTRACE` możliwości lub `createdump` uruchomienia z sudo lub su.</span><span class="sxs-lookup"><span data-stu-id="320a0-129">Note that collecting core dumps requires either the `SYS_PTRACE` capability or that `createdump` be run with sudo or su.</span></span>

## <a name="analyze-dumps-on-linux"></a><span data-ttu-id="320a0-130">Analizowanie zrzutów w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="320a0-130">Analyze dumps on Linux</span></span>

<span data-ttu-id="320a0-131">Zarówno zarządzane zrzuty zebrane z `dotnet-dump` i rdzenie podstawowe zbierane z programem `createdump` można analizować za pomocą `dotnet-dump` Narzędzia przy użyciu `dotnet-dump analyze` polecenia.</span><span class="sxs-lookup"><span data-stu-id="320a0-131">Both managed dumps collected with `dotnet-dump` and core dumps collected with `createdump` can be analyzed with the `dotnet-dump` tool using the `dotnet-dump analyze` command.</span></span> <span data-ttu-id="320a0-132">`dotnet dump`Wymaga, aby środowisko analizuje zrzut ma ten sam system operacyjny i architekturę co środowisko, w którym został przechwycony zrzut.</span><span class="sxs-lookup"><span data-stu-id="320a0-132">The `dotnet dump` requires that the environment analyzing the dump has the same OS and architecture as the environment the dump was captured in.</span></span>

<span data-ttu-id="320a0-133">Alternatywnie, [LLDB](https://lldb.llvm.org/) może służyć do analizowania zrzutów rdzeni w systemie Linux, co umożliwia analizę zarówno ramek zarządzanych, jak i natywnych.</span><span class="sxs-lookup"><span data-stu-id="320a0-133">Alternatively, [LLDB](https://lldb.llvm.org/) can be used to analyze core dumps on Linux, which allows analysis of both managed and native frames.</span></span> <span data-ttu-id="320a0-134">LLDB używa rozszerzenia SOS do debugowania kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="320a0-134">LLDB uses the SOS extension to debug managed code.</span></span> <span data-ttu-id="320a0-135">[`dotnet-sos`](dotnet-sos.md)Narzędzia interfejsu wiersza polecenia można użyć do instalacji sos, która zawiera [wiele przydatnych poleceń](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) debugowania kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="320a0-135">The [`dotnet-sos`](dotnet-sos.md) CLI tool can be used to install SOS which has [many useful commands](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) for debugging managed code.</span></span> <span data-ttu-id="320a0-136">W celu przeanalizowania zrzutów programu .NET Core LLDB i SOS wymagają następujących plików binarnych platformy .NET Core ze środowiska, w którym został utworzony zrzut:</span><span class="sxs-lookup"><span data-stu-id="320a0-136">In order to analyze .NET Core dumps, LLDB and SOS require the following .NET Core binaries from the environment the dump was created in:</span></span>

1. <span data-ttu-id="320a0-137">libmscordaccore.so</span><span class="sxs-lookup"><span data-stu-id="320a0-137">libmscordaccore.so</span></span>
2. <span data-ttu-id="320a0-138">libcoreclr.so</span><span class="sxs-lookup"><span data-stu-id="320a0-138">libcoreclr.so</span></span>
3. <span data-ttu-id="320a0-139">dotnet (host używany do uruchamiania aplikacji)</span><span class="sxs-lookup"><span data-stu-id="320a0-139">dotnet (the host used to launch the app)</span></span>

<span data-ttu-id="320a0-140">W większości przypadków te pliki binarne można pobrać przy użyciu [`dotnet-symbol`](dotnet-symbol.md) Narzędzia.</span><span class="sxs-lookup"><span data-stu-id="320a0-140">In most cases, these binaries can be downloaded using the [`dotnet-symbol`](dotnet-symbol.md) tool.</span></span> <span data-ttu-id="320a0-141">Jeśli nie można pobrać niezbędnych plików binarnych z `dotnet-symbol` (na przykład jeśli prywatna wersja platformy .NET Core oparta na źródle była w użyciu), może być konieczne skopiowanie plików wymienionych powyżej ze środowiska, w którym został utworzony.</span><span class="sxs-lookup"><span data-stu-id="320a0-141">If the necessary binaries can't be downloaded with `dotnet-symbol` (for example, if a private version of .NET Core built from source was in use), it may be necessary to copy the files listed above from the environment the dump was created in.</span></span> <span data-ttu-id="320a0-142">Jeśli pliki nie znajdują się obok pliku zrzutu, można użyć polecenia LLDB/SOS, `setclrpath <path>` Aby ustawić ścieżkę, z której mają zostać załadowane, i `setsymbolserver -directory <path>` ustawić ścieżkę do wyszukiwania dla plików symboli.</span><span class="sxs-lookup"><span data-stu-id="320a0-142">If the files aren't located next to the dump file, you can use the LLDB/SOS command `setclrpath <path>` to set the path they should be loaded from and `setsymbolserver -directory <path>` to set the path to look in for symbol files.</span></span>

<span data-ttu-id="320a0-143">Gdy wymagane pliki są dostępne, zrzut może zostać załadowany w LLDB, określając hosta dotnet jako plik wykonywalny do debugowania:</span><span class="sxs-lookup"><span data-stu-id="320a0-143">Once the necessary files are available, the dump can be loaded in LLDB by specifying the dotnet host as the executable to debug:</span></span>

```console
lldb --core <dump-file> <host-program>
```

<span data-ttu-id="320a0-144">W powyższym wierszu polecenia `<dump-file>` jest ścieżką do analizy zrzutu i `<host-program>` jest programem macierzystym, który uruchomił aplikację .NET Core.</span><span class="sxs-lookup"><span data-stu-id="320a0-144">In the above command line, `<dump-file>` is the path of the dump to analyze and `<host-program>` is the native program that started the .NET Core application.</span></span> <span data-ttu-id="320a0-145">Jest to zazwyczaj `dotnet` plik binarny, chyba że aplikacja jest niezależna. w takim przypadku jest to nazwa aplikacji bez rozszerzenia biblioteki DLL.</span><span class="sxs-lookup"><span data-stu-id="320a0-145">This is typically the `dotnet` binary unless the app is self-contained, in which case it is the name of the application without the dll extension.</span></span>

<span data-ttu-id="320a0-146">Po rozpoczęciu LLDB może być konieczne użycie polecenia, `setsymbolserver` Aby wskazać prawidłową lokalizację symboli ( `setsymbolserver -ms` do użycia serwera symboli firmy Microsoft lub `setsymbolserver -directory <path>` określić ścieżkę lokalną).</span><span class="sxs-lookup"><span data-stu-id="320a0-146">Once LLDB starts, it may be necessary to use the `setsymbolserver` command to point at the correct symbol location (`setsymbolserver -ms` to use Microsoft's symbol server or `setsymbolserver -directory <path>` to specify a local path).</span></span> <span data-ttu-id="320a0-147">Symbole natywne mogą być ładowane przez uruchomienie `loadsymbols` .</span><span class="sxs-lookup"><span data-stu-id="320a0-147">Native symbols can be loaded by running `loadsymbols`.</span></span> <span data-ttu-id="320a0-148">W tym momencie [polecenia sos](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) mogą służyć do analizowania zrzutu.</span><span class="sxs-lookup"><span data-stu-id="320a0-148">At this point, [SOS commands](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) can be used to analyze the dump.</span></span>

## <a name="see-also"></a><span data-ttu-id="320a0-149">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="320a0-149">See also</span></span>

- <span data-ttu-id="320a0-150">[dotnet-sos](dotnet-sos.md) , aby uzyskać więcej informacji na temat instalowania rozszerzenia sos.</span><span class="sxs-lookup"><span data-stu-id="320a0-150">[dotnet-sos](dotnet-sos.md) for more details on installing the SOS extension.</span></span>
- <span data-ttu-id="320a0-151">Program [dotnet — symbol](dotnet-symbol.md) , aby uzyskać więcej informacji na temat instalowania i używania narzędzia do pobierania symboli.</span><span class="sxs-lookup"><span data-stu-id="320a0-151">[dotnet-symbol](dotnet-symbol.md) for more details on installing and using the symbol download tool.</span></span>
- <span data-ttu-id="320a0-152">[Repozytorium diagnostyki .NET Core](https://github.com/dotnet/diagnostics/blob/master/documentation/) , aby uzyskać więcej informacji na temat debugowania, w tym przydatnych często zadawanych pytań.</span><span class="sxs-lookup"><span data-stu-id="320a0-152">[.NET Core diagnostics repo](https://github.com/dotnet/diagnostics/blob/master/documentation/) for more details on debugging, including a useful FAQ.</span></span>
- <span data-ttu-id="320a0-153">[Instalowanie programu LLDB](https://github.com/dotnet/diagnostics/blob/master/documentation/sos.md#getting-lldb) w celu uzyskania instrukcji dotyczących instalowania LLDB w systemie Linux lub Mac.</span><span class="sxs-lookup"><span data-stu-id="320a0-153">[Installing LLDB](https://github.com/dotnet/diagnostics/blob/master/documentation/sos.md#getting-lldb) for instructions on installing LLDB on Linux or Mac.</span></span>
