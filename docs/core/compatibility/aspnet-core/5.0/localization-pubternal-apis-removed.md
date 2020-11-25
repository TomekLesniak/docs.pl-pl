---
title: 'Zmiana podziału: Usunięto interfejsy API Pubternal'
description: Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0, gdzie zostały usunięte niektóre interfejsy API lokalizacji pubternal
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: ae647d66b716175536edb3c978b027ebb7d3ddac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761407"
---
# <a name="localization-pubternal-apis-removed"></a><span data-ttu-id="11299-103">Lokalizacja: Usunięto interfejsy API "Pubternal"</span><span class="sxs-lookup"><span data-stu-id="11299-103">Localization: "Pubternal" APIs removed</span></span>

<span data-ttu-id="11299-104">Aby lepiej zachować powierzchnię publicznego interfejsu API ASP.NET Core, niektóre :::no-loc text="\"pubternal\""::: interfejsy API lokalizacji zostały usunięte.</span><span class="sxs-lookup"><span data-stu-id="11299-104">To better maintain the public API surface of ASP.NET Core, some :::no-loc text="\"pubternal\""::: localization APIs were removed.</span></span> <span data-ttu-id="11299-105">:::no-loc text="\"pubternal\"":::Interfejs API ma `public` modyfikator dostępu i jest zdefiniowany w przestrzeni nazw, która oznacza przeznaczenie [wewnętrzne](../../../../csharp/language-reference/keywords/internal.md) .</span><span class="sxs-lookup"><span data-stu-id="11299-105">A :::no-loc text="\"pubternal\""::: API has a `public` access modifier and is defined in a namespace that implies an [internal](../../../../csharp/language-reference/keywords/internal.md) intent.</span></span>

<span data-ttu-id="11299-106">Aby zapoznać się z omówieniem, zobacz [dotnet/aspnetcore # 22291](https://github.com/dotnet/aspnetcore/issues/22291).</span><span class="sxs-lookup"><span data-stu-id="11299-106">For discussion, see [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="11299-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="11299-107">Version introduced</span></span>

<span data-ttu-id="11299-108">5,0 wersja zapoznawcza 6</span><span class="sxs-lookup"><span data-stu-id="11299-108">5.0 Preview 6</span></span>

## <a name="old-behavior"></a><span data-ttu-id="11299-109">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="11299-109">Old behavior</span></span>

<span data-ttu-id="11299-110">Następujące interfejsy API `public` :</span><span class="sxs-lookup"><span data-stu-id="11299-110">The following APIs were `public`:</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <span data-ttu-id="11299-111">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` przeciążenia konstruktora akceptujące jeden z następujących typów parametrów:</span><span class="sxs-lookup"><span data-stu-id="11299-111">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

## <a name="new-behavior"></a><span data-ttu-id="11299-112">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="11299-112">New behavior</span></span>

<span data-ttu-id="11299-113">Na poniższej liście przedstawiono zmiany:</span><span class="sxs-lookup"><span data-stu-id="11299-113">The following list outlines the changes:</span></span>

- <span data-ttu-id="11299-114">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` stała `Microsoft.Extensions.Localization.AssemblyWrapper` się i jest teraz `internal` .</span><span class="sxs-lookup"><span data-stu-id="11299-114">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` became `Microsoft.Extensions.Localization.AssemblyWrapper` and is now `internal`.</span></span>
- <span data-ttu-id="11299-115">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` stała `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` się i jest teraz `internal` .</span><span class="sxs-lookup"><span data-stu-id="11299-115">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` became `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` and is now `internal`.</span></span>
- <span data-ttu-id="11299-116">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` przeciążenia konstruktora akceptujące jeden z następujących typów parametrów są teraz `internal` :</span><span class="sxs-lookup"><span data-stu-id="11299-116">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types are now `internal`:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

## <a name="reason-for-change"></a><span data-ttu-id="11299-117">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="11299-117">Reason for change</span></span>

<span data-ttu-id="11299-118">Wyjaśniono dokładniej dla [ASPNET/anonsów # 377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), :::no-loc text="\"pubternal\""::: typy zostały usunięte z `public` powierzchni interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="11299-118">Explained more thoroughly at [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), :::no-loc text="\"pubternal\""::: types were removed from the `public` API surface.</span></span> <span data-ttu-id="11299-119">Te zmiany dostosowują więcej klas do tej decyzji projektowej.</span><span class="sxs-lookup"><span data-stu-id="11299-119">These changes adapt more classes to that design decision.</span></span> <span data-ttu-id="11299-120">Omawiane klasy były przeznaczone jako punkty rozszerzenia dla wewnętrznego testowania zespołu.</span><span class="sxs-lookup"><span data-stu-id="11299-120">The classes in question were intended as extension points for the team's internal testing.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="11299-121">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="11299-121">Recommended action</span></span>

<span data-ttu-id="11299-122">Chociaż jest to mało prawdopodobne, niektóre aplikacje mogą celowo lub przypadkowo zależeć od :::no-loc text="\"pubternal\""::: typów.</span><span class="sxs-lookup"><span data-stu-id="11299-122">Although it's unlikely, some apps may intentionally or accidentally depend upon the :::no-loc text="\"pubternal\""::: types.</span></span> <span data-ttu-id="11299-123">Zapoznaj się z nowymi sekcjami [zachowania](#new-behavior) , aby określić, jak przeprowadzić migrację z typów.</span><span class="sxs-lookup"><span data-stu-id="11299-123">See the [New behavior](#new-behavior) sections to determine how to migrate away from the types.</span></span>

<span data-ttu-id="11299-124">W przypadku zidentyfikowania scenariusza, który publiczny interfejs API jest dozwolony przed tą zmianą, ale nie teraz, należy rozwiązać problem w programie [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span><span class="sxs-lookup"><span data-stu-id="11299-124">If you've identified a scenario which the public API allowed before this change but doesn't now, file an issue at [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="11299-125">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="11299-125">Affected APIs</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.%23ctor%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `T:Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.#ctor`

-->
