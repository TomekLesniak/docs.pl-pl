---
title: polecenie wyszukiwania narzędzia dotnet
description: Polecenie wyszukiwania narzędzia dotnet przeszukuje narzędzia .NET, które są publikowane w NuGet.org.
ms.date: 11/11/2020
ms.openlocfilehash: e0289e651ec4a439c791c8c948bef2d85d9c3794
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634145"
---
# <a name="dotnet-tool-search"></a><span data-ttu-id="0a9a4-103">Wyszukiwanie narzędzia dotnet</span><span class="sxs-lookup"><span data-stu-id="0a9a4-103">dotnet tool search</span></span>

<span data-ttu-id="0a9a4-104">**Ten artykuł dotyczy:** ✔️ .NET 5,0 SDK i nowszych wersji</span><span class="sxs-lookup"><span data-stu-id="0a9a4-104">**This article applies to:** ✔️ .NET 5.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="0a9a4-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="0a9a4-105">Name</span></span>

<span data-ttu-id="0a9a4-106">`dotnet tool search` — Przeszukuje wszystkie [Narzędzia .NET](global-tools.md) , które są publikowane w programie NuGet.</span><span class="sxs-lookup"><span data-stu-id="0a9a4-106">`dotnet tool search` - Searches all [.NET tools](global-tools.md) that are published to NuGet.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0a9a4-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="0a9a4-107">Synopsis</span></span>

```dotnetcli
dotnet tool search [--detail]  [--prerelease]
    [--skip <NUMBER>] [--take <NUMBER>] <SEARCH TERM>

dotnet tool search -h|--help
```

## <a name="description"></a><span data-ttu-id="0a9a4-108">Opis</span><span class="sxs-lookup"><span data-stu-id="0a9a4-108">Description</span></span>

<span data-ttu-id="0a9a4-109">`dotnet tool search`Polecenie umożliwia przeszukiwanie narzędzia NuGet dla narzędzi, które mogą być używane jako globalne, narzędzie-ścieżka i narzędzia platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="0a9a4-109">The `dotnet tool search` command provides a way for you to search NuGet for tools that can be used as .NET global, tool-path, or local tools.</span></span> <span data-ttu-id="0a9a4-110">Polecenie przeszukuje nazwy i metadane narzędzi, takie jak tytuły, opisy i Tagi.</span><span class="sxs-lookup"><span data-stu-id="0a9a4-110">The command searches the tool names and metadata such as titles, descriptions, and tags.</span></span>

