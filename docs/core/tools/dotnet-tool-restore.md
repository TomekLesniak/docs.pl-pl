---
title: polecenie Narzędzia dotnet
description: Polecenie Narzędzia dotnet jest instalowane na komputerze jako lokalne narzędzia .NET, które znajdują się w zakresie dla bieżącego katalogu.
ms.date: 02/14/2020
ms.openlocfilehash: 3425bc6b78fd53f578c209013f83b006305dbb81
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242932"
---
# <a name="dotnet-tool-restore"></a><span data-ttu-id="a0d92-103">dotnet tool restore</span><span class="sxs-lookup"><span data-stu-id="a0d92-103">dotnet tool restore</span></span>

<span data-ttu-id="a0d92-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 3,0 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="a0d92-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="a0d92-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="a0d92-105">Name</span></span>

<span data-ttu-id="a0d92-106">`dotnet tool restore` -Instaluje lokalne narzędzia .NET, które znajdują się w zakresie dla bieżącego katalogu.</span><span class="sxs-lookup"><span data-stu-id="a0d92-106">`dotnet tool restore` - Installs the .NET local tools that are in scope for the current directory.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a0d92-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="a0d92-107">Synopsis</span></span>

```dotnetcli
dotnet tool restore
    [--configfile <FILE>] [--add-source <SOURCE>]
    [tool-manifest <PATH_TO_MANIFEST_FILE>] [--disable-parallel]
    [--ignore-failed-sources] [--no-cache] [--interactive]
    [-v|--verbosity <LEVEL>]

dotnet tool restore -h|--help
```

## <a name="description"></a><span data-ttu-id="a0d92-108">Opis</span><span class="sxs-lookup"><span data-stu-id="a0d92-108">Description</span></span>

<span data-ttu-id="a0d92-109">`dotnet tool restore`Polecenie znajduje plik manifestu narzędzia, który znajduje się w zakresie dla bieżącego katalogu i instaluje narzędzia, które są w nim wymienione.</span><span class="sxs-lookup"><span data-stu-id="a0d92-109">The `dotnet tool restore` command finds the tool manifest file that is in scope for the current directory and installs the tools that are listed in it.</span></span> <span data-ttu-id="a0d92-110">Aby uzyskać informacje na temat plików manifestu, zobacz [Instalowanie narzędzia lokalnego](global-tools.md#install-a-local-tool) i [wywoływanie narzędzia lokalnego](global-tools.md#invoke-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="a0d92-110">For information about manifest files, see [Install a local tool](global-tools.md#install-a-local-tool) and [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="options"></a><span data-ttu-id="a0d92-111">Opcje</span><span class="sxs-lookup"><span data-stu-id="a0d92-111">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="a0d92-112">Plik konfiguracji NuGet (*nuget.config*) do użycia.</span><span class="sxs-lookup"><span data-stu-id="a0d92-112">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="a0d92-113">Dodaje dodatkowe źródło pakietów NuGet do użycia podczas instalacji.</span><span class="sxs-lookup"><span data-stu-id="a0d92-113">Adds an additional NuGet package source to use during installation.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="a0d92-114">Ścieżka do pliku manifestu.</span><span class="sxs-lookup"><span data-stu-id="a0d92-114">Path to the manifest file.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="a0d92-115">Zapobiegaj równoległemu przywracaniu wielu projektów.</span><span class="sxs-lookup"><span data-stu-id="a0d92-115">Prevent restoring multiple projects in parallel.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="a0d92-116">Traktuj błędy źródłowe pakietu jako ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="a0d92-116">Treat package source failures as warnings.</span></span>

- **`--no-cache`**

  <span data-ttu-id="a0d92-117">Nie Buforuj pakietów i żądań HTTP.</span><span class="sxs-lookup"><span data-stu-id="a0d92-117">Do not cache packages and http requests.</span></span>

- **`--interactive`**

  <span data-ttu-id="a0d92-118">Umożliwia zatrzymanie polecenia i oczekiwanie na dane wejściowe użytkownika lub akcję (na przykład zakończenie uwierzytelniania).</span><span class="sxs-lookup"><span data-stu-id="a0d92-118">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`-h|--help`**

  <span data-ttu-id="a0d92-119">Drukuje krótką pomoc dla polecenia.</span><span class="sxs-lookup"><span data-stu-id="a0d92-119">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="a0d92-120">Ustawia poziom szczegółowości polecenia.</span><span class="sxs-lookup"><span data-stu-id="a0d92-120">Sets the verbosity level of the command.</span></span> <span data-ttu-id="a0d92-121">Dozwolone wartości to `q[uiet]` , `m[inimal]` , `n[ormal]` , `d[etailed]` i `diag[nostic]` .</span><span class="sxs-lookup"><span data-stu-id="a0d92-121">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="example"></a><span data-ttu-id="a0d92-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="a0d92-122">Example</span></span>

- **`dotnet tool restore`**

  <span data-ttu-id="a0d92-123">Przywraca lokalne narzędzia dla bieżącego katalogu.</span><span class="sxs-lookup"><span data-stu-id="a0d92-123">Restores local tools for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0d92-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a0d92-124">See also</span></span>

- [<span data-ttu-id="a0d92-125">Narzędzia .NET</span><span class="sxs-lookup"><span data-stu-id="a0d92-125">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="a0d92-126">Samouczek: Instalowanie i używanie lokalnego narzędzia .NET przy użyciu interfejsu wiersza polecenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="a0d92-126">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
