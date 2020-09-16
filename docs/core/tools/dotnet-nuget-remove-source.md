---
title: polecenie Remove Source NuGet narzędzia dotnet
description: Polecenie Remove Source NuGet programu dotnet spowoduje usunięcie istniejącego źródła z plików konfiguracji programu NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: b5575c31c0008d6e3e5a2e52906a076614217dd0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537896"
---
# <a name="dotnet-nuget-remove-source"></a><span data-ttu-id="96ec6-103">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="96ec6-103">dotnet nuget remove source</span></span>

<span data-ttu-id="96ec6-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 3.1.200 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="96ec6-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="96ec6-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="96ec6-105">Name</span></span>

<span data-ttu-id="96ec6-106">`dotnet nuget remove source` -Usuń źródło NuGet.</span><span class="sxs-lookup"><span data-stu-id="96ec6-106">`dotnet nuget remove source` - Remove a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="96ec6-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="96ec6-107">Synopsis</span></span>

```dotnetcli
dotnet nuget remove source <NAME> [--configfile <FILE>]

dotnet nuget remove source -h|--help
```

## <a name="description"></a><span data-ttu-id="96ec6-108">Opis</span><span class="sxs-lookup"><span data-stu-id="96ec6-108">Description</span></span>

<span data-ttu-id="96ec6-109">`dotnet nuget remove source`Polecenie usuwa istniejące źródło z plików konfiguracji programu NuGet.</span><span class="sxs-lookup"><span data-stu-id="96ec6-109">The `dotnet nuget remove source` command removes an existing source from your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="96ec6-110">Argumenty</span><span class="sxs-lookup"><span data-stu-id="96ec6-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="96ec6-111">Nazwa źródła.</span><span class="sxs-lookup"><span data-stu-id="96ec6-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="96ec6-112">Opcje</span><span class="sxs-lookup"><span data-stu-id="96ec6-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="96ec6-113">Plik konfiguracji programu NuGet.</span><span class="sxs-lookup"><span data-stu-id="96ec6-113">The NuGet configuration file.</span></span> <span data-ttu-id="96ec6-114">Jeśli zostanie określony, będą używane tylko ustawienia z tego pliku.</span><span class="sxs-lookup"><span data-stu-id="96ec6-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="96ec6-115">Jeśli nie zostanie określony, zostanie użyta hierarchia plików konfiguracji z bieżącego katalogu.</span><span class="sxs-lookup"><span data-stu-id="96ec6-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="96ec6-116">Aby uzyskać więcej informacji, zobacz [typowe konfiguracje NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="96ec6-116">For more information, see [Common NuGet Configurations](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="96ec6-117">Przykłady</span><span class="sxs-lookup"><span data-stu-id="96ec6-117">Examples</span></span>

- <span data-ttu-id="96ec6-118">Usuń źródło o nazwie `mySource` :</span><span class="sxs-lookup"><span data-stu-id="96ec6-118">Remove a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget remove source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="96ec6-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="96ec6-119">See also</span></span>

- [<span data-ttu-id="96ec6-120">Sekcje źródłowe pakietu w plikach NuGet.config</span><span class="sxs-lookup"><span data-stu-id="96ec6-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="96ec6-121">sources — polecenie (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="96ec6-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