<span data-ttu-id="0a9a4-111">Polecenie używa [interfejsu API wyszukiwania NuGet](/nuget/api/search-query-service-resource#search-for-packages).</span><span class="sxs-lookup"><span data-stu-id="0a9a4-111">The command uses the [NuGet Search API](/nuget/api/search-query-service-resource#search-for-packages).</span></span> <span data-ttu-id="0a9a4-112">Filtruje on `packageType=dotnettool` , aby wybrać tylko pakiety narzędzi .NET.</span><span class="sxs-lookup"><span data-stu-id="0a9a4-112">It filters on `packageType=dotnettool` to select only .NET tool packages.</span></span>

## <a name="options"></a><span data-ttu-id="0a9a4-113">Opcje</span><span class="sxs-lookup"><span data-stu-id="0a9a4-113">Options</span></span>

- **`--detail`**

  <span data-ttu-id="0a9a4-114">Pokazuje szczegółowe wyniki zapytania.</span><span class="sxs-lookup"><span data-stu-id="0a9a4-114">Shows detailed results from the query.</span></span>

- **`--prerelease`**

  <span data-ttu-id="0a9a4-115">Obejmuje pakiety wersji wstępnej.</span><span class="sxs-lookup"><span data-stu-id="0a9a4-115">Includes pre-release packages.</span></span>

- **`--skip <NUMBER>`**

  <span data-ttu-id="0a9a4-116">Określa liczbę wyników zapytania do pominięcia.</span><span class="sxs-lookup"><span data-stu-id="0a9a4-116">Specifies the number of query results to skip.</span></span> <span data-ttu-id="0a9a4-117">Używany do dzielenia na strony.</span><span class="sxs-lookup"><span data-stu-id="0a9a4-117">Used for pagination.</span></span>

- **`--take <NUMBER>`**

  <span data-ttu-id="0a9a4-118">Określa liczbę wyników zapytania do wyświetlenia.</span><span class="sxs-lookup"><span data-stu-id="0a9a4-118">Specifies the number of query results to show.</span></span> <span data-ttu-id="0a9a4-119">Używany do dzielenia na strony.</span><span class="sxs-lookup"><span data-stu-id="0a9a4-119">Used for pagination.</span></span>

- **`-h|--help`**

  <span data-ttu-id="0a9a4-120">Wyświetla pomoc w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="0a9a4-120">Shows command-line help.</span></span>

## <a name="examples"></a><span data-ttu-id="0a9a4-121">Przykłady</span><span class="sxs-lookup"><span data-stu-id="0a9a4-121">Examples</span></span>

- <span data-ttu-id="0a9a4-122">Wyszukaj NuGet.org dla narzędzi .NET, które mają "format" w nazwie lub opisie pakietu:</span><span class="sxs-lookup"><span data-stu-id="0a9a4-122">Search NuGet.org for .NET tools that have "format" in their package name or description:</span></span>

  ```dotnetcli
  dotnet tool search format
  ```

  <span data-ttu-id="0a9a4-123">Dane wyjściowe wyglądają podobnie do poniższego przykładu:</span><span class="sxs-lookup"><span data-stu-id="0a9a4-123">The output looks like the following example:</span></span>

  ```output
  Package ID                              Latest Version      Authors                                                                     Downloads      Verified
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
  dotnet-format                           4.1.131201          Microsoft                                                                   496746
  bsoa.generator                          1.0.0               Microsoft                                                                   533
  ```

- <span data-ttu-id="0a9a4-124">Wyszukiwanie w programie NuGet.org dla narzędzi .NET, które mają "format" w nazwie lub metadanych pakietu, pokazują tylko pierwszy wynik i pokazują widok szczegółowy.</span><span class="sxs-lookup"><span data-stu-id="0a9a4-124">Search NuGet.org for .NET tools that have "format" in their package name or metadata, show only the first result, and show a detailed view.</span></span>

  ```dotnetcli
  dotnet tool search format --take 1 --detail
  ```

  <span data-ttu-id="0a9a4-125">Dane wyjściowe wyglądają podobnie do poniższego przykładu:</span><span class="sxs-lookup"><span data-stu-id="0a9a4-125">The output looks like the following example:</span></span>

  ```output
  ----------------
  dotnet-format
  Latest Version: 4.1.131201
  Authors: Microsoft
  Tags:
  Downloads: 496746
  Verified: False
  Description: Command line tool for formatting C# and Visual Basic code files based on .editorconfig settings.
  Versions:
          3.0.2 Downloads: 1973
          3.0.4 Downloads: 9064
          3.1.37601 Downloads: 114730
          3.2.107702 Downloads: 13423
          3.3.111304 Downloads: 131195
          4.0.130203 Downloads: 78610
          4.1.131201 Downloads: 145927
  ```

## <a name="see-also"></a><span data-ttu-id="0a9a4-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0a9a4-126">See also</span></span>

- [<span data-ttu-id="0a9a4-127">Narzędzia .NET</span><span class="sxs-lookup"><span data-stu-id="0a9a4-127">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="0a9a4-128">Samouczek: Instalowanie i używanie narzędzia globalnego platformy .NET przy użyciu interfejsu wiersza polecenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="0a9a4-128">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="0a9a4-129">Samouczek: Instalowanie i używanie lokalnego narzędzia .NET przy użyciu interfejsu wiersza polecenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="0a9a4-129">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
