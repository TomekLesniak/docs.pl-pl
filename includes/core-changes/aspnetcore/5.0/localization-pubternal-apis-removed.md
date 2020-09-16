---
ms.openlocfilehash: 62a5f56bb7fffc453623a2c3202f288a19110158
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539516"
---
### <a name="localization-pubternal-apis-removed"></a><span data-ttu-id="b7501-101">Lokalizacja: Usunięto interfejsy API "Pubternal"</span><span class="sxs-lookup"><span data-stu-id="b7501-101">Localization: "Pubternal" APIs removed</span></span>

<span data-ttu-id="b7501-102">Aby lepiej zachować powierzchnię publicznego interfejsu API ASP.NET Core, niektóre :::no-loc text="\"pubternal\""::: interfejsy API lokalizacji zostały usunięte.</span><span class="sxs-lookup"><span data-stu-id="b7501-102">To better maintain the public API surface of ASP.NET Core, some :::no-loc text="\"pubternal\""::: localization APIs were removed.</span></span> <span data-ttu-id="b7501-103">:::no-loc text="\"pubternal\"":::Interfejs API ma `public` modyfikator dostępu i jest zdefiniowany w przestrzeni nazw, która oznacza przeznaczenie [wewnętrzne](../../../../docs/csharp/language-reference/keywords/internal.md) .</span><span class="sxs-lookup"><span data-stu-id="b7501-103">A :::no-loc text="\"pubternal\""::: API has a `public` access modifier and is defined in a namespace that implies an [internal](../../../../docs/csharp/language-reference/keywords/internal.md) intent.</span></span>

<span data-ttu-id="b7501-104">Aby zapoznać się z omówieniem, zobacz [dotnet/aspnetcore # 22291](https://github.com/dotnet/aspnetcore/issues/22291).</span><span class="sxs-lookup"><span data-stu-id="b7501-104">For discussion, see [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b7501-105">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="b7501-105">Version introduced</span></span>

<span data-ttu-id="b7501-106">5,0 wersja zapoznawcza 6</span><span class="sxs-lookup"><span data-stu-id="b7501-106">5.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b7501-107">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="b7501-107">Old behavior</span></span>

<span data-ttu-id="b7501-108">Następujące interfejsy API `public` :</span><span class="sxs-lookup"><span data-stu-id="b7501-108">The following APIs were `public`:</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <span data-ttu-id="b7501-109">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` przeciążenia konstruktora akceptujące jeden z następujących typów parametrów:</span><span class="sxs-lookup"><span data-stu-id="b7501-109">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="new-behavior"></a><span data-ttu-id="b7501-110">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="b7501-110">New behavior</span></span>

<span data-ttu-id="b7501-111">Na poniższej liście przedstawiono zmiany:</span><span class="sxs-lookup"><span data-stu-id="b7501-111">The following list outlines the changes:</span></span>

- <span data-ttu-id="b7501-112">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` stała `Microsoft.Extensions.Localization.AssemblyWrapper` się i jest teraz `internal` .</span><span class="sxs-lookup"><span data-stu-id="b7501-112">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` became `Microsoft.Extensions.Localization.AssemblyWrapper` and is now `internal`.</span></span>
- <span data-ttu-id="b7501-113">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` stała `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` się i jest teraz `internal` .</span><span class="sxs-lookup"><span data-stu-id="b7501-113">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` became `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` and is now `internal`.</span></span>
- <span data-ttu-id="b7501-114">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` przeciążenia konstruktora akceptujące jeden z następujących typów parametrów są teraz `internal` :</span><span class="sxs-lookup"><span data-stu-id="b7501-114">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types are now `internal`:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="reason-for-change"></a><span data-ttu-id="b7501-115">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="b7501-115">Reason for change</span></span>

<span data-ttu-id="b7501-116">Wyjaśniono dokładniej dla [ASPNET/anonsów # 377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), :::no-loc text="\"pubternal\""::: typy zostały usunięte z `public` powierzchni interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="b7501-116">Explained more thoroughly at [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), :::no-loc text="\"pubternal\""::: types were removed from the `public` API surface.</span></span> <span data-ttu-id="b7501-117">Te zmiany dostosowują więcej klas do tej decyzji projektowej.</span><span class="sxs-lookup"><span data-stu-id="b7501-117">These changes adapt more classes to that design decision.</span></span> <span data-ttu-id="b7501-118">Omawiane klasy były przeznaczone jako punkty rozszerzenia dla wewnętrznego testowania zespołu.</span><span class="sxs-lookup"><span data-stu-id="b7501-118">The classes in question were intended as extension points for the team's internal testing.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b7501-119">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="b7501-119">Recommended action</span></span>

<span data-ttu-id="b7501-120">Chociaż jest to mało prawdopodobne, niektóre aplikacje mogą celowo lub przypadkowo zależeć od :::no-loc text="\"pubternal\""::: typów.</span><span class="sxs-lookup"><span data-stu-id="b7501-120">Although it's unlikely, some apps may intentionally or accidentally depend upon the :::no-loc text="\"pubternal\""::: types.</span></span> <span data-ttu-id="b7501-121">Zapoznaj się z nowymi sekcjami [zachowania](#new-behavior) , aby określić, jak przeprowadzić migrację z typów.</span><span class="sxs-lookup"><span data-stu-id="b7501-121">See the [New behavior](#new-behavior) sections to determine how to migrate away from the types.</span></span>

<span data-ttu-id="b7501-122">W przypadku zidentyfikowania scenariusza, który publiczny interfejs API jest dozwolony przed tą zmianą, ale nie teraz, należy rozwiązać problem w programie [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span><span class="sxs-lookup"><span data-stu-id="b7501-122">If you've identified a scenario which the public API allowed before this change but doesn't now, file an issue at [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span></span>

#### <a name="category"></a><span data-ttu-id="b7501-123">Kategoria</span><span class="sxs-lookup"><span data-stu-id="b7501-123">Category</span></span>

<span data-ttu-id="b7501-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7501-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b7501-125">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="b7501-125">Affected APIs</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `T:Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.#ctor`

-->
