---
title: Rozwiązywanie problemów z użyciem narzędzia .NET Core
description: Poznaj typowe problemy występujące podczas uruchamiania narzędzi .NET Core i możliwych rozwiązań.
author: kdollard
ms.topic: troubleshooting
ms.date: 02/14/2020
ms.openlocfilehash: db88958e1605fef589c5dbcb12065a6318183705
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608316"
---
# <a name="troubleshoot-net-core-tool-usage-issues"></a><span data-ttu-id="55b91-103">Rozwiązywanie problemów z użyciem narzędzia .NET Core</span><span class="sxs-lookup"><span data-stu-id="55b91-103">Troubleshoot .NET Core tool usage issues</span></span>

<span data-ttu-id="55b91-104">Podczas próby zainstalowania lub uruchomienia narzędzia platformy .NET Core może wystąpić problem, który może być globalnym narzędziem lub narzędziem lokalnym.</span><span class="sxs-lookup"><span data-stu-id="55b91-104">You might come across issues when trying to install or run a .NET Core tool, which can be a global tool or a local tool.</span></span> <span data-ttu-id="55b91-105">W tym artykule opisano typowe główne przyczyny i niektóre możliwe rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="55b91-105">This article describes the common root causes and some possible solutions.</span></span>

## <a name="installed-net-core-tool-fails-to-run"></a><span data-ttu-id="55b91-106">Nie można uruchomić zainstalowanego narzędzia .NET Core</span><span class="sxs-lookup"><span data-stu-id="55b91-106">Installed .NET Core tool fails to run</span></span>

<span data-ttu-id="55b91-107">W przypadku niepowodzenia uruchomienia narzędzia .NET Core najprawdopodobniej wystąpił jeden z następujących problemów:</span><span class="sxs-lookup"><span data-stu-id="55b91-107">When a .NET Core tool fails to run, most likely you ran into one of the following issues:</span></span>

* <span data-ttu-id="55b91-108">Nie znaleziono pliku wykonywalnego dla narzędzia.</span><span class="sxs-lookup"><span data-stu-id="55b91-108">The executable file for the tool wasn't found.</span></span>
* <span data-ttu-id="55b91-109">Nie znaleziono prawidłowej wersji środowiska uruchomieniowego .NET Core.</span><span class="sxs-lookup"><span data-stu-id="55b91-109">The correct version of the .NET Core runtime wasn't found.</span></span>

### <a name="executable-file-not-found"></a><span data-ttu-id="55b91-110">Nie znaleziono pliku wykonywalnego</span><span class="sxs-lookup"><span data-stu-id="55b91-110">Executable file not found</span></span>

<span data-ttu-id="55b91-111">Jeśli plik wykonywalny nie zostanie znaleziony, zostanie wyświetlony komunikat podobny do następującego:</span><span class="sxs-lookup"><span data-stu-id="55b91-111">If the executable file isn't found, you'll see a message similar to the following:</span></span>

```console
Could not execute because the specified command or file was not found.
Possible reasons for this include:
  * You misspelled a built-in dotnet command.
  * You intended to execute a .NET Core program, but dotnet-xyz does not exist.
  * You intended to run a global tool, but a dotnet-prefixed executable with this name could not be found on the PATH.
```

<span data-ttu-id="55b91-112">Nazwa pliku wykonywalnego określa sposób wywołania narzędzia.</span><span class="sxs-lookup"><span data-stu-id="55b91-112">The name of the executable determines how you invoke the tool.</span></span> <span data-ttu-id="55b91-113">W poniższej tabeli opisano format:</span><span class="sxs-lookup"><span data-stu-id="55b91-113">The following table describes the format:</span></span>

| <span data-ttu-id="55b91-114">Format nazwy pliku wykonywalnego</span><span class="sxs-lookup"><span data-stu-id="55b91-114">Executable name format</span></span>  | <span data-ttu-id="55b91-115">Format wywołania</span><span class="sxs-lookup"><span data-stu-id="55b91-115">Invocation format</span></span>   |
|-------------------------|---------------------|
| `dotnet-<toolName>.exe` | `dotnet <toolName>` |
| `<toolName>.exe`        | `<toolName>`        |

