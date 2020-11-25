---
title: 'Istotna zmiana: rozszerzenia: zmiany odwołania do pakietów wpływające na niektóre pakiety NuGet'
description: 'Dowiedz się więcej o nieistotnej zmianie w 5,0 ASP.NET Core rozszerzenia zatytułowane: zmiany odwołania do pakietów wpływające na niektóre pakiety NuGet'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 4a525d9f7aad4409fd507fcf80c00968ff4b63d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761475"
---
# <a name="extensions-package-reference-changes-affecting-some-nuget-packages"></a><span data-ttu-id="471fe-103">Rozszerzenia: zmiany odwołania do pakietów wpływające na niektóre pakiety NuGet</span><span class="sxs-lookup"><span data-stu-id="471fe-103">Extensions: Package reference changes affecting some NuGet packages</span></span>

<span data-ttu-id="471fe-104">Po przeprowadzeniu migracji niektórych `Microsoft.Extensions.*` pakietów NuGet z repozytorium [dotnet/Extensions](https://github.com/dotnet/extensions) do programu [dotnet/Runtime](https://github.com/dotnet/runtime), zgodnie z opisem w polu [ASPNET/anonse # 411](https://github.com/aspnet/Announcements/issues/411), zmiany pakietów są stosowane do niektórych migrowanych pakietów.</span><span class="sxs-lookup"><span data-stu-id="471fe-104">With the migration of some `Microsoft.Extensions.*` NuGet packages from the [dotnet/extensions](https://github.com/dotnet/extensions) repository to [dotnet/runtime](https://github.com/dotnet/runtime), as described in [aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411), packaging changes are being applied to some of the migrated packages.</span></span> <span data-ttu-id="471fe-105">Aby zapoznać się z omówieniem tego problemu, zobacz [dotnet/aspnetcore # 21033](https://github.com/dotnet/aspnetcore/issues/21033).</span><span class="sxs-lookup"><span data-stu-id="471fe-105">For discussion on this issue, see [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="471fe-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="471fe-106">Version introduced</span></span>

<span data-ttu-id="471fe-107">5,0 wersja zapoznawcza 4</span><span class="sxs-lookup"><span data-stu-id="471fe-107">5.0 Preview 4</span></span>

## <a name="old-behavior"></a><span data-ttu-id="471fe-108">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="471fe-108">Old behavior</span></span>

<span data-ttu-id="471fe-109">Niektóre `Microsoft.Extensions.*` pakiety zawierają odwołania do pakietów dla interfejsów API, na których opiera się Twoja aplikacja.</span><span class="sxs-lookup"><span data-stu-id="471fe-109">Some `Microsoft.Extensions.*` packages included package references for APIs on which your app relied.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="471fe-110">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="471fe-110">New behavior</span></span>

<span data-ttu-id="471fe-111">Być może aplikacja będzie musiała dodać `Microsoft.Extensions.*` zależności pakietu.</span><span class="sxs-lookup"><span data-stu-id="471fe-111">Your app may have to add `Microsoft.Extensions.*` package dependencies.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="471fe-112">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="471fe-112">Reason for change</span></span>

<span data-ttu-id="471fe-113">Zasady pakowania zostały zaktualizowane w celu lepszego dopasowania do repozytorium *dotnet/Runtime* .</span><span class="sxs-lookup"><span data-stu-id="471fe-113">Packaging policies were updated to better align with the *dotnet/runtime* repository.</span></span> <span data-ttu-id="471fe-114">W ramach nowych zasad odwołania do nieużywanych pakietów są usuwane z plików *. nupkg* podczas tworzenia pakietów.</span><span class="sxs-lookup"><span data-stu-id="471fe-114">Under the new policy, unused package references are removed from *.nupkg* files during packaging.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="471fe-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="471fe-115">Recommended action</span></span>

<span data-ttu-id="471fe-116">Konsumenci pakietów, których to dotyczy, powinni dodać bezpośrednią zależność do usuniętej zależności pakietu w projekcie, jeśli są używane interfejsy API z usuniętej zależności pakietu.</span><span class="sxs-lookup"><span data-stu-id="471fe-116">Consumers of the affected packages should add a direct dependency on the removed package dependency in their project if APIs from removed package dependency are used.</span></span> <span data-ttu-id="471fe-117">W poniższej tabeli wymieniono odnośne pakiety i odpowiednie zmiany.</span><span class="sxs-lookup"><span data-stu-id="471fe-117">The following table lists the affected packages and the corresponding changes.</span></span>

|<span data-ttu-id="471fe-118">Nazwa pakietu</span><span class="sxs-lookup"><span data-stu-id="471fe-118">Package name</span></span>|<span data-ttu-id="471fe-119">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="471fe-119">Change description</span></span>|
|------------|------------------|
|[<span data-ttu-id="471fe-120">Microsoft.Extensions.Configwersja. Obiekt</span><span class="sxs-lookup"><span data-stu-id="471fe-120">Microsoft.Extensions.Configuration.Binder</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Binder)|<span data-ttu-id="471fe-121">Usunięto odwołanie do `Microsoft.Extensions.Configuration`</span><span class="sxs-lookup"><span data-stu-id="471fe-121">Removed reference to `Microsoft.Extensions.Configuration`</span></span>|
|[<span data-ttu-id="471fe-122">Microsoft.Extensions.Configuration.Jsna</span><span class="sxs-lookup"><span data-stu-id="471fe-122">Microsoft.Extensions.Configuration.Json</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Json)    |<span data-ttu-id="471fe-123">Usunięto odwołanie do `System.Threading.Tasks.Extensions`</span><span class="sxs-lookup"><span data-stu-id="471fe-123">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="471fe-124">Microsoft. Extensions. host. Abstracts</span><span class="sxs-lookup"><span data-stu-id="471fe-124">Microsoft.Extensions.Hosting.Abstractions</span></span>](https://nuget.org/packages/Microsoft.Extensions.Hosting.Abstractions)|<span data-ttu-id="471fe-125">Usunięto odwołanie do `Microsoft.Extensions.Logging.Abstractions`</span><span class="sxs-lookup"><span data-stu-id="471fe-125">Removed reference to `Microsoft.Extensions.Logging.Abstractions`</span></span>|
|[<span data-ttu-id="471fe-126">Microsoft.Extensions.Logging</span><span class="sxs-lookup"><span data-stu-id="471fe-126">Microsoft.Extensions.Logging</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging)                          |<span data-ttu-id="471fe-127">Usunięto odwołanie do `Microsoft.Extensions.Configuration.Binder`</span><span class="sxs-lookup"><span data-stu-id="471fe-127">Removed reference to `Microsoft.Extensions.Configuration.Binder`</span></span>|
|[<span data-ttu-id="471fe-128">Microsoft. Extensions. Logging. Console</span><span class="sxs-lookup"><span data-stu-id="471fe-128">Microsoft.Extensions.Logging.Console</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.Console)          |<span data-ttu-id="471fe-129">Usunięto odwołanie do `Microsoft.Extensions.Configuration.Abstractions`</span><span class="sxs-lookup"><span data-stu-id="471fe-129">Removed reference to `Microsoft.Extensions.Configuration.Abstractions`</span></span>|
|[<span data-ttu-id="471fe-130">Microsoft. Extensions. Logging. EventLog</span><span class="sxs-lookup"><span data-stu-id="471fe-130">Microsoft.Extensions.Logging.EventLog</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventLog)        |<span data-ttu-id="471fe-131">Usunięto odwołanie do `System.Diagnostics.EventLog` dla monikera platformy docelowej .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="471fe-131">Removed reference to `System.Diagnostics.EventLog` for the .NET Framework 4.6.1 target framework moniker</span></span>|
|[<span data-ttu-id="471fe-132">Microsoft. Extensions. Logging. EventSource</span><span class="sxs-lookup"><span data-stu-id="471fe-132">Microsoft.Extensions.Logging.EventSource</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventSource)  |<span data-ttu-id="471fe-133">Usunięto odwołanie do `System.Threading.Tasks.Extensions`</span><span class="sxs-lookup"><span data-stu-id="471fe-133">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="471fe-134">Microsoft. Extensions. Opcje</span><span class="sxs-lookup"><span data-stu-id="471fe-134">Microsoft.Extensions.Options</span></span>](https://nuget.org/packages/Microsoft.Extensions.Options)                          |<span data-ttu-id="471fe-135">Usunięto odwołanie do `System.ComponentModel.Annotations`</span><span class="sxs-lookup"><span data-stu-id="471fe-135">Removed reference to `System.ComponentModel.Annotations`</span></span>|

<span data-ttu-id="471fe-136">Na przykład odwołanie do pakietu `Microsoft.Extensions.Configuration` zostało usunięte z `Microsoft.Extensions.Configuration.Binder` .</span><span class="sxs-lookup"><span data-stu-id="471fe-136">For example, the package reference to `Microsoft.Extensions.Configuration` was removed from `Microsoft.Extensions.Configuration.Binder`.</span></span> <span data-ttu-id="471fe-137">W pakiecie nie użyto interfejsu API z zależności.</span><span class="sxs-lookup"><span data-stu-id="471fe-137">No API from the dependency was used in the package.</span></span> <span data-ttu-id="471fe-138">Użytkownicy `Microsoft.Extensions.Configuration.Binder` , którzy zależą od interfejsów API, `Microsoft.Extensions.Configuration` powinni dodać bezpośrednie odwołanie do niego w swoim projekcie.</span><span class="sxs-lookup"><span data-stu-id="471fe-138">Users of `Microsoft.Extensions.Configuration.Binder` who depend on APIs from `Microsoft.Extensions.Configuration` should add a direct reference to it in their project.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="471fe-139">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="471fe-139">Affected APIs</span></span>

<span data-ttu-id="471fe-140">Brak</span><span class="sxs-lookup"><span data-stu-id="471fe-140">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
