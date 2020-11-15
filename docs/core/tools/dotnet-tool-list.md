---
title: polecenie listy narzędzi dotnet
description: Polecenie Lista narzędzi dotnet zawiera listę narzędzi .NET, które są zainstalowane na komputerze.
ms.date: 02/14/2020
ms.openlocfilehash: d884f2c41834dd9704de3a8ca15417ba368fde4b
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634288"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="18559-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="18559-103">dotnet tool list</span></span>

<span data-ttu-id="18559-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,1 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="18559-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="18559-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="18559-105">Name</span></span>

<span data-ttu-id="18559-106">`dotnet tool list` -Wyświetla wszystkie [Narzędzia .NET](global-tools.md) określonego typu aktualnie zainstalowane na maszynie.</span><span class="sxs-lookup"><span data-stu-id="18559-106">`dotnet tool list` - Lists all [.NET tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="18559-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="18559-107">Synopsis</span></span>

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list --local

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a><span data-ttu-id="18559-108">Opis</span><span class="sxs-lookup"><span data-stu-id="18559-108">Description</span></span>

<span data-ttu-id="18559-109">`dotnet tool list`Polecenie umożliwia wyświetlenie listy wszystkich narzędzi globalnych, ścieżek narzędziowych i lokalnych programu .NET zainstalowanych na komputerze.</span><span class="sxs-lookup"><span data-stu-id="18559-109">The `dotnet tool list` command provides a way for you to list all .NET global, tool-path, or local tools installed on your machine.</span></span> <span data-ttu-id="18559-110">Polecenie wyświetla listę Nazwa pakietu, zainstalowana wersja i polecenie Narzędzia.</span><span class="sxs-lookup"><span data-stu-id="18559-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="18559-111">Aby użyć polecenia, należy określić jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="18559-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="18559-112">Aby wyświetlić narzędzia globalne zainstalowane w lokalizacji domyślnej, użyj `--global` opcji</span><span class="sxs-lookup"><span data-stu-id="18559-112">To list global tools installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="18559-113">Aby wyświetlić narzędzia globalne zainstalowane w niestandardowej lokalizacji, użyj `--tool-path` opcji.</span><span class="sxs-lookup"><span data-stu-id="18559-113">To list global tools installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="18559-114">Aby wyświetlić listę lokalnych narzędzi, użyj `--local` opcji lub Pomiń `--global` Opcje, `--tool-path` i `--local` .</span><span class="sxs-lookup"><span data-stu-id="18559-114">To list local tools, use the `--local` option or omit the `--global`, `--tool-path`, and `--local` options.</span></span>

<span data-ttu-id="18559-115">**Narzędzia lokalne są dostępne począwszy od zestaw .NET Core SDK 3,0.**</span><span class="sxs-lookup"><span data-stu-id="18559-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="18559-116">Opcje</span><span class="sxs-lookup"><span data-stu-id="18559-116">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="18559-117">Wyświetla narzędzia globalne dla całego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="18559-117">Lists user-wide global tools.</span></span> <span data-ttu-id="18559-118">Nie można łączyć z `--tool-path` opcją.</span><span class="sxs-lookup"><span data-stu-id="18559-118">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="18559-119">Pomijanie obu `--global` i `--tool-path` wyświetla listę lokalnych narzędzi.</span><span class="sxs-lookup"><span data-stu-id="18559-119">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="18559-120">Drukuje krótką pomoc dla polecenia.</span><span class="sxs-lookup"><span data-stu-id="18559-120">Prints out a short help for the command.</span></span>

- **`--local`**

  <span data-ttu-id="18559-121">Wyświetla listę lokalnych narzędzi dla bieżącego katalogu.</span><span class="sxs-lookup"><span data-stu-id="18559-121">Lists local tools for the current directory.</span></span> <span data-ttu-id="18559-122">Nie można łączyć z `--global` `--tool-path` opcjami ani.</span><span class="sxs-lookup"><span data-stu-id="18559-122">Can't be combined with the `--global` or `--tool-path` options.</span></span> <span data-ttu-id="18559-123">Pominięcie obu tych elementów `--global` i `--tool-path` wyświetlenie listy lokalnych narzędzi, nawet jeśli `--local` nie jest określony.</span><span class="sxs-lookup"><span data-stu-id="18559-123">Omitting both `--global` and `--tool-path` lists local tools even if `--local` is not specified.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="18559-124">Określa niestandardową lokalizację, w której mają zostać znalezione narzędzia globalne.</span><span class="sxs-lookup"><span data-stu-id="18559-124">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="18559-125">ŚCIEŻKA może być bezwzględna lub względna.</span><span class="sxs-lookup"><span data-stu-id="18559-125">PATH can be absolute or relative.</span></span> <span data-ttu-id="18559-126">Nie można łączyć z `--global` opcją.</span><span class="sxs-lookup"><span data-stu-id="18559-126">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="18559-127">Pomijanie obu `--global` i `--tool-path` wyświetla listę lokalnych narzędzi.</span><span class="sxs-lookup"><span data-stu-id="18559-127">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="18559-128">Przykłady</span><span class="sxs-lookup"><span data-stu-id="18559-128">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="18559-129">Wyświetla wszystkie narzędzia globalne zainstalowane na komputerze (bieżący profil użytkownika).</span><span class="sxs-lookup"><span data-stu-id="18559-129">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="18559-130">Wyświetla listę globalnych narzędzi z określonego katalogu systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="18559-130">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="18559-131">Wyświetla listę globalnych narzędzi z określonego katalogu Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="18559-131">Lists the global tools from a specific Linux/macOS directory.</span></span>

- <span data-ttu-id="18559-132">**`dotnet tool list`** oraz **`dotnet tool list --local`**</span><span class="sxs-lookup"><span data-stu-id="18559-132">**`dotnet tool list`** or **`dotnet tool list --local`**</span></span>

  <span data-ttu-id="18559-133">Wyświetla listę wszystkich narzędzi lokalnych dostępnych w bieżącym katalogu.</span><span class="sxs-lookup"><span data-stu-id="18559-133">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="18559-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="18559-134">See also</span></span>

- [<span data-ttu-id="18559-135">Narzędzia .NET</span><span class="sxs-lookup"><span data-stu-id="18559-135">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="18559-136">Samouczek: Instalowanie i używanie narzędzia globalnego platformy .NET przy użyciu interfejsu wiersza polecenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="18559-136">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="18559-137">Samouczek: Instalowanie i używanie lokalnego narzędzia .NET przy użyciu interfejsu wiersza polecenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="18559-137">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