* <span data-ttu-id="55b91-116">Narzędzia globalne</span><span class="sxs-lookup"><span data-stu-id="55b91-116">Global tools</span></span>

  <span data-ttu-id="55b91-117">Narzędzia globalne można zainstalować w katalogu domyślnym lub w określonej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="55b91-117">Global tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="55b91-118">Domyślne katalogi są następujące:</span><span class="sxs-lookup"><span data-stu-id="55b91-118">The default directories are:</span></span>

  | <span data-ttu-id="55b91-119">System operacyjny</span><span class="sxs-lookup"><span data-stu-id="55b91-119">OS</span></span>          | <span data-ttu-id="55b91-120">Ścieżka</span><span class="sxs-lookup"><span data-stu-id="55b91-120">Path</span></span>                          |
  |-------------|-------------------------------|
  | <span data-ttu-id="55b91-121">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="55b91-121">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
  | <span data-ttu-id="55b91-122">Windows</span><span class="sxs-lookup"><span data-stu-id="55b91-122">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

  <span data-ttu-id="55b91-123">Jeśli próbujesz uruchomić narzędzie globalne, sprawdź, czy `PATH` zmienna środowiskowa na komputerze zawiera ścieżkę, w której zainstalowano narzędzie globalne i czy plik wykonywalny znajduje się w tej ścieżce.</span><span class="sxs-lookup"><span data-stu-id="55b91-123">If you're trying to run a global tool, check that the `PATH` environment variable on your machine contains the path where you installed the global tool and that the executable is in that path.</span></span>

  <span data-ttu-id="55b91-124">Interfejs wiersza polecenia platformy .NET Core próbuje dodać domyślną lokalizację do zmiennej środowiskowej PATH przy pierwszym użyciu.</span><span class="sxs-lookup"><span data-stu-id="55b91-124">The .NET Core CLI tries to add the default location to the PATH environment variable on its first usage.</span></span> <span data-ttu-id="55b91-125">Istnieją jednak sytuacje, w których lokalizacja nie może być automatycznie dodawana do ścieżki:</span><span class="sxs-lookup"><span data-stu-id="55b91-125">However, there are some scenarios where the location might not be added to PATH automatically:</span></span>

  * <span data-ttu-id="55b91-126">Jeśli używasz systemu Linux i zainstalowano zestaw .NET Core SDK przy użyciu plików *tar. gz* , a nie apt-get lub RPM.</span><span class="sxs-lookup"><span data-stu-id="55b91-126">If you're using Linux and you've installed the .NET Core SDK using *.tar.gz* files and not apt-get or rpm.</span></span>
  * <span data-ttu-id="55b91-127">Jeśli używasz macOS 10,15 "Catalina" lub nowszych wersji.</span><span class="sxs-lookup"><span data-stu-id="55b91-127">If you're using macOS 10.15 "Catalina" or later versions.</span></span>
  * <span data-ttu-id="55b91-128">Jeśli używasz macOS 10,14 "Mojave" lub wcześniejszych wersji, a zainstalowano zestaw .NET Core SDK przy użyciu plików *tar. gz* , a nie *. pkg*.</span><span class="sxs-lookup"><span data-stu-id="55b91-128">If you're using macOS 10.14 "Mojave" or earlier versions, and you've installed the .NET Core SDK using *.tar.gz* files and not *.pkg*.</span></span>
  * <span data-ttu-id="55b91-129">Jeśli zainstalowano zestaw SDK programu .NET Core 3,0 i ustawisz `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` zmienną środowiskową na `false` .</span><span class="sxs-lookup"><span data-stu-id="55b91-129">If you've installed the .NET Core 3.0 SDK and you've set the `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` environment variable to `false`.</span></span>
  * <span data-ttu-id="55b91-130">Jeśli zainstalowano zestaw .NET Core 2,2 SDK lub wcześniejsze wersje, a `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` zmienna środowiskowa jest ustawiona na `true` .</span><span class="sxs-lookup"><span data-stu-id="55b91-130">If you've installed .NET Core 2.2 SDK or earlier versions, and you've set the `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` environment variable to `true`.</span></span>

  <span data-ttu-id="55b91-131">W tych scenariuszach lub w przypadku wybrania `--tool-path` opcji `PATH` zmienna środowiskowa na komputerze nie zawiera automatycznie ścieżki, w której zainstalowano narzędzie globalne.</span><span class="sxs-lookup"><span data-stu-id="55b91-131">In these scenarios or if you specified the `--tool-path` option, the `PATH` environment variable on your machine doesn't automatically contain the path where you installed the global tool.</span></span> <span data-ttu-id="55b91-132">W takim przypadku należy dołączyć lokalizację narzędzia (na przykład `$HOME/.dotnet/tools` ) do `PATH` zmiennej środowiskowej przy użyciu dowolnej metody zapewnianej przez powłokę do aktualizowania zmiennych środowiskowych.</span><span class="sxs-lookup"><span data-stu-id="55b91-132">In that case, append the tool location (for example, `$HOME/.dotnet/tools`) to the `PATH` environment variable by using whatever method your shell provides for updating environment variables.</span></span> <span data-ttu-id="55b91-133">Aby uzyskać więcej informacji, zobacz [Narzędzia platformy .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="55b91-133">For more information, see [.NET Core tools](global-tools.md).</span></span>

