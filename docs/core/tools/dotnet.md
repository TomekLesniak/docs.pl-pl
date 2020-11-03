---
title: dotnet — polecenie
description: Dowiedz się więcej na temat polecenia dotnet (sterownika generycznego dla interfejs wiersza polecenia platformy .NET Core) i jego użycia.
ms.date: 02/13/2020
ms.openlocfilehash: 4e182e1b8dff725c479297f7f1587ceaccf2942f
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "93281626"
---
# <a name="dotnet-command"></a><span data-ttu-id="32c1b-103">dotnet — polecenie</span><span class="sxs-lookup"><span data-stu-id="32c1b-103">dotnet command</span></span>

<span data-ttu-id="32c1b-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,1 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="32c1b-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="32c1b-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="32c1b-105">Name</span></span>

<span data-ttu-id="32c1b-106">`dotnet` — Sterownik generyczny dla interfejs wiersza polecenia platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="32c1b-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="32c1b-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="32c1b-107">Synopsis</span></span>

<span data-ttu-id="32c1b-108">Aby uzyskać informacje na temat dostępnych poleceń i środowiska:</span><span class="sxs-lookup"><span data-stu-id="32c1b-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
```

<span data-ttu-id="32c1b-109">Aby uruchomić polecenie (wymaga instalacji zestawu SDK):</span><span class="sxs-lookup"><span data-stu-id="32c1b-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

<span data-ttu-id="32c1b-110">Aby uruchomić aplikację:</span><span class="sxs-lookup"><span data-stu-id="32c1b-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="32c1b-111">`--roll-forward` jest dostępny od wersji .NET Core 3. x.</span><span class="sxs-lookup"><span data-stu-id="32c1b-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="32c1b-112">Używany `--roll-forward-on-no-candidate-fx` dla platformy .NET Core 2. x.</span><span class="sxs-lookup"><span data-stu-id="32c1b-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="32c1b-113">Opis</span><span class="sxs-lookup"><span data-stu-id="32c1b-113">Description</span></span>

<span data-ttu-id="32c1b-114">`dotnet`Polecenie ma dwie funkcje:</span><span class="sxs-lookup"><span data-stu-id="32c1b-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="32c1b-115">Zawiera polecenia umożliwiające pracę z projektami .NET Core.</span><span class="sxs-lookup"><span data-stu-id="32c1b-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="32c1b-116">Na przykład [`dotnet build`](dotnet-build.md) kompiluje projekt.</span><span class="sxs-lookup"><span data-stu-id="32c1b-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="32c1b-117">Każde polecenie definiuje własne opcje i argumenty.</span><span class="sxs-lookup"><span data-stu-id="32c1b-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="32c1b-118">Wszystkie polecenia obsługują `--help` opcję drukowania krótkiej dokumentacji dotyczącej sposobu korzystania z polecenia.</span><span class="sxs-lookup"><span data-stu-id="32c1b-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="32c1b-119">Uruchamia aplikacje platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="32c1b-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="32c1b-120">Należy określić ścieżkę do pliku aplikacji, `.dll` Aby uruchomić aplikację.</span><span class="sxs-lookup"><span data-stu-id="32c1b-120">You specify the path to an application `.dll` file to run the application.</span></span>  <span data-ttu-id="32c1b-121">Aby uruchomić aplikację, należy znaleźć i wykonać punkt wejścia, który w przypadku aplikacji konsolowych jest `Main` metodą.</span><span class="sxs-lookup"><span data-stu-id="32c1b-121">To run the application means to find and execute the entry point, which in the case of console apps is the `Main` method.</span></span> <span data-ttu-id="32c1b-122">Na przykład `dotnet myapp.dll` uruchamia `myapp` aplikację.</span><span class="sxs-lookup"><span data-stu-id="32c1b-122">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="32c1b-123">Zobacz [wdrażanie aplikacji .NET Core](../deploying/index.md) , aby dowiedzieć się więcej na temat opcji wdrażania.</span><span class="sxs-lookup"><span data-stu-id="32c1b-123">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="32c1b-124">Opcje</span><span class="sxs-lookup"><span data-stu-id="32c1b-124">Options</span></span>

<span data-ttu-id="32c1b-125">Różne opcje są dostępne dla `dotnet` siebie, na potrzeby uruchamiania polecenia i uruchamiania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="32c1b-125">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="32c1b-126">Opcje dla dotnet</span><span class="sxs-lookup"><span data-stu-id="32c1b-126">Options for dotnet by itself</span></span>

<span data-ttu-id="32c1b-127">Poniższe opcje są odpowiednie dla `dotnet` siebie.</span><span class="sxs-lookup"><span data-stu-id="32c1b-127">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="32c1b-128">Na przykład `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="32c1b-128">For example, `dotnet --info`.</span></span> <span data-ttu-id="32c1b-129">Drukują informacje o środowisku.</span><span class="sxs-lookup"><span data-stu-id="32c1b-129">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="32c1b-130">Drukuje szczegółowe informacje na temat instalacji programu .NET Core i środowiska maszynowego, takiego jak bieżący system operacyjny, i zatwierdzania SHA dla wersji .NET Core.</span><span class="sxs-lookup"><span data-stu-id="32c1b-130">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="32c1b-131">Drukuje używaną wersję zestaw .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="32c1b-131">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="32c1b-132">Drukuje listę zainstalowanych środowiska uruchomieniowego platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="32c1b-132">Prints out a list of the installed .NET Core runtimes.</span></span> <span data-ttu-id="32c1b-133">Wersja x86 zestawu SDK zawiera tylko środowiska uruchomieniowe x86, a wersja x64 zestawu SDK zawiera tylko środowiska uruchomieniowe x64.</span><span class="sxs-lookup"><span data-stu-id="32c1b-133">An x86 version of the SDK lists only x86 runtimes, and an x64 version of the SDK lists only x64 runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="32c1b-134">Drukuje listę zainstalowanych zestawów SDK platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="32c1b-134">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="32c1b-135">Drukuje listę dostępnych poleceń.</span><span class="sxs-lookup"><span data-stu-id="32c1b-135">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="32c1b-136">Opcje zestawu SDK do uruchamiania polecenia</span><span class="sxs-lookup"><span data-stu-id="32c1b-136">SDK options for running a command</span></span>

