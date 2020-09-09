---
title: dotnet-sos-.NET Core
description: Instalowanie i używanie narzędzia wiersza polecenia dotnet-sos.
ms.date: 08/26/2020
ms.openlocfilehash: 3ce7ca79bbc2c72958d395e9d312e3001ec9fbf8
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598352"
---
# <a name="sos-installer-dotnet-sos"></a><span data-ttu-id="c9ee5-103">Instalator SOS (dotnet-sos)</span><span class="sxs-lookup"><span data-stu-id="c9ee5-103">SOS installer (dotnet-sos)</span></span>

<span data-ttu-id="c9ee5-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,1 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="c9ee5-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install-dotnet-sos"></a><span data-ttu-id="c9ee5-105">Zainstaluj dotnet-sos</span><span class="sxs-lookup"><span data-stu-id="c9ee5-105">Install dotnet-sos</span></span>

<span data-ttu-id="c9ee5-106">Aby zainstalować najnowszą wersję `dotnet-sos` [pakietu NuGet](https://www.nuget.org/packages/dotnet-sos), użyj polecenia [Narzędzia dotnet Install](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="c9ee5-106">To install the latest release version of the `dotnet-sos` [NuGet package](https://www.nuget.org/packages/dotnet-sos), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-sos
```

## <a name="synopsis"></a><span data-ttu-id="c9ee5-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="c9ee5-107">Synopsis</span></span>

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a><span data-ttu-id="c9ee5-108">Opis</span><span class="sxs-lookup"><span data-stu-id="c9ee5-108">Description</span></span>

<span data-ttu-id="c9ee5-109">`dotnet-sos`Narzędzie globalne instaluje [rozszerzenie debugera sos](https://docs.microsoft.com/dotnet/framework/tools/sos-dll-sos-debugging-extension) umożliwiające [inspekcję stanu zarządzanego programu .NET Core](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) z natywnych debugerów, takich jak WinDbg/CDB w systemach Windows i LLDB w systemach Linux i MacOS.</span><span class="sxs-lookup"><span data-stu-id="c9ee5-109">The `dotnet-sos` global tool installs the [SOS debugger extension](https://docs.microsoft.com/dotnet/framework/tools/sos-dll-sos-debugging-extension) allowing [inspection of managed .NET Core state](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) from native debuggers like WinDbg/cdb on Windows and lldb on Linux and MacOS.</span></span> <span data-ttu-id="c9ee5-110">Należy zauważyć, że najnowsze wersje debugera systemu Windows (>= Version 10.0.18317.1001 of WinDbg lub CDB) będą automatycznie ładować SOS z galerii rozszerzeń firmy Microsoft, więc zainstalowanie SOS za pomocą `dotnet-sos` narzędzia jest konieczna tylko w systemach Linux i MacOS lub w systemie Windows, jeśli są używane starsze narzędzia debugowania.</span><span class="sxs-lookup"><span data-stu-id="c9ee5-110">Note that recent versions of the Windows Debugger (>= version 10.0.18317.1001 of WinDbg or cdb) will load SOS automatically from the Microsoft extension gallery, so installing SOS via the `dotnet-sos` tool is only needed on Linux and MacOS or on Windows if using older debugging tools.</span></span>

## <a name="options"></a><span data-ttu-id="c9ee5-111">Opcje</span><span class="sxs-lookup"><span data-stu-id="c9ee5-111">Options</span></span>

- **`--version`**

  <span data-ttu-id="c9ee5-112">Wyświetla informacje o wersji.</span><span class="sxs-lookup"><span data-stu-id="c9ee5-112">Displays version information.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c9ee5-113">Wyświetla pomoc w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="c9ee5-113">Shows command-line help.</span></span>

## <a name="dotnet-sos-install"></a><span data-ttu-id="c9ee5-114">Instalacja dotnet-sos</span><span class="sxs-lookup"><span data-stu-id="c9ee5-114">dotnet-sos install</span></span>

<span data-ttu-id="c9ee5-115">Instaluje [rozszerzenie sos lokalnie](https://docs.microsoft.com/dotnet/framework/tools/sos-dll-sos-debugging-extension) na potrzeby debugowania procesów .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c9ee5-115">Installs the [SOS extension locally](https://docs.microsoft.com/dotnet/framework/tools/sos-dll-sos-debugging-extension) for use debugging .NET Core processes.</span></span> <span data-ttu-id="c9ee5-116">W systemach MacOS i Linux plik. lldbinit zostanie zaktualizowany, dzięki czemu rozszerzenie zostanie automatycznie załadowane przy uruchomieniu LLDB.</span><span class="sxs-lookup"><span data-stu-id="c9ee5-116">On MacOS and Linux, the .lldbinit file will be updated so that the extension automatically loads at lldb startup.</span></span> <span data-ttu-id="c9ee5-117">Jeśli instalujesz SOS w systemie Windows przy użyciu starszych narzędzi debugowania (< wersja 10.0.18317.1001), musisz ręcznie załadować rozszerzenie w programie WinDbg lub CDB, uruchamiając `.load %USERPROFILE%\.dotnet\sos\sos.dll` je w debugerze.</span><span class="sxs-lookup"><span data-stu-id="c9ee5-117">If installing SOS on Windows with older debugging tools (< version 10.0.18317.1001), you will need to manually load the extension in WinDbg or cdb by running `.load %USERPROFILE%\.dotnet\sos\sos.dll` in the debugger.</span></span>

### <a name="synopsis"></a><span data-ttu-id="c9ee5-118">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="c9ee5-118">Synopsis</span></span>

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a><span data-ttu-id="c9ee5-119">sos — Dezinstalacja</span><span class="sxs-lookup"><span data-stu-id="c9ee5-119">dotnet-sos uninstall</span></span>

<span data-ttu-id="c9ee5-120">Odinstalowuje [rozszerzenie sos](https://docs.microsoft.com/dotnet/framework/tools/sos-dll-sos-debugging-extension) i, jeśli w systemie Linux lub MacOS, usunie je z konfiguracji LLDB.</span><span class="sxs-lookup"><span data-stu-id="c9ee5-120">Uninstalls the [SOS extension](https://docs.microsoft.com/dotnet/framework/tools/sos-dll-sos-debugging-extension) and, if on Linux or MacOS, removes it from lldb configuration.</span></span>

### <a name="synopsis"></a><span data-ttu-id="c9ee5-121">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="c9ee5-121">Synopsis</span></span>

```console
dotnet-sos uninstall
```