* <span data-ttu-id="55b91-134">Narzędzia lokalne</span><span class="sxs-lookup"><span data-stu-id="55b91-134">Local tools</span></span>

  <span data-ttu-id="55b91-135">Jeśli próbujesz uruchomić narzędzie lokalne, sprawdź, czy istnieje plik manifestu o nazwie *dotnet-tools.json* w bieżącym katalogu lub w dowolnym z jego katalogów nadrzędnych.</span><span class="sxs-lookup"><span data-stu-id="55b91-135">If you're trying to run a local tool, verify that there's a manifest file called *dotnet-tools.json* in the current directory or any of its parent directories.</span></span> <span data-ttu-id="55b91-136">Ten plik może również znajdować się w folderze o nazwie *. config* gdziekolwiek w hierarchii folderów projektu, a nie w folderze głównym.</span><span class="sxs-lookup"><span data-stu-id="55b91-136">This file can also live under a folder named *.config* anywhere in the project folder hierarchy, instead of the root folder.</span></span> <span data-ttu-id="55b91-137">Jeśli *dotnet-tools.json* istnieje, otwórz go i sprawdź narzędzie, które próbujesz uruchomić.</span><span class="sxs-lookup"><span data-stu-id="55b91-137">If *dotnet-tools.json* exists, open it and check for the tool you're trying to run.</span></span> <span data-ttu-id="55b91-138">Jeśli plik nie zawiera wpisu dla programu `"isRoot": true` , należy również zapoznać się z tematem dalszej hierarchii plików dla dodatkowych plików manifestu narzędzia.</span><span class="sxs-lookup"><span data-stu-id="55b91-138">If the file doesn't contain an entry for `"isRoot": true`, then also check further up the file hierarchy for additional tool manifest files.</span></span>

  <span data-ttu-id="55b91-139">Jeśli próbujesz uruchomić narzędzie .NET Core, które zostało zainstalowane z określoną ścieżką, musisz dołączyć tę ścieżkę podczas korzystania z narzędzia.</span><span class="sxs-lookup"><span data-stu-id="55b91-139">If you're trying to run a .NET Core tool that was installed with a specified path, you need to include that path when using the tool.</span></span> <span data-ttu-id="55b91-140">Przykładem użycia narzędzia z zainstalowaną ścieżką narzędzia jest:</span><span class="sxs-lookup"><span data-stu-id="55b91-140">An example of using a tool-path installed tool is:</span></span>

  ```console
  ..\<toolDirectory>\dotnet-<toolName>
  ```

### <a name="runtime-not-found"></a><span data-ttu-id="55b91-141">Nie znaleziono środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="55b91-141">Runtime not found</span></span>