<span data-ttu-id="32c1b-137">Następujące opcje są przeznaczone dla `dotnet` polecenia.</span><span class="sxs-lookup"><span data-stu-id="32c1b-137">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="32c1b-138">Na przykład `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="32c1b-138">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="32c1b-139">Włącza diagnostykę danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="32c1b-139">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="32c1b-140">Ustawia poziom szczegółowości polecenia.</span><span class="sxs-lookup"><span data-stu-id="32c1b-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="32c1b-141">Dozwolone wartości to `q[uiet]` , `m[inimal]` , `n[ormal]` , `d[etailed]` i `diag[nostic]` .</span><span class="sxs-lookup"><span data-stu-id="32c1b-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="32c1b-142">Nieobsługiwane w każdym poleceniu.</span><span class="sxs-lookup"><span data-stu-id="32c1b-142">Not supported in every command.</span></span> <span data-ttu-id="32c1b-143">Aby określić, czy ta opcja jest dostępna, zobacz określoną stronę poleceń.</span><span class="sxs-lookup"><span data-stu-id="32c1b-143">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="32c1b-144">Drukuje dokumentację dla danego polecenia, na przykład `dotnet build --help` .</span><span class="sxs-lookup"><span data-stu-id="32c1b-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="32c1b-145">Każde polecenie definiuje opcje specyficzne dla tego polecenia.</span><span class="sxs-lookup"><span data-stu-id="32c1b-145">Each command defines options specific to that command.</span></span> <span data-ttu-id="32c1b-146">Listę dostępnych opcji można znaleźć na stronie z konkretnym poleceniem.</span><span class="sxs-lookup"><span data-stu-id="32c1b-146">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="32c1b-147">Opcje środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="32c1b-147">Runtime options</span></span>

<span data-ttu-id="32c1b-148">Poniższe opcje są dostępne podczas `dotnet` uruchamiania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="32c1b-148">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="32c1b-149">Na przykład `dotnet myapp.dll --roll-forward Major`.</span><span class="sxs-lookup"><span data-stu-id="32c1b-149">For example, `dotnet myapp.dll --roll-forward Major`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="32c1b-150">Ścieżka zawierająca zasady i zestawy do sondowania.</span><span class="sxs-lookup"><span data-stu-id="32c1b-150">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="32c1b-151">Ścieżka do dodatkowego *.deps.js* pliku.</span><span class="sxs-lookup"><span data-stu-id="32c1b-151">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="32c1b-152">*deps.jsw* pliku zawiera listę zależności, zależności kompilacji i informacje o wersji używane do rozwiązywania konfliktów zestawów.</span><span class="sxs-lookup"><span data-stu-id="32c1b-152">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="32c1b-153">Aby uzyskać więcej informacji, zobacz [pliki konfiguracji środowiska uruchomieniowego](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) w serwisie GitHub.</span><span class="sxs-lookup"><span data-stu-id="32c1b-153">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--depsfile <PATH_TO_DEPSFILE>`**

  <span data-ttu-id="32c1b-154">Ścieżka do *deps.js* pliku.</span><span class="sxs-lookup"><span data-stu-id="32c1b-154">Path to the *deps.json* file.</span></span> <span data-ttu-id="32c1b-155">*deps.jsw* pliku to plik konfiguracji, który zawiera informacje o zależnościach niezbędnych do uruchomienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="32c1b-155">A *deps.json* file is a configuration file that contains information about dependencies necessary to run the application.</span></span> <span data-ttu-id="32c1b-156">Ten plik jest generowany przez zestaw .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="32c1b-156">This file is generated by the .NET Core SDK.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="32c1b-157">Ścieżka do *runtimeconfig.js* pliku.</span><span class="sxs-lookup"><span data-stu-id="32c1b-157">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="32c1b-158">*runtimeconfig.jsw* pliku to plik konfiguracji, który zawiera ustawienia czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="32c1b-158">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="32c1b-159">Aby uzyskać więcej informacji, zobacz [Ustawienia konfiguracji środowiska uruchomieniowego .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="32c1b-159">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="32c1b-160">**`--roll-forward <SETTING>`\*\*\*\*Dostępne począwszy od zestaw .NET Core SDK 3,0.**</span><span class="sxs-lookup"><span data-stu-id="32c1b-160">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="32c1b-161">Kontroluje sposób, w jaki do aplikacji jest stosowane przewinięcie do przodu.</span><span class="sxs-lookup"><span data-stu-id="32c1b-161">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="32c1b-162">`SETTING`Może to być jedna z następujących wartości.</span><span class="sxs-lookup"><span data-stu-id="32c1b-162">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="32c1b-163">Jeśli nie zostanie określony, `Minor` jest wartością domyślną.</span><span class="sxs-lookup"><span data-stu-id="32c1b-163">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="32c1b-164">`LatestPatch` — Przewinięcie do najwyższej wersji poprawki.</span><span class="sxs-lookup"><span data-stu-id="32c1b-164">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="32c1b-165">Spowoduje to wyłączenie wycofywania wersji pomocniczej.</span><span class="sxs-lookup"><span data-stu-id="32c1b-165">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="32c1b-166">`Minor` — Przewinięcie do najmniejszej wyższej wersji pomocniczej, jeśli brakuje wymaganej wersji pomocniczej.</span><span class="sxs-lookup"><span data-stu-id="32c1b-166">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="32c1b-167">Jeśli jest obecna żądana wersja pomocnicza, zostaną użyte zasady LatestPatch.</span><span class="sxs-lookup"><span data-stu-id="32c1b-167">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="32c1b-168">`Major` -Przewinięcie do najmniejszej wyższej wersji głównej i najniższej wersji pomocniczej, jeśli brakuje wersji głównej.</span><span class="sxs-lookup"><span data-stu-id="32c1b-168">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="32c1b-169">Jeśli jest obecna żądana wersja główna, są używane zasady pomocnicze.</span><span class="sxs-lookup"><span data-stu-id="32c1b-169">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="32c1b-170">`LatestMinor` — Przewinięcie do najnowszej wersji pomocniczej, nawet jeśli jest obecna żądana wersja pomocnicza.</span><span class="sxs-lookup"><span data-stu-id="32c1b-170">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="32c1b-171">Przeznaczone do scenariuszy hostingu składników.</span><span class="sxs-lookup"><span data-stu-id="32c1b-171">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="32c1b-172">`LatestMajor` — Przewinięcie do przodu do najwyższej głównej i najwyższej wersji pomocniczej, nawet jeśli zażądano obecności głównej.</span><span class="sxs-lookup"><span data-stu-id="32c1b-172">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="32c1b-173">Przeznaczone do scenariuszy hostingu składników.</span><span class="sxs-lookup"><span data-stu-id="32c1b-173">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="32c1b-174">`Disable` — Nie przetaczaj dalej.</span><span class="sxs-lookup"><span data-stu-id="32c1b-174">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="32c1b-175">Powiąż tylko z określoną wersją.</span><span class="sxs-lookup"><span data-stu-id="32c1b-175">Only bind to specified version.</span></span> <span data-ttu-id="32c1b-176">Te zasady nie są zalecane do użytku ogólnego, ponieważ uniemożliwiają one przekazanie do najnowszych poprawek.</span><span class="sxs-lookup"><span data-stu-id="32c1b-176">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="32c1b-177">Ta wartość jest zalecana tylko do celów testowych.</span><span class="sxs-lookup"><span data-stu-id="32c1b-177">This value is only recommended for testing.</span></span>

  <span data-ttu-id="32c1b-178">Z wyjątkiem programu `Disable` , wszystkie ustawienia będą używać najwyższej dostępnej wersji poprawki.</span><span class="sxs-lookup"><span data-stu-id="32c1b-178">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

  <span data-ttu-id="32c1b-179">Zachowanie przewinięcie do przodu można także skonfigurować we właściwościach pliku projektu, właściwości pliku konfiguracji czasu wykonywania i zmiennej środowiskowej.</span><span class="sxs-lookup"><span data-stu-id="32c1b-179">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="32c1b-180">Aby uzyskać więcej informacji, zobacz [wersja główna środowiska uruchomieniowego do przodu](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span><span class="sxs-lookup"><span data-stu-id="32c1b-180">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

- <span data-ttu-id="32c1b-181">**`--roll-forward-on-no-candidate-fx <N>`\*\*\*\*Dostępne w zestawie SDK platformy .NET Core 2. x.**</span><span class="sxs-lookup"><span data-stu-id="32c1b-181">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="32c1b-182">Definiuje zachowanie, gdy wymagana architektura udostępniona jest niedostępna.</span><span class="sxs-lookup"><span data-stu-id="32c1b-182">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="32c1b-183">`N` może to być:</span><span class="sxs-lookup"><span data-stu-id="32c1b-183">`N` can be:</span></span>

  - <span data-ttu-id="32c1b-184">`0` -Wyłącz parzystą wersję pomocniczą do przodu.</span><span class="sxs-lookup"><span data-stu-id="32c1b-184">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="32c1b-185">`1` — Przewinięcie do wersji pomocniczej, ale nie w wersji głównej.</span><span class="sxs-lookup"><span data-stu-id="32c1b-185">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="32c1b-186">Jest to zachowanie domyślne.</span><span class="sxs-lookup"><span data-stu-id="32c1b-186">This is the default behavior.</span></span>
  - <span data-ttu-id="32c1b-187">`2` — Przewinięcie do przodu w wersjach pomocniczych i głównych.</span><span class="sxs-lookup"><span data-stu-id="32c1b-187">`2` - Roll forward on minor and major versions.</span></span>

  <span data-ttu-id="32c1b-188">Aby uzyskać więcej informacji, zobacz [przewinięcie do przodu](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="32c1b-188">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

  <span data-ttu-id="32c1b-189">Począwszy od platformy .NET Core 3,0, ta opcja jest zastępowana przez `--roll-forward` , a ta opcja powinna być używana zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="32c1b-189">Starting with .NET Core 3.0, this option is superseded by `--roll-forward`, and that option should be used instead.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="32c1b-190">Wersja środowiska uruchomieniowego platformy .NET Core do użycia w celu uruchomienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="32c1b-190">Version of the .NET Core runtime to use to run the application.</span></span>

  <span data-ttu-id="32c1b-191">Ta opcja zastępuje wersję pierwszego odniesienia struktury w `.runtimeconfig.json` pliku aplikacji.</span><span class="sxs-lookup"><span data-stu-id="32c1b-191">This option overrides the version of the first framework reference in the application's `.runtimeconfig.json` file.</span></span> <span data-ttu-id="32c1b-192">Oznacza to, że działa tylko zgodnie z oczekiwaniami, jeśli istnieje tylko jedno odwołanie do struktury.</span><span class="sxs-lookup"><span data-stu-id="32c1b-192">This means it only works as expected if there's just one framework reference.</span></span> <span data-ttu-id="32c1b-193">Jeśli aplikacja ma więcej niż jedno odwołanie do platformy, użycie tej opcji może spowodować błędy.</span><span class="sxs-lookup"><span data-stu-id="32c1b-193">If the application has more than one framework reference, using this option may cause errors.</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="32c1b-194">Polecenia dotnet</span><span class="sxs-lookup"><span data-stu-id="32c1b-194">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="32c1b-195">Ogólne</span><span class="sxs-lookup"><span data-stu-id="32c1b-195">General</span></span>

| <span data-ttu-id="32c1b-196">Polecenie</span><span class="sxs-lookup"><span data-stu-id="32c1b-196">Command</span></span>                                       | <span data-ttu-id="32c1b-197">Funkcja</span><span class="sxs-lookup"><span data-stu-id="32c1b-197">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="32c1b-198">dotnet build</span><span class="sxs-lookup"><span data-stu-id="32c1b-198">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="32c1b-199">Kompiluje aplikację platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="32c1b-199">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="32c1b-200">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="32c1b-200">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="32c1b-201">Współdziała z serwerami uruchomionymi przez kompilację.</span><span class="sxs-lookup"><span data-stu-id="32c1b-201">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="32c1b-202">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="32c1b-202">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="32c1b-203">Czyste dane wyjściowe kompilacji.</span><span class="sxs-lookup"><span data-stu-id="32c1b-203">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="32c1b-204">dotnet help</span><span class="sxs-lookup"><span data-stu-id="32c1b-204">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="32c1b-205">Przedstawia bardziej szczegółową dokumentację dla polecenia w trybie online.</span><span class="sxs-lookup"><span data-stu-id="32c1b-205">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="32c1b-206">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="32c1b-206">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="32c1b-207">Migruje prawidłowy projekt w wersji zapoznawczej 2 do projektu zestaw .NET Core SDK 1,0.</span><span class="sxs-lookup"><span data-stu-id="32c1b-207">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="32c1b-208">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="32c1b-208">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="32c1b-209">Zapewnia dostęp do wiersza polecenia programu MSBuild.</span><span class="sxs-lookup"><span data-stu-id="32c1b-209">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="32c1b-210">dotnet new</span><span class="sxs-lookup"><span data-stu-id="32c1b-210">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="32c1b-211">Inicjuje projekt C# lub F # dla danego szablonu.</span><span class="sxs-lookup"><span data-stu-id="32c1b-211">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="32c1b-212">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="32c1b-212">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="32c1b-213">Tworzy pakiet NuGet kodu.</span><span class="sxs-lookup"><span data-stu-id="32c1b-213">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="32c1b-214">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="32c1b-214">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="32c1b-215">Publikuje zależne od programu .NET Framework lub samodzielną aplikację.</span><span class="sxs-lookup"><span data-stu-id="32c1b-215">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="32c1b-216">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="32c1b-216">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="32c1b-217">Przywraca zależności dla danej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="32c1b-217">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="32c1b-218">dotnet run</span><span class="sxs-lookup"><span data-stu-id="32c1b-218">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="32c1b-219">Uruchamia aplikację ze źródła.</span><span class="sxs-lookup"><span data-stu-id="32c1b-219">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="32c1b-220">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="32c1b-220">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="32c1b-221">Opcje dodawania, usuwania i wyświetlania listy projektów w pliku rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="32c1b-221">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="32c1b-222">dotnet store</span><span class="sxs-lookup"><span data-stu-id="32c1b-222">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="32c1b-223">Przechowuje zestawy w magazynie pakietów środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="32c1b-223">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="32c1b-224">dotnet test</span><span class="sxs-lookup"><span data-stu-id="32c1b-224">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="32c1b-225">Uruchamia testy przy użyciu modułu uruchamiającego testy.</span><span class="sxs-lookup"><span data-stu-id="32c1b-225">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="32c1b-226">Odwołania projektu</span><span class="sxs-lookup"><span data-stu-id="32c1b-226">Project references</span></span>

<span data-ttu-id="32c1b-227">Polecenie</span><span class="sxs-lookup"><span data-stu-id="32c1b-227">Command</span></span> | <span data-ttu-id="32c1b-228">Funkcja</span><span class="sxs-lookup"><span data-stu-id="32c1b-228">Function</span></span>
--- | ---
[<span data-ttu-id="32c1b-229">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="32c1b-229">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="32c1b-230">Dodaje odwołanie do projektu.</span><span class="sxs-lookup"><span data-stu-id="32c1b-230">Adds a project reference.</span></span>
[<span data-ttu-id="32c1b-231">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="32c1b-231">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="32c1b-232">Wyświetla listę odwołań do projektu.</span><span class="sxs-lookup"><span data-stu-id="32c1b-232">Lists project references.</span></span>
[<span data-ttu-id="32c1b-233">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="32c1b-233">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="32c1b-234">Usuwa odwołanie do projektu.</span><span class="sxs-lookup"><span data-stu-id="32c1b-234">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="32c1b-235">Pakiety NuGet</span><span class="sxs-lookup"><span data-stu-id="32c1b-235">NuGet packages</span></span>

<span data-ttu-id="32c1b-236">Polecenie</span><span class="sxs-lookup"><span data-stu-id="32c1b-236">Command</span></span> | <span data-ttu-id="32c1b-237">Funkcja</span><span class="sxs-lookup"><span data-stu-id="32c1b-237">Function</span></span>
--- | ---
[<span data-ttu-id="32c1b-238">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="32c1b-238">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="32c1b-239">Dodaje pakiet NuGet.</span><span class="sxs-lookup"><span data-stu-id="32c1b-239">Adds a NuGet package.</span></span>
[<span data-ttu-id="32c1b-240">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="32c1b-240">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="32c1b-241">Usuwa pakiet NuGet.</span><span class="sxs-lookup"><span data-stu-id="32c1b-241">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="32c1b-242">Polecenia NuGet</span><span class="sxs-lookup"><span data-stu-id="32c1b-242">NuGet commands</span></span>

<span data-ttu-id="32c1b-243">Polecenie</span><span class="sxs-lookup"><span data-stu-id="32c1b-243">Command</span></span> | <span data-ttu-id="32c1b-244">Funkcja</span><span class="sxs-lookup"><span data-stu-id="32c1b-244">Function</span></span>
--- | ---
[<span data-ttu-id="32c1b-245">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="32c1b-245">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="32c1b-246">Usuwa pakiet z serwera lub go wystawia.</span><span class="sxs-lookup"><span data-stu-id="32c1b-246">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="32c1b-247">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="32c1b-247">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="32c1b-248">Wypchnij pakiet na serwer i opublikuje go.</span><span class="sxs-lookup"><span data-stu-id="32c1b-248">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="32c1b-249">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="32c1b-249">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="32c1b-250">Czyści lub wyświetla lokalne zasoby NuGet, takie jak pamięć podręczna żądań HTTP, tymczasowa pamięć podręczna lub folder pakietów globalnych dla całego komputera.</span><span class="sxs-lookup"><span data-stu-id="32c1b-250">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="32c1b-251">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="32c1b-251">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="32c1b-252">Dodaje źródło NuGet.</span><span class="sxs-lookup"><span data-stu-id="32c1b-252">Adds a NuGet source.</span></span>
[<span data-ttu-id="32c1b-253">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="32c1b-253">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="32c1b-254">Wyłącza Źródło NuGet.</span><span class="sxs-lookup"><span data-stu-id="32c1b-254">Disables a NuGet source.</span></span>
[<span data-ttu-id="32c1b-255">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="32c1b-255">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="32c1b-256">Włącza Źródło NuGet.</span><span class="sxs-lookup"><span data-stu-id="32c1b-256">Enables a NuGet source.</span></span>
[<span data-ttu-id="32c1b-257">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="32c1b-257">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="32c1b-258">Wyświetla wszystkie skonfigurowane źródła NuGet.</span><span class="sxs-lookup"><span data-stu-id="32c1b-258">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="32c1b-259">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="32c1b-259">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="32c1b-260">Usuwa źródło NuGet.</span><span class="sxs-lookup"><span data-stu-id="32c1b-260">Removes a NuGet source.</span></span>
[<span data-ttu-id="32c1b-261">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="32c1b-261">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="32c1b-262">Aktualizuje źródło narzędzia NuGet.</span><span class="sxs-lookup"><span data-stu-id="32c1b-262">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="32c1b-263">Globalne, ścieżki narzędziowe i polecenia narzędzi lokalnych</span><span class="sxs-lookup"><span data-stu-id="32c1b-263">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="32c1b-264">Narzędzia są aplikacjami konsolowymi, które są instalowane z pakietów NuGet i są wywoływane z wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="32c1b-264">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="32c1b-265">Narzędzia można pisać samodzielnie lub instalować Narzędzia zapisane przez inne firmy.</span><span class="sxs-lookup"><span data-stu-id="32c1b-265">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="32c1b-266">Narzędzia są również nazywane narzędziami globalnymi, narzędziami ścieżki narzędzi i narzędziami lokalnymi.</span><span class="sxs-lookup"><span data-stu-id="32c1b-266">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="32c1b-267">Aby uzyskać więcej informacji, zobacz [Narzędzia platformy .NET Core — Omówienie](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="32c1b-267">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="32c1b-268">Narzędzia globalne i ścieżki narzędzi są dostępne począwszy od zestaw .NET Core SDK 2,1.</span><span class="sxs-lookup"><span data-stu-id="32c1b-268">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="32c1b-269">Narzędzia lokalne są dostępne począwszy od zestaw .NET Core SDK 3,0.</span><span class="sxs-lookup"><span data-stu-id="32c1b-269">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="32c1b-270">Polecenie</span><span class="sxs-lookup"><span data-stu-id="32c1b-270">Command</span></span> | <span data-ttu-id="32c1b-271">Funkcja</span><span class="sxs-lookup"><span data-stu-id="32c1b-271">Function</span></span>
--- | ---
[<span data-ttu-id="32c1b-272">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="32c1b-272">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="32c1b-273">Instaluje narzędzie na komputerze.</span><span class="sxs-lookup"><span data-stu-id="32c1b-273">Installs a tool on your machine.</span></span>
[<span data-ttu-id="32c1b-274">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="32c1b-274">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="32c1b-275">Wyświetla listę wszystkich globalnych narzędzi, ścieżek narzędziowych lub lokalnych zainstalowanych obecnie na komputerze.</span><span class="sxs-lookup"><span data-stu-id="32c1b-275">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="32c1b-276">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="32c1b-276">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="32c1b-277">Odinstalowuje narzędzie z komputera.</span><span class="sxs-lookup"><span data-stu-id="32c1b-277">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="32c1b-278">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="32c1b-278">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="32c1b-279">Aktualizuje narzędzie zainstalowane na komputerze.</span><span class="sxs-lookup"><span data-stu-id="32c1b-279">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="32c1b-280">Dodatkowe narzędzia</span><span class="sxs-lookup"><span data-stu-id="32c1b-280">Additional tools</span></span>

<span data-ttu-id="32c1b-281">Począwszy od zestaw .NET Core SDK 2.1.300, wiele narzędzi, które były dostępne tylko dla każdego projektu, przy użyciu, `DotnetCliToolReference` jest teraz dostępne jako część zestaw .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="32c1b-281">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="32c1b-282">Te narzędzia są wymienione w poniższej tabeli:</span><span class="sxs-lookup"><span data-stu-id="32c1b-282">These tools are listed in the following table:</span></span>

| <span data-ttu-id="32c1b-283">Narzędzie</span><span class="sxs-lookup"><span data-stu-id="32c1b-283">Tool</span></span>                                              | <span data-ttu-id="32c1b-284">Funkcja</span><span class="sxs-lookup"><span data-stu-id="32c1b-284">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="32c1b-285">dev-certs</span><span class="sxs-lookup"><span data-stu-id="32c1b-285">dev-certs</span></span>                                         | <span data-ttu-id="32c1b-286">Tworzy i zarządza certyfikatami deweloperskimi.</span><span class="sxs-lookup"><span data-stu-id="32c1b-286">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="32c1b-287">bieżąco</span><span class="sxs-lookup"><span data-stu-id="32c1b-287">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="32c1b-288">Entity Framework Core narzędzia wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="32c1b-288">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="32c1b-289">SQL-pamięć podręczna</span><span class="sxs-lookup"><span data-stu-id="32c1b-289">sql-cache</span></span>                                         | <span data-ttu-id="32c1b-290">SQL Server narzędzia wiersza polecenia pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="32c1b-290">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="32c1b-291">wpisy tajne użytkownika</span><span class="sxs-lookup"><span data-stu-id="32c1b-291">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="32c1b-292">Zarządza kluczami tajnymi użytkowników deweloperskich.</span><span class="sxs-lookup"><span data-stu-id="32c1b-292">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="32c1b-293">Obejrzyj</span><span class="sxs-lookup"><span data-stu-id="32c1b-293">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="32c1b-294">Uruchamia obserwatora plików, który uruchamia polecenie, gdy pliki zmienią się.</span><span class="sxs-lookup"><span data-stu-id="32c1b-294">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="32c1b-295">Aby uzyskać więcej informacji na temat każdego narzędzia, wpisz `dotnet <tool-name> --help` .</span><span class="sxs-lookup"><span data-stu-id="32c1b-295">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="32c1b-296">Przykłady</span><span class="sxs-lookup"><span data-stu-id="32c1b-296">Examples</span></span>

<span data-ttu-id="32c1b-297">Utwórz nową aplikację konsolową platformy .NET Core:</span><span class="sxs-lookup"><span data-stu-id="32c1b-297">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="32c1b-298">Kompiluj projekt i jego zależności w danym katalogu:</span><span class="sxs-lookup"><span data-stu-id="32c1b-298">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="32c1b-299">Uruchom aplikację:</span><span class="sxs-lookup"><span data-stu-id="32c1b-299">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="32c1b-300">Zmienne środowiskowe</span><span class="sxs-lookup"><span data-stu-id="32c1b-300">Environment variables</span></span>

- <span data-ttu-id="32c1b-301">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="32c1b-301">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="32c1b-302">Określa lokalizację środowiska uruchomieniowego programu .NET Core, jeśli nie są one zainstalowane w domyślnej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="32c1b-302">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="32c1b-303">Domyślna lokalizacja w systemie Windows to `C:\Program Files\dotnet` .</span><span class="sxs-lookup"><span data-stu-id="32c1b-303">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="32c1b-304">Domyślną lokalizacją w systemie Linux i macOS jest `/usr/share/dotnet` .</span><span class="sxs-lookup"><span data-stu-id="32c1b-304">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="32c1b-305">Ta zmienna środowiskowa jest używana tylko w przypadku uruchamiania aplikacji za pośrednictwem wygenerowanych plików wykonywalnych (apphosts).</span><span class="sxs-lookup"><span data-stu-id="32c1b-305">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="32c1b-306">`DOTNET_ROOT(x86)` jest używany zamiast w przypadku uruchamiania 32-bitowego pliku wykonywalnego w 64-bitowym systemie operacyjnym.</span><span class="sxs-lookup"><span data-stu-id="32c1b-306">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `NUGET_PACKAGES`

  <span data-ttu-id="32c1b-307">Folder pakiety globalne.</span><span class="sxs-lookup"><span data-stu-id="32c1b-307">The global packages folder.</span></span> <span data-ttu-id="32c1b-308">Jeśli nie jest ustawiona, zostanie ona domyślnie `~/.nuget/packages` włączona w systemie UNIX lub `%userprofile%\.nuget\packages` w systemie Windows.</span><span class="sxs-lookup"><span data-stu-id="32c1b-308">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="32c1b-309">Określa lokalizację indeksu obsługi, który ma być używany przez host udostępniony podczas ładowania środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="32c1b-309">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="32c1b-310">Określa, czy podczas pierwszego uruchomienia są wyświetlane komunikaty telemetryczne programu .NET Core i telemetrii.</span><span class="sxs-lookup"><span data-stu-id="32c1b-310">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="32c1b-311">Ustaw, aby `true` wyciszyć te komunikaty (wartości `true` , `1` lub `yes` zaakceptować) lub ustawić na wartość `false` Zezwalaj (wartości `false` , `0` lub `no` zaakceptować).</span><span class="sxs-lookup"><span data-stu-id="32c1b-311">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="32c1b-312">Jeśli nie zostanie ustawiona, wartość domyślna to, `false` a komunikaty będą wyświetlane po pierwszym uruchomieniu.</span><span class="sxs-lookup"><span data-stu-id="32c1b-312">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="32c1b-313">Ta flaga nie ma wpływu na dane telemetryczne (Zobacz, `DOTNET_CLI_TELEMETRY_OPTOUT` Aby zrezygnować z wysyłania danych telemetrycznych).</span><span class="sxs-lookup"><span data-stu-id="32c1b-313">This flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="32c1b-314">Określa, czy dane dotyczące użycia narzędzi .NET Core są zbierane i wysyłane do firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="32c1b-314">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="32c1b-315">Ustaw `true` , aby zrezygnować z funkcji telemetrii (wartości `true` , `1` lub `yes` zaakceptować).</span><span class="sxs-lookup"><span data-stu-id="32c1b-315">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="32c1b-316">W przeciwnym razie ustaw opcję, aby `false` można było wybrać funkcje telemetrii (wartości `false` , `0` lub `no` zaakceptowane).</span><span class="sxs-lookup"><span data-stu-id="32c1b-316">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="32c1b-317">Jeśli nie zostanie ustawiona, wartość domyślna to `false` i aktywna funkcja telemetrii.</span><span class="sxs-lookup"><span data-stu-id="32c1b-317">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="32c1b-318">Określa, czy środowisko uruchomieniowe programu .NET Core, udostępnione środowisko lub zestaw SDK są rozpoznawane z lokalizacji globalnej.</span><span class="sxs-lookup"><span data-stu-id="32c1b-318">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="32c1b-319">Jeśli nie zostanie ustawiona, wartość domyślna to 1 (logiczna `true` ).</span><span class="sxs-lookup"><span data-stu-id="32c1b-319">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="32c1b-320">Ustawienie wartości 0 (logiczne `false` ) nie jest rozpoznawane z lokalizacji globalnej i ma wyizolowane instalacje .NET Core.</span><span class="sxs-lookup"><span data-stu-id="32c1b-320">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="32c1b-321">Aby uzyskać więcej informacji o wyszukiwaniu wielu poziomów, zobacz [SharedFX wyszukiwanie na wielu poziomach](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="32c1b-321">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="32c1b-322">`DOTNET_ROLL_FORWARD`**Dostępne począwszy od platformy .NET Core 3. x.**</span><span class="sxs-lookup"><span data-stu-id="32c1b-322">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x.**</span></span>

  <span data-ttu-id="32c1b-323">Określa zachowanie funkcji przyciągania do przodu.</span><span class="sxs-lookup"><span data-stu-id="32c1b-323">Determines roll forward behavior.</span></span> <span data-ttu-id="32c1b-324">Aby uzyskać więcej informacji, zobacz `--roll-forward` opcję wcześniejszą w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="32c1b-324">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="32c1b-325">`DOTNET_ROLL_FORWARD_TO_PRERELEASE`**Dostępne począwszy od platformy .NET Core 3. x.**</span><span class="sxs-lookup"><span data-stu-id="32c1b-325">`DOTNET_ROLL_FORWARD_TO_PRERELEASE` **Available starting with .NET Core 3.x.**</span></span>

  <span data-ttu-id="32c1b-326">Jeśli jest ustawiona na `1` (Enabled), umożliwia przewracanie do wersji wstępnej z wersji Release.</span><span class="sxs-lookup"><span data-stu-id="32c1b-326">If set to `1` (enabled), enables rolling forward to a pre-release version from a release version.</span></span> <span data-ttu-id="32c1b-327">Domyślnie ( `0` -Disabled), gdy wymagana jest wydana wersja środowiska uruchomieniowego programu .NET Core, przewinięcie do przodu spowoduje uwzględnienie tylko zainstalowanych wersji.</span><span class="sxs-lookup"><span data-stu-id="32c1b-327">By default (`0` - disabled), when a release version of .NET Core runtime is requested, roll-forward will only consider installed release versions.</span></span>

  <span data-ttu-id="32c1b-328">Aby uzyskać więcej informacji, zobacz [przewinięcie do przodu](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span><span class="sxs-lookup"><span data-stu-id="32c1b-328">For more information, see [Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

- <span data-ttu-id="32c1b-329">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`**Dostępne w programie .NET Core 2. x.**</span><span class="sxs-lookup"><span data-stu-id="32c1b-329">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x.**</span></span>

  <span data-ttu-id="32c1b-330">Wyłącza dodatkową wersję do przodu, jeśli jest ustawiona na `0` .</span><span class="sxs-lookup"><span data-stu-id="32c1b-330">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="32c1b-331">Aby uzyskać więcej informacji, zobacz [przewinięcie do przodu](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="32c1b-331">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

  <span data-ttu-id="32c1b-332">To ustawienie jest zastępowane w programie .NET Core 3,0 przez program `DOTNET_ROLL_FORWARD` .</span><span class="sxs-lookup"><span data-stu-id="32c1b-332">This setting is superseded in .NET Core 3.0 by `DOTNET_ROLL_FORWARD`.</span></span> <span data-ttu-id="32c1b-333">Zamiast tego należy użyć nowych ustawień.</span><span class="sxs-lookup"><span data-stu-id="32c1b-333">The new settings should be used instead.</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="32c1b-334">Ustawia język interfejsu użytkownika CLI przy użyciu wartości ustawień regionalnych, takich jak `en-us` .</span><span class="sxs-lookup"><span data-stu-id="32c1b-334">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="32c1b-335">Obsługiwane wartości są takie same jak w przypadku programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="32c1b-335">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="32c1b-336">Aby uzyskać więcej informacji, zobacz sekcję dotyczącą zmiany języka Instalatora w [dokumentacji instalacyjnej programu Visual Studio](/visualstudio/install/install-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="32c1b-336">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="32c1b-337">Reguły Menedżera zasobów platformy .NET mają zastosowanie, więc nie trzeba wybierać dokładnego dopasowania, &mdash; które można również wybrać w `CultureInfo` drzewie.</span><span class="sxs-lookup"><span data-stu-id="32c1b-337">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="32c1b-338">Jeśli na przykład ustawisz ją na `fr-CA` , interfejs wiersza polecenia znajdzie i użyje `fr` tłumaczeń.</span><span class="sxs-lookup"><span data-stu-id="32c1b-338">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="32c1b-339">Jeśli ustawisz go na język, który nie jest obsługiwany, interfejs wiersza polecenia powróci do języka angielskiego.</span><span class="sxs-lookup"><span data-stu-id="32c1b-339">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="32c1b-340">W przypadku plików wykonywalnych z obsługą graficznego interfejsu użytkownika — wyłącza okno podręczne, które jest zwykle wyświetlane dla niektórych klas błędów.</span><span class="sxs-lookup"><span data-stu-id="32c1b-340">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="32c1b-341">Tylko zapisuje `stderr` i opuszcza te przypadki.</span><span class="sxs-lookup"><span data-stu-id="32c1b-341">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="32c1b-342">Odpowiednik opcji interfejsu wiersza polecenia `--additional-deps` .</span><span class="sxs-lookup"><span data-stu-id="32c1b-342">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="32c1b-343">Zastępuje wykrytego identyfikatora RID.</span><span class="sxs-lookup"><span data-stu-id="32c1b-343">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="32c1b-344">Lokalizacja "udostępnionego magazynu", do którego w niektórych przypadkach jest powracana rozdzielczość zestawu.</span><span class="sxs-lookup"><span data-stu-id="32c1b-344">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="32c1b-345">Lista zestawów, z których mają zostać załadowane i wykonane uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="32c1b-345">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="32c1b-346">`DOTNET_BUNDLE_EXTRACT_BASE_DIR`**Dostępne począwszy od platformy .NET Core 3. x.**</span><span class="sxs-lookup"><span data-stu-id="32c1b-346">`DOTNET_BUNDLE_EXTRACT_BASE_DIR` **Available starting with .NET Core 3.x.**</span></span>

  <span data-ttu-id="32c1b-347">Określa katalog, do którego zostanie wyodrębniona aplikacja Jednoplikowa przed wykonaniem.</span><span class="sxs-lookup"><span data-stu-id="32c1b-347">Specifies a directory to which a single-file application is extracted before it is executed.</span></span>

  <span data-ttu-id="32c1b-348">Aby uzyskać więcej informacji, zobacz [pliki wykonywalne pojedynczego pliku](../whats-new/dotnet-core-3-0.md#single-file-executables).</span><span class="sxs-lookup"><span data-stu-id="32c1b-348">For more information, see [Single-file executables](../whats-new/dotnet-core-3-0.md#single-file-executables).</span></span>

- <span data-ttu-id="32c1b-349">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="32c1b-349">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="32c1b-350">Steruje śledzeniem diagnostyki ze składników hostingowych, takich jak `dotnet.exe` , `hostfxr` , i `hostpolicy` .</span><span class="sxs-lookup"><span data-stu-id="32c1b-350">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

  * <span data-ttu-id="32c1b-351">`COREHOST_TRACE=[0/1]` -Domyślnie `0` — śledzenie jest wyłączone.</span><span class="sxs-lookup"><span data-stu-id="32c1b-351">`COREHOST_TRACE=[0/1]` - default is `0` - tracing disabled.</span></span> <span data-ttu-id="32c1b-352">Jeśli jest ustawiona na `1` , śledzenie diagnostyki jest włączone.</span><span class="sxs-lookup"><span data-stu-id="32c1b-352">If set to `1`, diagnostics tracing is enabled.</span></span>
  * <span data-ttu-id="32c1b-353">`COREHOST_TRACEFILE=<file path>` -działa tylko wtedy, gdy śledzenie jest włączone za pośrednictwem `COREHOST_TRACE=1` .</span><span class="sxs-lookup"><span data-stu-id="32c1b-353">`COREHOST_TRACEFILE=<file path>` - only has effect if tracing is enabled via `COREHOST_TRACE=1`.</span></span> <span data-ttu-id="32c1b-354">Po ustawieniu informacje o śledzeniu są zapisywane w określonym pliku, w przeciwnym razie informacje o śledzeniu są zapisywane w `stderr` .</span><span class="sxs-lookup"><span data-stu-id="32c1b-354">When set, the tracing information is written to the specified file, otherwise the tracing information is written to `stderr`.</span></span> <span data-ttu-id="32c1b-355">**Dostępne począwszy od platformy .NET Core 3. x.**</span><span class="sxs-lookup"><span data-stu-id="32c1b-355">**Available starting with .NET Core 3.x.**</span></span>
  * <span data-ttu-id="32c1b-356">`COREHOST_TRACE_VERBOSITY=[1/2/3/4]` -wartość domyślna to `4` .</span><span class="sxs-lookup"><span data-stu-id="32c1b-356">`COREHOST_TRACE_VERBOSITY=[1/2/3/4]` - default is `4`.</span></span> <span data-ttu-id="32c1b-357">To ustawienie jest używane tylko wtedy, gdy śledzenie jest włączone za pośrednictwem `COREHOST_TRACE=1` .</span><span class="sxs-lookup"><span data-stu-id="32c1b-357">The setting is used only when tracing is enabled via `COREHOST_TRACE=1`.</span></span> <span data-ttu-id="32c1b-358">**Dostępne począwszy od platformy .NET Core 3. x.**</span><span class="sxs-lookup"><span data-stu-id="32c1b-358">**Available starting with .NET Core 3.x.**</span></span>
    * <span data-ttu-id="32c1b-359">`4` — wszystkie informacje o śledzeniu są zapisywane</span><span class="sxs-lookup"><span data-stu-id="32c1b-359">`4` - all tracing information is written</span></span>
    * <span data-ttu-id="32c1b-360">`3` -tylko komunikaty informacyjne, ostrzegawcze i błędów są zapisywane</span><span class="sxs-lookup"><span data-stu-id="32c1b-360">`3` - only informational, warning and error messages are written</span></span>
    * <span data-ttu-id="32c1b-361">`2` -tylko ostrzeżenia i komunikaty o błędach są zapisywane</span><span class="sxs-lookup"><span data-stu-id="32c1b-361">`2` - only warning and error messages are written</span></span>
    * <span data-ttu-id="32c1b-362">`1` tylko komunikaty o błędach są zapisywane</span><span class="sxs-lookup"><span data-stu-id="32c1b-362">`1` - only error messages are written</span></span>

  <span data-ttu-id="32c1b-363">Typowym sposobem uzyskania szczegółowych informacji śledzenia dotyczących uruchamiania aplikacji jest ustawienie `COREHOST_TRACE=1` i `COREHOST_TRACEFILE=host_trace.txt` uruchomienie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="32c1b-363">The typical way to get detailed trace information about application startup is to set `COREHOST_TRACE=1` and `COREHOST_TRACEFILE=host_trace.txt` and then run the application.</span></span> <span data-ttu-id="32c1b-364">Nowy plik `host_trace.txt` zostanie utworzony w bieżącym katalogu ze szczegółowymi informacjami.</span><span class="sxs-lookup"><span data-stu-id="32c1b-364">A new file `host_trace.txt` will be created in the current directory with the detailed information.</span></span>

## <a name="see-also"></a><span data-ttu-id="32c1b-365">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="32c1b-365">See also</span></span>

- [<span data-ttu-id="32c1b-366">Pliki konfiguracji środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="32c1b-366">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="32c1b-367">Ustawienia konfiguracji środowiska uruchomieniowego .NET Core</span><span class="sxs-lookup"><span data-stu-id="32c1b-367">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
