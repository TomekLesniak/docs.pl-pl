---
title: dotnet-Zrzuć narzędzie diagnostyczne — interfejs wiersza polecenia platformy .NET
description: Informacje o instalowaniu i używaniu narzędzia dotnet-dump interfejsu wiersza polecenia do zbierania i analizowania zrzutów systemu Windows i Linux bez żadnego natywnego debugera.
ms.date: 11/17/2020
ms.openlocfilehash: ea9a70c4dc47b5006339e9a197712092eb66b241
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822207"
---
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a><span data-ttu-id="b1edc-103">Narzędzie do zbierania i analizowania zrzutów (dotnet-dump)</span><span class="sxs-lookup"><span data-stu-id="b1edc-103">Dump collection and analysis utility (dotnet-dump)</span></span>

<span data-ttu-id="b1edc-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 3,0 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="b1edc-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

> [!NOTE]
> <span data-ttu-id="b1edc-105">`dotnet-dump` Program macOS jest obsługiwany tylko z platformą .NET 5,0 i nowszymi wersjami.</span><span class="sxs-lookup"><span data-stu-id="b1edc-105">`dotnet-dump` for macOS is only supported with .NET 5.0 and later versions.</span></span>

## <a name="install"></a><span data-ttu-id="b1edc-106">Instalowanie</span><span class="sxs-lookup"><span data-stu-id="b1edc-106">Install</span></span>

<span data-ttu-id="b1edc-107">Istnieją dwa sposoby na pobranie i zainstalowanie `dotnet-dump` :</span><span class="sxs-lookup"><span data-stu-id="b1edc-107">There are two ways to download and install `dotnet-dump`:</span></span>

