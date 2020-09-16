---
title: polecenie źródła listy NuGet dotnet
description: Polecenie Source list NuGet programu dotnet zawiera listę wszystkich istniejących źródeł z plików konfiguracji programu NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 071061e32aa1bf888e197ec6bf97f4e4f6859f0b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537900"
---
# <a name="dotnet-nuget-list-source"></a><span data-ttu-id="cfc4c-103">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="cfc4c-103">dotnet nuget list source</span></span>

<span data-ttu-id="cfc4c-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 3.1.200 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="cfc4c-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="cfc4c-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="cfc4c-105">Name</span></span>

<span data-ttu-id="cfc4c-106">`dotnet nuget list source` -Wyświetla wszystkie skonfigurowane źródła NuGet.</span><span class="sxs-lookup"><span data-stu-id="cfc4c-106">`dotnet nuget list source` - Lists all configured NuGet sources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cfc4c-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="cfc4c-107">Synopsis</span></span>

```dotnetcli
dotnet nuget list source [--format [Detailed|Short]] [--configfile <FILE>]

dotnet nuget list source -h|--help
```

## <a name="description"></a><span data-ttu-id="cfc4c-108">Opis</span><span class="sxs-lookup"><span data-stu-id="cfc4c-108">Description</span></span>

<span data-ttu-id="cfc4c-109">`dotnet nuget list source`Polecenie wyświetla listę wszystkich istniejących źródeł z plików konfiguracji programu NuGet.</span><span class="sxs-lookup"><span data-stu-id="cfc4c-109">The `dotnet nuget list source` command lists all existing sources from your NuGet configuration files.</span></span>

## <a name="options"></a><span data-ttu-id="cfc4c-110">Opcje</span><span class="sxs-lookup"><span data-stu-id="cfc4c-110">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="cfc4c-111">Plik konfiguracji programu NuGet.</span><span class="sxs-lookup"><span data-stu-id="cfc4c-111">The NuGet configuration file.</span></span> <span data-ttu-id="cfc4c-112">Jeśli zostanie określony, będą używane tylko ustawienia z tego pliku.</span><span class="sxs-lookup"><span data-stu-id="cfc4c-112">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="cfc4c-113">Jeśli nie zostanie określony, zostanie użyta hierarchia plików konfiguracji z bieżącego katalogu.</span><span class="sxs-lookup"><span data-stu-id="cfc4c-113">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="cfc4c-114">Aby uzyskać więcej informacji, zobacz [typowe konfiguracje NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="cfc4c-114">For more information, see [Common NuGet Configurations](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`--format [Detailed|Short]`**

  <span data-ttu-id="cfc4c-115">Format danych wyjściowych polecenia list: `Detailed` (wartość domyślna) i `Short` .</span><span class="sxs-lookup"><span data-stu-id="cfc4c-115">The format of the list command output: `Detailed` (the default) and `Short`.</span></span>

## <a name="examples"></a><span data-ttu-id="cfc4c-116">Przykłady</span><span class="sxs-lookup"><span data-stu-id="cfc4c-116">Examples</span></span>

- <span data-ttu-id="cfc4c-117">Wyświetl listę skonfigurowanych źródeł z bieżącego katalogu:</span><span class="sxs-lookup"><span data-stu-id="cfc4c-117">List configured sources from the current directory:</span></span>

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a><span data-ttu-id="cfc4c-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cfc4c-118">See also</span></span>

- [<span data-ttu-id="cfc4c-119">Sekcje źródłowe pakietu w plikach NuGet.config</span><span class="sxs-lookup"><span data-stu-id="cfc4c-119">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="cfc4c-120">sources — polecenie (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="cfc4c-120">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