<span data-ttu-id="55b91-142">Narzędzia .NET Core są [aplikacjami zależnymi od](../deploying/index.md#publish-framework-dependent)platformy, co oznacza, że korzystają z środowiska uruchomieniowego .NET Core zainstalowanego na komputerze.</span><span class="sxs-lookup"><span data-stu-id="55b91-142">.NET Core tools are [framework-dependent applications](../deploying/index.md#publish-framework-dependent), which means they rely on a .NET Core runtime installed on your machine.</span></span> <span data-ttu-id="55b91-143">Jeśli oczekiwane środowisko uruchomieniowe nie zostanie znalezione, są one zgodne z normalnymi regułami przetaczania w czasie wykonywania w środowisku .NET Core</span><span class="sxs-lookup"><span data-stu-id="55b91-143">If the expected runtime isn't found, they follow normal .NET Core runtime roll-forward rules such as:</span></span>

* <span data-ttu-id="55b91-144">Aplikacja przenosi do przodu do najwyższej wersji poprawki określonej głównej i pomocniczej.</span><span class="sxs-lookup"><span data-stu-id="55b91-144">An application rolls forward to the highest patch release of the specified major and minor version.</span></span>
* <span data-ttu-id="55b91-145">Jeśli nie ma pasującego środowiska uruchomieniowego z odpowiadającym mu numerem wersji głównej i pomocniczej, używana jest kolejna wyższa wersja pomocnicza.</span><span class="sxs-lookup"><span data-stu-id="55b91-145">If there's no matching runtime with a matching major and minor version number, the next higher minor version is used.</span></span>
* <span data-ttu-id="55b91-146">Przewinięcie do przodu nie występuje między wersjami w wersji zapoznawczej środowiska uruchomieniowego a wersjami zapoznawczymi i wersjami.</span><span class="sxs-lookup"><span data-stu-id="55b91-146">Roll forward doesn't occur between preview versions of the runtime or between preview versions and release versions.</span></span> <span data-ttu-id="55b91-147">W związku z tym narzędzia programu .NET Core utworzone przy użyciu wersji zapoznawczej muszą zostać odbudowane i ponownie opublikowane przez autora oraz zainstalowaną ponowną instalację.</span><span class="sxs-lookup"><span data-stu-id="55b91-147">So, .NET Core tools created using preview versions must be rebuilt and republished by the author and reinstalled.</span></span>

<span data-ttu-id="55b91-148">Przekazanie do przodu nie będzie odbywać się domyślnie w dwóch typowych scenariuszach:</span><span class="sxs-lookup"><span data-stu-id="55b91-148">Roll-forward won't occur by default in two common scenarios:</span></span>

* <span data-ttu-id="55b91-149">Dostępne są tylko małe wersje środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="55b91-149">Only lower versions of the runtime are available.</span></span> <span data-ttu-id="55b91-150">Przekazanie do przodu wybiera tylko późniejsze wersje środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="55b91-150">Roll-forward only selects later versions of the runtime.</span></span>
* <span data-ttu-id="55b91-151">Dostępne są tylko nowsze wersje główne środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="55b91-151">Only higher major versions of the runtime are available.</span></span> <span data-ttu-id="55b91-152">Przekazanie do przodu nie przekracza głównych granic wersji.</span><span class="sxs-lookup"><span data-stu-id="55b91-152">Roll-forward doesn't cross major version boundaries.</span></span>

<span data-ttu-id="55b91-153">Jeśli aplikacja nie może znaleźć odpowiedniego środowiska uruchomieniowego, nie można uruchomić i zgłosi błąd.</span><span class="sxs-lookup"><span data-stu-id="55b91-153">If an application can't find an appropriate runtime, it fails to run and reports an error.</span></span>

<span data-ttu-id="55b91-154">Aby dowiedzieć się, które środowiska uruchomieniowe platformy .NET Core są zainstalowane na maszynie, użyj jednego z następujących poleceń:</span><span class="sxs-lookup"><span data-stu-id="55b91-154">You can find out which .NET Core runtimes are installed on your machine using one of the following commands:</span></span>

```dotnetcli
dotnet --list-runtimes
dotnet --info
```

<span data-ttu-id="55b91-155">Jeśli uważasz, że narzędzie powinno obsługiwać aktualnie zainstalowaną wersję środowiska uruchomieniowego, możesz skontaktować się z autorem narzędzia i sprawdzić, czy może zaktualizować numer wersji lub wiele obiektów docelowych.</span><span class="sxs-lookup"><span data-stu-id="55b91-155">If you think the tool should support the runtime version you currently have installed, you can contact the tool author and see if they can update the version number or multi-target.</span></span> <span data-ttu-id="55b91-156">Po ponownym skompilowaniu i ponownym opublikowaniu pakietu narzędzi do NuGet przy użyciu zaktualizowanego numeru wersji można zaktualizować kopię.</span><span class="sxs-lookup"><span data-stu-id="55b91-156">Once they've recompiled and republished their tool package to NuGet with an updated version number, you can update your copy.</span></span> <span data-ttu-id="55b91-157">Chociaż to się nie dzieje, najszybszym rozwiązaniem jest zainstalowanie wersji środowiska uruchomieniowego, która będzie działać z narzędziem, które próbujesz uruchomić.</span><span class="sxs-lookup"><span data-stu-id="55b91-157">While that doesn't happen, the quickest solution for you is to install a version of the runtime that would work with the tool you're trying to run.</span></span> <span data-ttu-id="55b91-158">Aby pobrać konkretną wersję środowiska uruchomieniowego platformy .NET Core, odwiedź [stronę pobierania programu .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="55b91-158">To download a specific .NET Core runtime version, visit the [.NET Core download page](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="55b91-159">W przypadku zainstalowania zestaw .NET Core SDK w lokalizacji innej niż domyślna należy ustawić dla zmiennej środowiskowej `DOTNET_ROOT` katalog zawierający `dotnet` plik wykonywalny.</span><span class="sxs-lookup"><span data-stu-id="55b91-159">If you install the .NET Core SDK to a non-default location, you need to set the environment variable `DOTNET_ROOT` to the directory that contains the `dotnet` executable.</span></span>

## <a name="net-core-tool-installation-fails"></a><span data-ttu-id="55b91-160">Instalacja narzędzia .NET Core kończy się niepowodzeniem</span><span class="sxs-lookup"><span data-stu-id="55b91-160">.NET Core tool installation fails</span></span>

<span data-ttu-id="55b91-161">Istnieje kilka powodów, dla których instalacja narzędzia globalnego lub lokalnego programu .NET Core może zakończyć się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="55b91-161">There are a number of reasons the installation of a .NET Core global or local tool may fail.</span></span> <span data-ttu-id="55b91-162">Gdy instalacja narzędzia nie powiedzie się, zostanie wyświetlony komunikat podobny do następującego:</span><span class="sxs-lookup"><span data-stu-id="55b91-162">When the tool installation fails, you'll see a message similar to the following one:</span></span>

```console
Tool '{0}' failed to install. This failure may have been caused by:

* You are attempting to install a preview release and did not use the --version option to specify the version.
* A package by this name was found, but it was not a .NET Core tool.
* The required NuGet feed cannot be accessed, perhaps because of an Internet connection problem.
* You mistyped the name of the tool.

For more reasons, including package naming enforcement, visit https://aka.ms/failure-installing-tool
```

<span data-ttu-id="55b91-163">Aby pomóc zdiagnozować te błędy, komunikaty NuGet są wyświetlane bezpośrednio użytkownikowi wraz z poprzednią wiadomością.</span><span class="sxs-lookup"><span data-stu-id="55b91-163">To help diagnose these failures, NuGet messages are shown directly to the user, along with the previous message.</span></span> <span data-ttu-id="55b91-164">Komunikat NuGet może pomóc w zidentyfikowaniu problemu.</span><span class="sxs-lookup"><span data-stu-id="55b91-164">The NuGet message may help you identify the problem.</span></span>

### <a name="package-naming-enforcement"></a><span data-ttu-id="55b91-165">Wymuszanie nazewnictwa pakietów</span><span class="sxs-lookup"><span data-stu-id="55b91-165">Package naming enforcement</span></span>

<span data-ttu-id="55b91-166">Firma Microsoft zmieniła swoje wskazówki dotyczące identyfikatora pakietu dla narzędzi, co spowodowało, że nie znaleziono wielu narzędzi z przewidywaną nazwą.</span><span class="sxs-lookup"><span data-stu-id="55b91-166">Microsoft has changed its guidance on the Package ID for tools, resulting in a number of tools not being found with the predicted name.</span></span> <span data-ttu-id="55b91-167">Nowe wskazówki polegają na tym, że wszystkie narzędzia firmy Microsoft są poprzedzone prefiksem "Microsoft".</span><span class="sxs-lookup"><span data-stu-id="55b91-167">The new guidance is that all Microsoft tools be prefixed with "Microsoft."</span></span> <span data-ttu-id="55b91-168">Ten prefiks jest zarezerwowany i może być używany tylko w przypadku pakietów podpisanych za pomocą autoryzowanego certyfikatu firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55b91-168">This prefix is reserved and can only be used for packages signed with a Microsoft authorized certificate.</span></span>

<span data-ttu-id="55b91-169">W trakcie przejścia niektóre narzędzia firmy Microsoft będą miały starą postać identyfikatora pakietu, a inne będą miały nowy formularz:</span><span class="sxs-lookup"><span data-stu-id="55b91-169">During the transition, some Microsoft tools will have the old form of the package ID, while others will have the new form:</span></span>

```dotnetcli
dotnet tool install -g Microsoft.<toolName>
dotnet tool install -g <toolName>
```

<span data-ttu-id="55b91-170">W miarę aktualizowania identyfikatorów pakietów należy zmienić identyfikator pakietu, aby pobrać najnowsze aktualizacje.</span><span class="sxs-lookup"><span data-stu-id="55b91-170">As package IDs are updated, you'll need to change to the new package ID to get the latest updates.</span></span> <span data-ttu-id="55b91-171">Pakiety z uproszczoną nazwą narzędzia będą przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="55b91-171">Packages with the simplified tool name will be deprecated.</span></span>

### <a name="preview-releases"></a><span data-ttu-id="55b91-172">Wersje zapoznawcze</span><span class="sxs-lookup"><span data-stu-id="55b91-172">Preview releases</span></span>

* <span data-ttu-id="55b91-173">Podjęto próbę zainstalowania wersji zapoznawczej i nie użyto `--version` opcji do określenia wersji.</span><span class="sxs-lookup"><span data-stu-id="55b91-173">You're attempting to install a preview release and didn't use the `--version` option to specify the version.</span></span>

<span data-ttu-id="55b91-174">Narzędzia .NET Core, które są w wersji zapoznawczej, muszą być określone przy użyciu części nazwy, aby wskazać, że są one w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="55b91-174">.NET Core tools that are in preview must be specified with a portion of the name to indicate that they are in preview.</span></span> <span data-ttu-id="55b91-175">Nie musisz zawierać całej wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="55b91-175">You don't need to include the entire preview.</span></span> <span data-ttu-id="55b91-176">Przy założeniu, że numery wersji mają oczekiwany format, można użyć podobnej do poniższego przykładu:</span><span class="sxs-lookup"><span data-stu-id="55b91-176">Assuming the version numbers are in the expected format, you can use something like the following example:</span></span>

```dotnetcli
dotnet tool install -g --version 1.1.0-pre <toolName>
```

### <a name="package-isnt-a-net-core-tool"></a><span data-ttu-id="55b91-177">Pakiet nie jest narzędziem platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="55b91-177">Package isn't a .NET Core tool</span></span>

* <span data-ttu-id="55b91-178">Znaleziono pakiet NuGet o tej nazwie, ale nie jest to narzędzie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="55b91-178">A NuGet package by this name was found, but it wasn't a .NET Core tool.</span></span>

<span data-ttu-id="55b91-179">Jeśli spróbujesz zainstalować pakiet NuGet, który jest regularnym pakietem NuGet, a nie narzędziem .NET Core, zobaczysz błąd podobny do poniższego:</span><span class="sxs-lookup"><span data-stu-id="55b91-179">If you try to install a NuGet package that is a regular NuGet package and not a .NET Core tool, you'll see an error similar to the following:</span></span>

> <span data-ttu-id="55b91-180">NU1212: Nieprawidłowa kombinacja projektu — pakiet dla `<ToolName>` .</span><span class="sxs-lookup"><span data-stu-id="55b91-180">NU1212: Invalid project-package combination for `<ToolName>`.</span></span> <span data-ttu-id="55b91-181">Styl projektu DotnetToolReference może zawierać tylko odwołania do typu DotnetTool.</span><span class="sxs-lookup"><span data-stu-id="55b91-181">DotnetToolReference project style can only contain references of the DotnetTool type.</span></span>

### <a name="nuget-feed-cant-be-accessed"></a><span data-ttu-id="55b91-182">Nie można uzyskać dostępu do źródła danych NuGet</span><span class="sxs-lookup"><span data-stu-id="55b91-182">NuGet feed can't be accessed</span></span>

* <span data-ttu-id="55b91-183">Nie można uzyskać dostępu do wymaganego kanału informacyjnego NuGet, prawdopodobnie z powodu problemu z połączeniem internetowym.</span><span class="sxs-lookup"><span data-stu-id="55b91-183">The required NuGet feed can't be accessed, perhaps because of an Internet connection problem.</span></span>

<span data-ttu-id="55b91-184">Instalacja narzędzia wymaga dostępu do źródła danych NuGet zawierającego pakiet narzędzi.</span><span class="sxs-lookup"><span data-stu-id="55b91-184">Tool installation requires access to the NuGet feed that contains the tool package.</span></span> <span data-ttu-id="55b91-185">Nie powiedzie się, jeśli źródło danych nie jest dostępne.</span><span class="sxs-lookup"><span data-stu-id="55b91-185">It fails if the feed isn't available.</span></span> <span data-ttu-id="55b91-186">Można zmienić źródła danych z `nuget.config` , zażądać określonego `nuget.config` pliku lub określić dodatkowe źródła danych za pomocą `--add-source` przełącznika.</span><span class="sxs-lookup"><span data-stu-id="55b91-186">You can alter feeds with `nuget.config`, request a specific `nuget.config` file, or specify additional feeds with the `--add-source` switch.</span></span> <span data-ttu-id="55b91-187">Domyślnie NuGet zgłasza błąd dla każdego źródła danych, które nie może nawiązać połączenia.</span><span class="sxs-lookup"><span data-stu-id="55b91-187">By default, NuGet throws an error for any feed that can't connect.</span></span> <span data-ttu-id="55b91-188">Flaga `--ignore-failed-sources` może pominąć te źródła nieosiągalne.</span><span class="sxs-lookup"><span data-stu-id="55b91-188">The flag `--ignore-failed-sources` can skip these non-reachable sources.</span></span>

### <a name="package-id-incorrect"></a><span data-ttu-id="55b91-189">Nieprawidłowy identyfikator pakietu</span><span class="sxs-lookup"><span data-stu-id="55b91-189">Package ID incorrect</span></span>

* <span data-ttu-id="55b91-190">Nazwa narzędzia nie została wpisana.</span><span class="sxs-lookup"><span data-stu-id="55b91-190">You mistyped the name of the tool.</span></span>

<span data-ttu-id="55b91-191">Typową przyczyną błędu jest to, że nazwa narzędzia nie jest poprawna.</span><span class="sxs-lookup"><span data-stu-id="55b91-191">A common reason for failure is that the tool name isn't correct.</span></span> <span data-ttu-id="55b91-192">Może się to zdarzyć z powodu błędnego wpisania lub, ponieważ narzędzie zostało przeniesione lub zostało zaniechane.</span><span class="sxs-lookup"><span data-stu-id="55b91-192">This can happen because of mistyping, or because the tool has moved or been deprecated.</span></span> <span data-ttu-id="55b91-193">W przypadku narzędzi w systemie NuGet.org należy upewnić się, że nazwa jest poprawna, aby wyszukać narzędzie pod adresem NuGet.org i skopiować polecenie instalacji.</span><span class="sxs-lookup"><span data-stu-id="55b91-193">For tools on NuGet.org, one way to ensure you have the name correct is to search for the tool at NuGet.org and copy the installation command.</span></span>

## <a name="see-also"></a><span data-ttu-id="55b91-194">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="55b91-194">See also</span></span>

* [<span data-ttu-id="55b91-195">Narzędzia .NET Core</span><span class="sxs-lookup"><span data-stu-id="55b91-195">.NET Core tools</span></span>](global-tools.md)