- <span data-ttu-id="b1edc-108">**Narzędzie globalne dotnet:**</span><span class="sxs-lookup"><span data-stu-id="b1edc-108">**dotnet global tool:**</span></span>

  <span data-ttu-id="b1edc-109">Aby zainstalować najnowszą wersję `dotnet-dump` [pakietu NuGet](https://www.nuget.org/packages/dotnet-dump), użyj polecenia [Narzędzia dotnet Install](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="b1edc-109">To install the latest release version of the `dotnet-dump` [NuGet package](https://www.nuget.org/packages/dotnet-dump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-dump
  ```

- <span data-ttu-id="b1edc-110">**Pobieranie bezpośrednie:**</span><span class="sxs-lookup"><span data-stu-id="b1edc-110">**Direct download:**</span></span>

  <span data-ttu-id="b1edc-111">Pobierz plik wykonywalny narzędzia, który jest zgodny z platformą:</span><span class="sxs-lookup"><span data-stu-id="b1edc-111">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="b1edc-112">System operacyjny</span><span class="sxs-lookup"><span data-stu-id="b1edc-112">OS</span></span>  | <span data-ttu-id="b1edc-113">Platforma</span><span class="sxs-lookup"><span data-stu-id="b1edc-113">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="b1edc-114">Windows</span><span class="sxs-lookup"><span data-stu-id="b1edc-114">Windows</span></span> | <span data-ttu-id="b1edc-115">[x86](https://aka.ms/dotnet-dump/win-x86) \| [x64](https://aka.ms/dotnet-dump/win-x64) \| [ARM](https://aka.ms/dotnet-dump/win-arm) \| [ARM — x64](https://aka.ms/dotnet-dump/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="b1edc-115">[x86](https://aka.ms/dotnet-dump/win-x86) \| [x64](https://aka.ms/dotnet-dump/win-x64) \| [arm](https://aka.ms/dotnet-dump/win-arm) \| [arm-x64](https://aka.ms/dotnet-dump/win-arm64)</span></span> |
  | <span data-ttu-id="b1edc-116">macOS</span><span class="sxs-lookup"><span data-stu-id="b1edc-116">macOS</span></span>   | [<span data-ttu-id="b1edc-117">x64</span><span class="sxs-lookup"><span data-stu-id="b1edc-117">x64</span></span>](https://aka.ms/dotnet-dump/osx-x64) |
  | <span data-ttu-id="b1edc-118">Linux</span><span class="sxs-lookup"><span data-stu-id="b1edc-118">Linux</span></span>   | <span data-ttu-id="b1edc-119">[x64](https://aka.ms/dotnet-dump/linux-x64) \| [ARM](https://aka.ms/dotnet-dump/linux-arm) \| [arm64](https://aka.ms/dotnet-dump/linux-arm64) \| [MUSL — x64](https://aka.ms/dotnet-dump/linux-musl-x64) \| [MUSL — arm64](https://aka.ms/dotnet-dump/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="b1edc-119">[x64](https://aka.ms/dotnet-dump/linux-x64) \| [arm](https://aka.ms/dotnet-dump/linux-arm) \| [arm64](https://aka.ms/dotnet-dump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-dump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-dump/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="b1edc-120">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="b1edc-120">Synopsis</span></span>

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="b1edc-121">Opis</span><span class="sxs-lookup"><span data-stu-id="b1edc-121">Description</span></span>

<span data-ttu-id="b1edc-122">`dotnet-dump`Globalne Narzędzie to sposób zbierania i analizowania zrzutów systemów Windows i Linux bez żadnego natywnego debugera, który jest taki sam jak `lldb` w systemie Linux.</span><span class="sxs-lookup"><span data-stu-id="b1edc-122">The `dotnet-dump` global tool is a way to collect and analyze Windows and Linux dumps without any native debugger involved like `lldb` on Linux.</span></span> <span data-ttu-id="b1edc-123">To narzędzie jest ważne na platformach, takich jak Alpine Linux, gdy w pełni działa `lldb` nie jest dostępny.</span><span class="sxs-lookup"><span data-stu-id="b1edc-123">This tool is important on platforms like Alpine Linux where a fully working `lldb` isn't available.</span></span> <span data-ttu-id="b1edc-124">`dotnet-dump`Narzędzie pozwala uruchamiać polecenia sos w celu analizowania awarii i modułu wyrzucania elementów bezużytecznych (GC), ale nie jest to debuger natywny, więc nie są obsługiwane elementy, takie jak wyświetlanie natywnych ramek stosu.</span><span class="sxs-lookup"><span data-stu-id="b1edc-124">The `dotnet-dump` tool allows you to run SOS commands to analyze crashes and the garbage collector (GC), but it isn't a native debugger so things like displaying native stack frames aren't supported.</span></span>

## <a name="options"></a><span data-ttu-id="b1edc-125">Opcje</span><span class="sxs-lookup"><span data-stu-id="b1edc-125">Options</span></span>

- **`--version`**

  <span data-ttu-id="b1edc-126">Wyświetla wersję narzędzia dotnet-dump.</span><span class="sxs-lookup"><span data-stu-id="b1edc-126">Displays the version of the dotnet-dump utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="b1edc-127">Wyświetla pomoc w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="b1edc-127">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="b1edc-128">Polecenia</span><span class="sxs-lookup"><span data-stu-id="b1edc-128">Commands</span></span>

| <span data-ttu-id="b1edc-129">Polecenie</span><span class="sxs-lookup"><span data-stu-id="b1edc-129">Command</span></span>                                     |
| ------------------------------------------- |
| [<span data-ttu-id="b1edc-130">Platforma dotnet — Zbieranie zrzutów</span><span class="sxs-lookup"><span data-stu-id="b1edc-130">dotnet-dump collect</span></span>](#dotnet-dump-collect) |
| [<span data-ttu-id="b1edc-131">Analiza zrzutów dotnet</span><span class="sxs-lookup"><span data-stu-id="b1edc-131">dotnet-dump analyze</span></span>](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a><span data-ttu-id="b1edc-132">Platforma dotnet — Zbieranie zrzutów</span><span class="sxs-lookup"><span data-stu-id="b1edc-132">dotnet-dump collect</span></span>

<span data-ttu-id="b1edc-133">Przechwytuje Zrzut z procesu.</span><span class="sxs-lookup"><span data-stu-id="b1edc-133">Captures a dump from a process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="b1edc-134">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="b1edc-134">Synopsis</span></span>

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [-n|--name] [--type] [-o|--output] [--diag]
```

### <a name="options"></a><span data-ttu-id="b1edc-135">Opcje</span><span class="sxs-lookup"><span data-stu-id="b1edc-135">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="b1edc-136">Wyświetla pomoc w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="b1edc-136">Shows command-line help.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="b1edc-137">Określa numer identyfikatora procesu, z którego ma zostać zebrany zrzut.</span><span class="sxs-lookup"><span data-stu-id="b1edc-137">Specifies the process ID number to collect a dump from.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="b1edc-138">Określa nazwę procesu, z którego ma zostać zebrany zrzut.</span><span class="sxs-lookup"><span data-stu-id="b1edc-138">Specifies the name of the process to collect a dump from.</span></span>

- **`--type <Full|Heap|Mini>`**

  <span data-ttu-id="b1edc-139">Określa typ zrzutu, który określa rodzaje informacji zbieranych z procesu.</span><span class="sxs-lookup"><span data-stu-id="b1edc-139">Specifies the dump type, which determines the kinds of information that are collected from the process.</span></span> <span data-ttu-id="b1edc-140">Istnieją trzy typy:</span><span class="sxs-lookup"><span data-stu-id="b1edc-140">There are three types:</span></span>

  - <span data-ttu-id="b1edc-141">`Full` -Największy zrzut zawierający całą pamięć, łącznie z obrazami modułu.</span><span class="sxs-lookup"><span data-stu-id="b1edc-141">`Full` - The largest dump containing all memory including the module images.</span></span>
  - <span data-ttu-id="b1edc-142">`Heap` -Duży i stosunkowo kompleksowy zrzut zawierający listy modułów, listy wątków, wszystkie stosy, informacje o wyjątkach, informacje o obsłudze i wszystkie pamięci z wyjątkiem zamapowanych obrazów.</span><span class="sxs-lookup"><span data-stu-id="b1edc-142">`Heap` - A large and relatively comprehensive dump containing module lists, thread lists, all stacks, exception information, handle information, and all memory except for mapped images.</span></span>
  - <span data-ttu-id="b1edc-143">`Mini` -Mały zrzut zawierający listy modułów, listy wątków, informacje o wyjątku i wszystkie stosy.</span><span class="sxs-lookup"><span data-stu-id="b1edc-143">`Mini` - A small dump containing module lists, thread lists, exception information, and all stacks.</span></span>

  <span data-ttu-id="b1edc-144">Jeśli nie zostanie określony, `Full` jest wartością domyślną.</span><span class="sxs-lookup"><span data-stu-id="b1edc-144">If not specified, `Full` is the default.</span></span>

- **`-o|--output <output_dump_path>`**

  <span data-ttu-id="b1edc-145">Pełna ścieżka i nazwa pliku, w którym ma zostać zapisany zebrany zrzut.</span><span class="sxs-lookup"><span data-stu-id="b1edc-145">The full path and file name where the collected dump should be written.</span></span>

  <span data-ttu-id="b1edc-146">Jeśli nie zostanie określony:</span><span class="sxs-lookup"><span data-stu-id="b1edc-146">If not specified:</span></span>

  - <span data-ttu-id="b1edc-147">Wartość domyślna to *. \ dump_YYYYMMDD_HHMMSS. dmp* w systemie Windows.</span><span class="sxs-lookup"><span data-stu-id="b1edc-147">Defaults to *.\dump_YYYYMMDD_HHMMSS.dmp* on Windows.</span></span>
  - <span data-ttu-id="b1edc-148">Wartość domyślna to *./core_YYYYMMDD_HHMMSS* w systemie Linux.</span><span class="sxs-lookup"><span data-stu-id="b1edc-148">Defaults to *./core_YYYYMMDD_HHMMSS* on Linux.</span></span>

  <span data-ttu-id="b1edc-149">RRRRMMDD to rok/miesiąc/dzień, a HHMMSS to godzina/minutę/sekundę.</span><span class="sxs-lookup"><span data-stu-id="b1edc-149">YYYYMMDD is Year/Month/Day and HHMMSS is Hour/Minute/Second.</span></span>

- **`--diag`**

  <span data-ttu-id="b1edc-150">Włącza rejestrowanie diagnostyczne kolekcji zrzutów.</span><span class="sxs-lookup"><span data-stu-id="b1edc-150">Enables dump collection diagnostic logging.</span></span>

## <a name="dotnet-dump-analyze"></a><span data-ttu-id="b1edc-151">Analiza zrzutów dotnet</span><span class="sxs-lookup"><span data-stu-id="b1edc-151">dotnet-dump analyze</span></span>

<span data-ttu-id="b1edc-152">Uruchamia powłokę interaktywną w celu eksplorowania zrzutu.</span><span class="sxs-lookup"><span data-stu-id="b1edc-152">Starts an interactive shell to explore a dump.</span></span> <span data-ttu-id="b1edc-153">Powłoka akceptuje różne [polecenia sos](#analyze-sos-commands).</span><span class="sxs-lookup"><span data-stu-id="b1edc-153">The shell accepts various [SOS commands](#analyze-sos-commands).</span></span>

### <a name="synopsis"></a><span data-ttu-id="b1edc-154">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="b1edc-154">Synopsis</span></span>

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a><span data-ttu-id="b1edc-155">Argumenty</span><span class="sxs-lookup"><span data-stu-id="b1edc-155">Arguments</span></span>

- **`<dump_path>`**

  <span data-ttu-id="b1edc-156">Określa ścieżkę do pliku zrzutu do przeanalizowania.</span><span class="sxs-lookup"><span data-stu-id="b1edc-156">Specifies the path to the dump file to analyze.</span></span>

### <a name="options"></a><span data-ttu-id="b1edc-157">Opcje</span><span class="sxs-lookup"><span data-stu-id="b1edc-157">Options</span></span>

- **`-c|--command <debug_command>`**

  <span data-ttu-id="b1edc-158">Określa [polecenie](#analyze-sos-commands) , które ma być uruchamiane w powłoce przy uruchamianiu.</span><span class="sxs-lookup"><span data-stu-id="b1edc-158">Specifies the [command](#analyze-sos-commands) to run in the shell on start.</span></span>

### <a name="analyze-sos-commands"></a><span data-ttu-id="b1edc-159">Analizowanie poleceń SOS</span><span class="sxs-lookup"><span data-stu-id="b1edc-159">Analyze SOS commands</span></span>

| <span data-ttu-id="b1edc-160">Polecenie</span><span class="sxs-lookup"><span data-stu-id="b1edc-160">Command</span></span>                             | <span data-ttu-id="b1edc-161">Funkcja</span><span class="sxs-lookup"><span data-stu-id="b1edc-161">Function</span></span>                                                                                      |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| `soshelp`                           | <span data-ttu-id="b1edc-162">Wyświetla wszystkie dostępne polecenia</span><span class="sxs-lookup"><span data-stu-id="b1edc-162">Displays all available commands</span></span>                                                               |
| `soshelp|help <command>`            | <span data-ttu-id="b1edc-163">Wyświetla określone polecenie.</span><span class="sxs-lookup"><span data-stu-id="b1edc-163">Displays the specified command.</span></span>                                                               |
| `exit|quit`                         | <span data-ttu-id="b1edc-164">Zamyka tryb interaktywny.</span><span class="sxs-lookup"><span data-stu-id="b1edc-164">Exits interactive mode.</span></span>                                                                       |
| `clrstack <arguments>`              | <span data-ttu-id="b1edc-165">Dostarcza ślad stosu wyłącznie dla kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="b1edc-165">Provides a stack trace of managed code only.</span></span>                                                  |
| `clrthreads <arguments>`            | <span data-ttu-id="b1edc-166">Wyświetla listę zarządzanych wątków, na których działa program.</span><span class="sxs-lookup"><span data-stu-id="b1edc-166">Lists the managed threads running.</span></span>                                                            |
| `dumpasync <arguments>`             | <span data-ttu-id="b1edc-167">Wyświetla informacje o maszynach stanu asynchronicznego na stertie zebranych elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="b1edc-167">Displays information about async state machines on the garbage-collected heap.</span></span>                |
| `dumpassembly <arguments>`          | <span data-ttu-id="b1edc-168">Wyświetla szczegółowe informacje o zestawie.</span><span class="sxs-lookup"><span data-stu-id="b1edc-168">Displays details about an assembly.</span></span>                                                           |
| `dumpclass <arguments>`             | <span data-ttu-id="b1edc-169">Wyświetla informacje o strukturze klasy EE pod podanym adresem.</span><span class="sxs-lookup"><span data-stu-id="b1edc-169">Displays information about a EE class structure at the specified address.</span></span>                     |
| `dumpdelegate <arguments>`          | <span data-ttu-id="b1edc-170">Wyświetla informacje o delegacie.</span><span class="sxs-lookup"><span data-stu-id="b1edc-170">Displays information about a delegate.</span></span>                                                        |
| `dumpdomain <arguments>`            | <span data-ttu-id="b1edc-171">Wyświetla informacje o wszystkich domenach aplikacji i wszystkich zestawach należących do domen.</span><span class="sxs-lookup"><span data-stu-id="b1edc-171">Displays information all the AppDomains and all assemblies within the domains.</span></span>                |
| `dumpheap <arguments>`              | <span data-ttu-id="b1edc-172">Wyświetla informacje na temat sterty i statystyk zbierania danych bezużytecznych dotyczących obiektów.</span><span class="sxs-lookup"><span data-stu-id="b1edc-172">Displays info about the garbage-collected heap and collection statistics about objects.</span></span>       |
| `dumpil <arguments>`                | <span data-ttu-id="b1edc-173">Wyświetla język pośredni Microsoft (MSIL) skojarzony z zarządzaną metodą.</span><span class="sxs-lookup"><span data-stu-id="b1edc-173">Displays the Microsoft intermediate language (MSIL) that is associated with a managed method.</span></span> |
| `dumplog <arguments>`               | <span data-ttu-id="b1edc-174">Zapisuje zawartość dziennika obciążenia pamięci do określonego pliku.</span><span class="sxs-lookup"><span data-stu-id="b1edc-174">Writes the contents of an in-memory stress log to the specified file.</span></span>                         |
| `dumpmd <arguments>`                | <span data-ttu-id="b1edc-175">Wyświetla informacje o strukturze MethodDesc pod podanym adresem.</span><span class="sxs-lookup"><span data-stu-id="b1edc-175">Displays information about a MethodDesc structure at the specified address.</span></span>                   |
| `dumpmodule <arguments>`            | <span data-ttu-id="b1edc-176">Wyświetla informacje o strukturze modułu EE pod podanym adresem.</span><span class="sxs-lookup"><span data-stu-id="b1edc-176">Displays information about a EE module structure at the specified address.</span></span>                    |
| `dumpmt <arguments>`                | <span data-ttu-id="b1edc-177">Wyświetla informacje dotyczące tabeli metod pod podanym adresem.</span><span class="sxs-lookup"><span data-stu-id="b1edc-177">Displays information about a method table at the specified address.</span></span>                           |
| `dumpobj <arguments>`               | <span data-ttu-id="b1edc-178">Wyświetla informacje o obiekcie pod podanym adresem.</span><span class="sxs-lookup"><span data-stu-id="b1edc-178">Displays info about an object at the specified address.</span></span>                                       |
| `dso|dumpstackobjects <arguments>`  | <span data-ttu-id="b1edc-179">Wyświetla wszystkie zarządzane obiekty znalezione w granicach bieżącego stosu.</span><span class="sxs-lookup"><span data-stu-id="b1edc-179">Displays all managed objects found within the bounds of the current stack.</span></span>                    |
| `eeheap <arguments>`                | <span data-ttu-id="b1edc-180">Wyświetla informacje o pamięci procesu używanej przez wewnętrzne struktury danych środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="b1edc-180">Displays info about process memory consumed by internal runtime data structures.</span></span>              |
| `finalizequeue <arguments>`         | <span data-ttu-id="b1edc-181">Wyświetla wszystkie obiekty zarejestrowane dla finalizacji.</span><span class="sxs-lookup"><span data-stu-id="b1edc-181">Displays all objects registered for finalization.</span></span>                                             |
| `gcroot <arguments>`                | <span data-ttu-id="b1edc-182">Wyświetla informacje o odwołaniach (lub elementach głównych) do obiektu pod podanym adresem.</span><span class="sxs-lookup"><span data-stu-id="b1edc-182">Displays info about references (or roots) to an object at the specified address.</span></span>              |
| `gcwhere <arguments>`               | <span data-ttu-id="b1edc-183">Wyświetla lokalizację w stercie GC argumentu przekazano.</span><span class="sxs-lookup"><span data-stu-id="b1edc-183">Displays the location in the GC heap of the argument passed in.</span></span>                               |
| `ip2md <arguments>`                 | <span data-ttu-id="b1edc-184">Wyświetla strukturę MethodDesc o określonym adresie w kodzie JIT.</span><span class="sxs-lookup"><span data-stu-id="b1edc-184">Displays the MethodDesc structure at the specified address in JIT code.</span></span>                       |
| `histclear <arguments>`             | <span data-ttu-id="b1edc-185">Zwalnia wszystkie zasoby używane przez rodzinę `hist*` poleceń.</span><span class="sxs-lookup"><span data-stu-id="b1edc-185">Releases any resources used by the family of `hist*` commands.</span></span>                                |
| `histinit <arguments>`              | <span data-ttu-id="b1edc-186">Inicjuje struktury SOS z dziennika obciążenia zapisanego w obiekcie debugowanym.</span><span class="sxs-lookup"><span data-stu-id="b1edc-186">Initializes the SOS structures from the stress log saved in the debuggee.</span></span>                     |
| `histobj <arguments>`               | <span data-ttu-id="b1edc-187">Wyświetla przemieszczenie dzienników obciążeniowych wyrzucania elementów bezużytecznych powiązanych z `<arguments>` .</span><span class="sxs-lookup"><span data-stu-id="b1edc-187">Displays the garbage collection stress log relocations related to `<arguments>`.</span></span>              |
| `histobjfind <arguments>`           | <span data-ttu-id="b1edc-188">Wyświetla wszystkie wpisy dziennika, które odwołują się do obiektu pod podanym adresem.</span><span class="sxs-lookup"><span data-stu-id="b1edc-188">Displays all the log entries that reference an object at the specified address.</span></span>               |
| `histroot <arguments>`              | <span data-ttu-id="b1edc-189">Wyświetla informacje powiązane zarówno z promocjami, jak i przeniesieniami określonego korzenia.</span><span class="sxs-lookup"><span data-stu-id="b1edc-189">Displays information related to both promotions and relocations of the specified root.</span></span>        |
| `lm|modules`                        | <span data-ttu-id="b1edc-190">Wyświetla moduły macierzyste w procesie.</span><span class="sxs-lookup"><span data-stu-id="b1edc-190">Displays the native modules in the process.</span></span>                                                   |
| `name2ee <arguments>`               | <span data-ttu-id="b1edc-191">Wyświetla strukturę metody i strukturę EEClass dla `<argument>` .</span><span class="sxs-lookup"><span data-stu-id="b1edc-191">Displays the MethodTable structure and EEClass structure for the `<argument>`.</span></span>                |
| `pe|printexception <arguments>`     | <span data-ttu-id="b1edc-192">Wyświetla dowolny obiekt pochodny od klasy Exception pod adresem `<argument>` .</span><span class="sxs-lookup"><span data-stu-id="b1edc-192">Displays any object derived from the Exception class at the address `<argument>`.</span></span>             |
| `setsymbolserver <arguments>`       | <span data-ttu-id="b1edc-193">Włącza obsługę serwera symboli</span><span class="sxs-lookup"><span data-stu-id="b1edc-193">Enables the symbol server support</span></span>                                                             |
| `syncblk <arguments>`               | <span data-ttu-id="b1edc-194">Wyświetla informacje o posiadaczu SyncBlock.</span><span class="sxs-lookup"><span data-stu-id="b1edc-194">Displays the SyncBlock holder info.</span></span>                                                           |
| `threads|setthread <threadid>`      | <span data-ttu-id="b1edc-195">Ustawia lub wyświetla bieżący identyfikator wątku dla poleceń SOS.</span><span class="sxs-lookup"><span data-stu-id="b1edc-195">Sets or displays the current thread ID for the SOS commands.</span></span>                                  |

## <a name="using-dotnet-dump"></a><span data-ttu-id="b1edc-196">Korzystanie z akcji `dotnet-dump`</span><span class="sxs-lookup"><span data-stu-id="b1edc-196">Using `dotnet-dump`</span></span>

<span data-ttu-id="b1edc-197">Pierwszym krokiem jest zebranie zrzutu.</span><span class="sxs-lookup"><span data-stu-id="b1edc-197">The first step is to collect a dump.</span></span> <span data-ttu-id="b1edc-198">Ten krok można pominąć, jeśli zrzut podstawowy został już wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="b1edc-198">This step can be skipped if a core dump has already been generated.</span></span> <span data-ttu-id="b1edc-199">System operacyjny lub wbudowana [Funkcja generowania zrzutów](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) środowiska uruchomieniowego platformy .NET Core może tworzyć zrzuty rdzeni.</span><span class="sxs-lookup"><span data-stu-id="b1edc-199">The operating system or the .NET Core runtime's built-in [dump generation feature](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) can each create core dumps.</span></span>

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

<span data-ttu-id="b1edc-200">Teraz Analizuj podstawowy zrzut przy użyciu `analyze` polecenia:</span><span class="sxs-lookup"><span data-stu-id="b1edc-200">Now analyze the core dump with the `analyze` command:</span></span>

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

<span data-ttu-id="b1edc-201">Ta akcja wywołuje interaktywną sesję, która akceptuje polecenia takie jak:</span><span class="sxs-lookup"><span data-stu-id="b1edc-201">This action brings up an interactive session that accepts commands like:</span></span>

```console
> clrstack
OS Thread Id: 0x573d (0)
    Child SP               IP Call Site
00007FFD28B42C58 00007fb22c1a8ed9 [HelperMethodFrame_PROTECTOBJ: 00007ffd28b42c58] System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo) [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.Program.Foo4(System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.Program.Foo2(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.Program.Foo1(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.Program.Main(System.String[]) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]
00007FFD28B43210 00007fb22aa9cedf [GCFrame: 00007ffd28b43210]
00007FFD28B43610 00007fb22aa9cedf [GCFrame: 00007ffd28b43610]
```

<span data-ttu-id="b1edc-202">Aby wyświetlić nieobsłużony wyjątek, który zabicia aplikacji:</span><span class="sxs-lookup"><span data-stu-id="b1edc-202">To see an unhandled exception that killed your app:</span></span>

```console
> pe -lines
Exception object: 00007fb18c038590
Exception type:   System.Reflection.TargetInvocationException
Message:          Exception has been thrown by the target of an invocation.
InnerException:   System.Exception, Use !PrintException 00007FB18C038368 to see more.
StackTrace (generated):
SP               IP               Function
00007FFD28B42DD0 0000000000000000 System.Private.CoreLib.dll!System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Private.CoreLib.dll!System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo)+0xa7 [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.dll!SymbolTestApp.Program.Foo4(System.String)+0x15d [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.dll!SymbolTestApp.Program.Foo2(Int32, System.String)+0x34 [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.dll!SymbolTestApp.Program.Foo1(Int32, System.String)+0x3a [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.dll!SymbolTestApp.Program.Main(System.String[])+0x6e [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]

StackTraceString: <none>
HResult: 80131604
```

## <a name="special-instructions-for-docker"></a><span data-ttu-id="b1edc-203">Specjalne instrukcje dotyczące platformy Docker</span><span class="sxs-lookup"><span data-stu-id="b1edc-203">Special instructions for Docker</span></span>

<span data-ttu-id="b1edc-204">Jeśli używasz programu Docker, Zbieranie zrzutów wymaga `SYS_PTRACE` możliwości ( `--cap-add=SYS_PTRACE` lub `--privileged` ).</span><span class="sxs-lookup"><span data-stu-id="b1edc-204">If you're running under Docker, dump collection requires `SYS_PTRACE` capabilities (`--cap-add=SYS_PTRACE` or `--privileged`).</span></span>

<span data-ttu-id="b1edc-205">W przypadku obrazów platformy Docker w systemie Microsoft .NET Core SDK Linux niektóre `dotnet-dump` polecenia mogą zgłosić następujący wyjątek:</span><span class="sxs-lookup"><span data-stu-id="b1edc-205">On Microsoft .NET Core SDK Linux Docker images, some `dotnet-dump` commands can throw the following exception:</span></span>

> <span data-ttu-id="b1edc-206">Nieobsłużony wyjątek: System.DllNotFoundException: nie można załadować biblioteki udostępnionej "libdl.so" ani jednego z jej wyjątków zależności.</span><span class="sxs-lookup"><span data-stu-id="b1edc-206">Unhandled exception: System.DllNotFoundException: Unable to load shared library 'libdl.so' or one of its dependencies' exception.</span></span>

<span data-ttu-id="b1edc-207">Aby obejść ten problem, zainstaluj pakiet "libc6-dev".</span><span class="sxs-lookup"><span data-stu-id="b1edc-207">To work around this problem, install the "libc6-dev" package.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1edc-208">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b1edc-208">See also</span></span>

- [<span data-ttu-id="b1edc-209">Zbieranie i analizowanie blogów zrzutów pamięci</span><span class="sxs-lookup"><span data-stu-id="b1edc-209">Collecting and analyzing memory dumps blog</span></span>](https://devblogs.microsoft.com/dotnet/collecting-and-analyzing-memory-dumps/)
- [<span data-ttu-id="b1edc-210">Narzędzie do analizy sterty (dotnet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="b1edc-210">Heap analysis tool (dotnet-gcdump)</span></span>](dotnet-gcdump.md)
