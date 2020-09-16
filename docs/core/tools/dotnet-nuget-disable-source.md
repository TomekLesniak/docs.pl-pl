---
title: polecenie Wyłącz źródło NuGet dotnet
description: Polecenie Wyłącz źródło NuGet programu dotnet wyłącza istniejące źródło w plikach konfiguracji programu NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: af37a6589cebaf0501ee5647ebadb83125d0f56e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537954"
---
# <a name="dotnet-nuget-disable-source"></a><span data-ttu-id="9de79-103">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="9de79-103">dotnet nuget disable source</span></span>

<span data-ttu-id="9de79-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 3.1.200 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="9de79-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="9de79-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="9de79-105">Name</span></span>

<span data-ttu-id="9de79-106">`dotnet nuget disable source` -Wyłącz źródło NuGet.</span><span class="sxs-lookup"><span data-stu-id="9de79-106">`dotnet nuget disable source` - Disable a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9de79-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="9de79-107">Synopsis</span></span>

```dotnetcli
dotnet nuget disable source <NAME> [--configfile <FILE>]

dotnet nuget disable source -h|--help
```

## <a name="description"></a><span data-ttu-id="9de79-108">Opis</span><span class="sxs-lookup"><span data-stu-id="9de79-108">Description</span></span>

<span data-ttu-id="9de79-109">`dotnet nuget disable source`Polecenie wyłącza istniejące źródło w plikach konfiguracji NuGet.</span><span class="sxs-lookup"><span data-stu-id="9de79-109">The `dotnet nuget disable source` command disables an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="9de79-110">Argumenty</span><span class="sxs-lookup"><span data-stu-id="9de79-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="9de79-111">Nazwa źródła.</span><span class="sxs-lookup"><span data-stu-id="9de79-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="9de79-112">Opcje</span><span class="sxs-lookup"><span data-stu-id="9de79-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="9de79-113">Plik konfiguracji programu NuGet.</span><span class="sxs-lookup"><span data-stu-id="9de79-113">The NuGet configuration file.</span></span> <span data-ttu-id="9de79-114">Jeśli zostanie określony, będą używane tylko ustawienia z tego pliku.</span><span class="sxs-lookup"><span data-stu-id="9de79-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="9de79-115">Jeśli nie zostanie określony, zostanie użyta hierarchia plików konfiguracji z bieżącego katalogu.</span><span class="sxs-lookup"><span data-stu-id="9de79-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="9de79-116">Aby uzyskać więcej informacji, zobacz [typowe konfiguracje NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="9de79-116">For more information, see [Common NuGet Configurations](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="9de79-117">Przykłady</span><span class="sxs-lookup"><span data-stu-id="9de79-117">Examples</span></span>

- <span data-ttu-id="9de79-118">Wyłącz źródło o nazwie `mySource` :</span><span class="sxs-lookup"><span data-stu-id="9de79-118">Disable a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget disable source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="9de79-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9de79-119">See also</span></span>

- [<span data-ttu-id="9de79-120">Sekcje źródłowe pakietu w plikach NuGet.config</span><span class="sxs-lookup"><span data-stu-id="9de79-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="9de79-121">sources — polecenie (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="9de79-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
