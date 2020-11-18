---
title: Narzędzie diagnostyczne dotnet-sos — interfejs wiersza polecenia platformy .NET
description: Dowiedz się, jak zainstalować i użyć narzędzia interfejsu wiersza polecenia dotnet-sos do zarządzania rozszerzeniem debugera SOS, które jest używane z natywnymi debugerami w systemach Windows i Linux.
ms.date: 11/17/2020
ms.openlocfilehash: 59512c42a778f68bb3cd092dc854dcc727fd2881
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825445"
---
# <a name="sos-installer-dotnet-sos"></a><span data-ttu-id="9eb9a-103">Instalator SOS (dotnet-sos)</span><span class="sxs-lookup"><span data-stu-id="9eb9a-103">SOS installer (dotnet-sos)</span></span>

<span data-ttu-id="9eb9a-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,1 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="9eb9a-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="9eb9a-105">Instalowanie</span><span class="sxs-lookup"><span data-stu-id="9eb9a-105">Install</span></span>

<span data-ttu-id="9eb9a-106">Istnieją dwa sposoby na pobranie i zainstalowanie `dotnet-sos` :</span><span class="sxs-lookup"><span data-stu-id="9eb9a-106">There are two ways to download and install `dotnet-sos`:</span></span>

- <span data-ttu-id="9eb9a-107">**Narzędzie globalne dotnet:**</span><span class="sxs-lookup"><span data-stu-id="9eb9a-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="9eb9a-108">Aby zainstalować najnowszą wersję `dotnet-sos` [pakietu NuGet](https://www.nuget.org/packages/dotnet-sos), użyj polecenia [Narzędzia dotnet Install](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="9eb9a-108">To install the latest release version of the `dotnet-sos` [NuGet package](https://www.nuget.org/packages/dotnet-sos), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-sos
  ```

- <span data-ttu-id="9eb9a-109">**Pobieranie bezpośrednie:**</span><span class="sxs-lookup"><span data-stu-id="9eb9a-109">**Direct download:**</span></span>

  <span data-ttu-id="9eb9a-110">Pobierz plik wykonywalny narzędzia, który jest zgodny z platformą:</span><span class="sxs-lookup"><span data-stu-id="9eb9a-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="9eb9a-111">System operacyjny</span><span class="sxs-lookup"><span data-stu-id="9eb9a-111">OS</span></span>  | <span data-ttu-id="9eb9a-112">Platforma</span><span class="sxs-lookup"><span data-stu-id="9eb9a-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="9eb9a-113">Windows</span><span class="sxs-lookup"><span data-stu-id="9eb9a-113">Windows</span></span> | <span data-ttu-id="9eb9a-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [ARM](https://aka.ms/dotnet-sos/win-arm) \| [ARM — x64](https://aka.ms/dotnet-sos/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="9eb9a-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64)</span></span> |
  | <span data-ttu-id="9eb9a-115">macOS</span><span class="sxs-lookup"><span data-stu-id="9eb9a-115">macOS</span></span>   | [<span data-ttu-id="9eb9a-116">x64</span><span class="sxs-lookup"><span data-stu-id="9eb9a-116">x64</span></span>](https://aka.ms/dotnet-sos/osx-x64) |
  | <span data-ttu-id="9eb9a-117">Linux</span><span class="sxs-lookup"><span data-stu-id="9eb9a-117">Linux</span></span>   | <span data-ttu-id="9eb9a-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [ARM](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [MUSL — x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [MUSL — arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="9eb9a-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="9eb9a-119">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="9eb9a-119">Synopsis</span></span>

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a><span data-ttu-id="9eb9a-120">Opis</span><span class="sxs-lookup"><span data-stu-id="9eb9a-120">Description</span></span>

<span data-ttu-id="9eb9a-121">`dotnet-sos`Narzędzie globalne instaluje [rozszerzenie debugera sos](../../framework/tools/sos-dll-sos-debugging-extension.md) umożliwiające [inspekcję stanu zarządzanego programu .NET Core](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) z natywnych debugerów, takich jak WinDbg/CDB w systemach Windows i LLDB w systemach Linux i macOS.</span><span class="sxs-lookup"><span data-stu-id="9eb9a-121">The `dotnet-sos` global tool installs the [SOS debugger extension](../../framework/tools/sos-dll-sos-debugging-extension.md) allowing [inspection of managed .NET Core state](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) from native debuggers like WinDbg/cdb on Windows and lldb on Linux and macOS.</span></span> <span data-ttu-id="9eb9a-122">Najnowsze wersje debugera systemu Windows (>= Version 10.0.18317.1001 of WinDbg lub CDB) będą automatycznie ładować SOS z galerii rozszerzeń firmy Microsoft, więc zainstalowanie SOS za pomocą `dotnet-sos` narzędzia jest konieczna tylko w systemach Linux i macOS lub w systemie Windows, jeśli są używane starsze narzędzia debugowania.</span><span class="sxs-lookup"><span data-stu-id="9eb9a-122">Recent versions of the Windows Debugger (>= version 10.0.18317.1001 of WinDbg or cdb) will load SOS automatically from the Microsoft extension gallery, so installing SOS via the `dotnet-sos` tool is only needed on Linux and macOS or on Windows if using older debugging tools.</span></span>

## <a name="options"></a><span data-ttu-id="9eb9a-123">Opcje</span><span class="sxs-lookup"><span data-stu-id="9eb9a-123">Options</span></span>

- **`--version`**

  <span data-ttu-id="9eb9a-124">Wyświetla informacje o wersji.</span><span class="sxs-lookup"><span data-stu-id="9eb9a-124">Displays version information.</span></span>

- **`-h|--help`**

  <span data-ttu-id="9eb9a-125">Wyświetla pomoc w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="9eb9a-125">Shows command-line help.</span></span>

## <a name="dotnet-sos-install"></a><span data-ttu-id="9eb9a-126">Instalacja dotnet-sos</span><span class="sxs-lookup"><span data-stu-id="9eb9a-126">dotnet-sos install</span></span>

<span data-ttu-id="9eb9a-127">Instaluje [rozszerzenie sos](../../framework/tools/sos-dll-sos-debugging-extension.md) lokalnie na potrzeby debugowania procesów .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9eb9a-127">Installs the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) locally for debugging .NET Core processes.</span></span> <span data-ttu-id="9eb9a-128">W systemach macOS i Linux plik. lldbinit zostanie zaktualizowany, dzięki czemu rozszerzenie zostanie automatycznie załadowane przy uruchomieniu LLDB.</span><span class="sxs-lookup"><span data-stu-id="9eb9a-128">On macOS and Linux, the .lldbinit file will be updated so that the extension automatically loads at lldb startup.</span></span> <span data-ttu-id="9eb9a-129">Jeśli instalujesz SOS w systemie Windows przy użyciu starszych narzędzi debugowania (< wersja 10.0.18317.1001), musisz ręcznie załadować rozszerzenie w programie WinDbg lub CDB, uruchamiając `.load %USERPROFILE%\.dotnet\sos\sos.dll` je w debugerze.</span><span class="sxs-lookup"><span data-stu-id="9eb9a-129">If installing SOS on Windows with older debugging tools (< version 10.0.18317.1001), you will need to manually load the extension in WinDbg or cdb by running `.load %USERPROFILE%\.dotnet\sos\sos.dll` in the debugger.</span></span>

### <a name="synopsis"></a><span data-ttu-id="9eb9a-130">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="9eb9a-130">Synopsis</span></span>

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a><span data-ttu-id="9eb9a-131">sos — Dezinstalacja</span><span class="sxs-lookup"><span data-stu-id="9eb9a-131">dotnet-sos uninstall</span></span>

<span data-ttu-id="9eb9a-132">Odinstalowuje [rozszerzenie sos](../../framework/tools/sos-dll-sos-debugging-extension.md) i, jeśli w systemie Linux lub macOS, usunie je z konfiguracji LLDB.</span><span class="sxs-lookup"><span data-stu-id="9eb9a-132">Uninstalls the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) and, if on Linux or macOS, removes it from lldb configuration.</span></span>

### <a name="synopsis"></a><span data-ttu-id="9eb9a-133">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="9eb9a-133">Synopsis</span></span>

```console
dotnet-sos uninstall
```
