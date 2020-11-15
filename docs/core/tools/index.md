---
title: INTERFEJS WIERSZA POLECENIA PLATFORMY .NET
titleSuffix: ''
description: Przegląd interfejsu wiersza polecenia platformy .NET i jego funkcji.
ms.topic: overview
ms.date: 02/13/2020
ms.openlocfilehash: 6a12e2d16afe36092c10e14a7465fa3bdbb23f32
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94633859"
---
# <a name="net-cli-overview"></a><span data-ttu-id="fc604-103">Interfejs wiersza polecenia platformy .NET — Omówienie</span><span class="sxs-lookup"><span data-stu-id="fc604-103">.NET CLI overview</span></span>

<span data-ttu-id="fc604-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,1 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="fc604-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="fc604-105">Interfejs wiersza polecenia (CLI) platformy .NET to Międzyplatformowy łańcucha narzędzi służący do tworzenia, tworzenia, uruchamiania i publikowania aplikacji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="fc604-105">The .NET command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET applications.</span></span>

<span data-ttu-id="fc604-106">Interfejs wiersza polecenia platformy .NET jest dołączony do [zestawu .NET SDK](../sdk.md).</span><span class="sxs-lookup"><span data-stu-id="fc604-106">The .NET CLI is included with the [.NET SDK](../sdk.md).</span></span> <span data-ttu-id="fc604-107">Aby dowiedzieć się, jak zainstalować zestaw SDK dla platformy .NET, zobacz [Instalowanie programu .NET Core](../install/windows.md).</span><span class="sxs-lookup"><span data-stu-id="fc604-107">To learn how to install the .NET SDK, see [Install .NET Core](../install/windows.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="fc604-108">Polecenia interfejsu wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="fc604-108">CLI commands</span></span>

<span data-ttu-id="fc604-109">Następujące polecenia są instalowane domyślnie:</span><span class="sxs-lookup"><span data-stu-id="fc604-109">The following commands are installed by default:</span></span>

### <a name="basic-commands"></a><span data-ttu-id="fc604-110">Polecenia podstawowe</span><span class="sxs-lookup"><span data-stu-id="fc604-110">Basic commands</span></span>

- [`new`](dotnet-new.md)
- [`restore`](dotnet-restore.md)
- [`build`](dotnet-build.md)
- [`publish`](dotnet-publish.md)
- [`run`](dotnet-run.md)
- [`test`](dotnet-test.md)
- [`vstest`](dotnet-vstest.md)
- [`pack`](dotnet-pack.md)
- [`migrate`](dotnet-migrate.md)
- [`clean`](dotnet-clean.md)
- [`sln`](dotnet-sln.md)
- [`help`](dotnet-help.md)
- [`store`](dotnet-store.md)

### <a name="project-modification-commands"></a><span data-ttu-id="fc604-111">Polecenia modyfikacji projektu</span><span class="sxs-lookup"><span data-stu-id="fc604-111">Project modification commands</span></span>

- [`add package`](dotnet-add-package.md)
- [`add reference`](dotnet-add-reference.md)
- [`remove package`](dotnet-remove-package.md)
- [`remove reference`](dotnet-remove-reference.md)
- [`list reference`](dotnet-list-reference.md)

### <a name="advanced-commands"></a><span data-ttu-id="fc604-112">Polecenia Zaawansowane</span><span class="sxs-lookup"><span data-stu-id="fc604-112">Advanced commands</span></span>

- [`nuget delete`](dotnet-nuget-delete.md)
- [`nuget locals`](dotnet-nuget-locals.md)
- [`nuget push`](dotnet-nuget-push.md)
- [`msbuild`](dotnet-msbuild.md)
- [`dotnet install script`](dotnet-install-script.md)

### <a name="tool-management-commands"></a><span data-ttu-id="fc604-113">Polecenia zarządzania narzędziami</span><span class="sxs-lookup"><span data-stu-id="fc604-113">Tool management commands</span></span>

- [`tool install`](dotnet-tool-install.md)
- [`tool list`](dotnet-tool-list.md)
- [`tool update`](dotnet-tool-update.md)
- <span data-ttu-id="fc604-114">[`tool restore`](global-tools.md#install-a-local-tool) Dostępne od zestaw .NET Core SDK 3,0.</span><span class="sxs-lookup"><span data-stu-id="fc604-114">[`tool restore`](global-tools.md#install-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- <span data-ttu-id="fc604-115">[`tool run`](global-tools.md#invoke-a-local-tool) Dostępne od zestaw .NET Core SDK 3,0.</span><span class="sxs-lookup"><span data-stu-id="fc604-115">[`tool run`](global-tools.md#invoke-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- [`tool uninstall`](dotnet-tool-uninstall.md)

<span data-ttu-id="fc604-116">Narzędzia są aplikacjami konsolowymi, które są instalowane z pakietów NuGet i są wywoływane z wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="fc604-116">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="fc604-117">Narzędzia można pisać samodzielnie lub instalować Narzędzia zapisane przez inne firmy.</span><span class="sxs-lookup"><span data-stu-id="fc604-117">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="fc604-118">Narzędzia są również nazywane narzędziami globalnymi, narzędziami ścieżki narzędzi i narzędziami lokalnymi.</span><span class="sxs-lookup"><span data-stu-id="fc604-118">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="fc604-119">Aby uzyskać więcej informacji, zobacz [Omówienie narzędzi platformy .NET](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fc604-119">For more information, see [.NET tools overview](global-tools.md).</span></span>

## <a name="command-structure"></a><span data-ttu-id="fc604-120">Struktura poleceń</span><span class="sxs-lookup"><span data-stu-id="fc604-120">Command structure</span></span>

<span data-ttu-id="fc604-121">Struktura poleceń interfejsu wiersza polecenia składa się ze [sterownika ("dotnet")](#driver), [polecenia](#command)oraz możliwych [argumentów](#arguments) i [opcji](#options)polecenia.</span><span class="sxs-lookup"><span data-stu-id="fc604-121">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="fc604-122">Ten wzorzec jest widoczny w większości operacji interfejsu wiersza polecenia, takich jak tworzenie nowej aplikacji konsolowej i uruchamianie jej z poziomu wiersza poleceń, ponieważ następujące polecenia pokazują, że są wykonywane z katalogu o nazwie *my_app* :</span><span class="sxs-lookup"><span data-stu-id="fc604-122">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app* :</span></span>

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a><span data-ttu-id="fc604-123">Sterownik</span><span class="sxs-lookup"><span data-stu-id="fc604-123">Driver</span></span>

<span data-ttu-id="fc604-124">Sterownik nosi nazwę [dotnet](dotnet.md) i ma dwie obowiązki, uruchamiają [aplikację zależną od platformy](../deploying/index.md) lub wykonując polecenie.</span><span class="sxs-lookup"><span data-stu-id="fc604-124">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span>

<span data-ttu-id="fc604-125">Aby uruchomić aplikację zależną od platformy, należy określić aplikację po stronie sterownika, na przykład `dotnet /path/to/my_app.dll` .</span><span class="sxs-lookup"><span data-stu-id="fc604-125">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="fc604-126">Gdy wykonujesz polecenie z folderu, w którym znajduje się biblioteka DLL aplikacji, po prostu wykonaj `dotnet my_app.dll` .</span><span class="sxs-lookup"><span data-stu-id="fc604-126">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="fc604-127">Jeśli chcesz użyć określonej wersji środowiska uruchomieniowego .NET, użyj `--fx-version <VERSION>` opcji (zobacz informacje dotyczące [polecenia dotnet](dotnet.md) ).</span><span class="sxs-lookup"><span data-stu-id="fc604-127">If you want to use a specific version of the .NET Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="fc604-128">Po podaniu polecenia do sterownika program `dotnet.exe` uruchamia proces wykonywania poleceń interfejsu wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="fc604-128">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="fc604-129">Przykład:</span><span class="sxs-lookup"><span data-stu-id="fc604-129">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="fc604-130">Najpierw sterownik Określa wersję zestawu SDK do użycia.</span><span class="sxs-lookup"><span data-stu-id="fc604-130">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="fc604-131">Jeśli nie ma [global.jsw](global-json.md) pliku, używana jest Najnowsza wersja zestawu SDK.</span><span class="sxs-lookup"><span data-stu-id="fc604-131">If there is no [global.json](global-json.md) file, the latest version of the SDK available is used.</span></span> <span data-ttu-id="fc604-132">Może to być wersja zapoznawcza lub stabilna, w zależności od tego, co jest najnowsze na komputerze.</span><span class="sxs-lookup"><span data-stu-id="fc604-132">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="fc604-133">Po ustaleniu wersji zestawu SDK wykonuje polecenie.</span><span class="sxs-lookup"><span data-stu-id="fc604-133">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="fc604-134">Polecenie</span><span class="sxs-lookup"><span data-stu-id="fc604-134">Command</span></span>

<span data-ttu-id="fc604-135">Polecenie wykonuje akcję.</span><span class="sxs-lookup"><span data-stu-id="fc604-135">The command performs an action.</span></span> <span data-ttu-id="fc604-136">Na przykład `dotnet build` kompiluje kod.</span><span class="sxs-lookup"><span data-stu-id="fc604-136">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="fc604-137">`dotnet publish` publikuje kod.</span><span class="sxs-lookup"><span data-stu-id="fc604-137">`dotnet publish` publishes code.</span></span> <span data-ttu-id="fc604-138">Polecenia są implementowane jako Aplikacja konsolowa przy użyciu `dotnet {command}` Konwencji.</span><span class="sxs-lookup"><span data-stu-id="fc604-138">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="fc604-139">Argumenty</span><span class="sxs-lookup"><span data-stu-id="fc604-139">Arguments</span></span>

<span data-ttu-id="fc604-140">Argumenty przekazywane do wiersza polecenia są argumentami wywoływanego polecenia.</span><span class="sxs-lookup"><span data-stu-id="fc604-140">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="fc604-141">Na przykład po wykonaniu `dotnet publish my_app.csproj` `my_app.csproj` argument wskazuje projekt do opublikowania i jest przesyłany do `publish` polecenia.</span><span class="sxs-lookup"><span data-stu-id="fc604-141">For example, when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="fc604-142">Opcje</span><span class="sxs-lookup"><span data-stu-id="fc604-142">Options</span></span>

<span data-ttu-id="fc604-143">Opcje, które są przekazywane w wierszu polecenia są opcje wywoływanego polecenia.</span><span class="sxs-lookup"><span data-stu-id="fc604-143">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="fc604-144">Na przykład po wykonaniu `dotnet publish --output /build_output` `--output` opcji i jej wartości są przesyłane do `publish` polecenia.</span><span class="sxs-lookup"><span data-stu-id="fc604-144">For example, when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc604-145">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="fc604-145">See also</span></span>

- [<span data-ttu-id="fc604-146">repozytorium usługi dotnet/zestawu SDK usługi GitHub</span><span class="sxs-lookup"><span data-stu-id="fc604-146">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- [<span data-ttu-id="fc604-147">Przewodnik instalacji platformy .NET</span><span class="sxs-lookup"><span data-stu-id="fc604-147">.NET installation guide</span></span>](../install/windows.md)
