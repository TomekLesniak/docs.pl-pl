---
title: 'Zmiana podziału: Blazor: docelowa struktura pakietów NuGet została zmieniona'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej Blazor: docelowa struktura pakietów NuGet została zmieniona'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 5515edc66ff9786f0d8f7e24e5fc28c71502567b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761480"
---
# <a name="blazor-target-framework-of-nuget-packages-changed"></a><span data-ttu-id="a9aa1-103">Blazor: zmieniono platformę docelową pakietów NuGet</span><span class="sxs-lookup"><span data-stu-id="a9aa1-103">Blazor: Target framework of NuGet packages changed</span></span>

<span data-ttu-id="a9aa1-104">Skompilowano projekty zestawu webBlazor 3,2 dla elementu docelowego .NET Standard 2,1 ( `<TargetFramework>netstandard2.1</TargetFramework>` ).</span><span class="sxs-lookup"><span data-stu-id="a9aa1-104">Blazor 3.2 WebAssembly projects were compiled to target .NET Standard 2.1 (`<TargetFramework>netstandard2.1</TargetFramework>`).</span></span> <span data-ttu-id="a9aa1-105">W ASP.NET Core 5,0 zarówno projekty Blazor Server i Blazor webassembly są przeznaczone dla platformy .NET 5,0 ( `<TargetFramework>net5.0</TargetFramework>` ).</span><span class="sxs-lookup"><span data-stu-id="a9aa1-105">In ASP.NET Core 5.0, both Blazor Server and Blazor WebAssembly projects target .NET 5.0 (`<TargetFramework>net5.0</TargetFramework>`).</span></span> <span data-ttu-id="a9aa1-106">Aby lepiej dostosować się do zmiany platformy docelowej, następujące pakiety Blazor nie są już docelowe .NET Standard 2,1:</span><span class="sxs-lookup"><span data-stu-id="a9aa1-106">To better align with the target framework change, the following Blazor packages no longer target .NET Standard 2.1:</span></span>

* [<span data-ttu-id="a9aa1-107">Microsoft. AspNetCore. Components</span><span class="sxs-lookup"><span data-stu-id="a9aa1-107">Microsoft.AspNetCore.Components</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components)
* [<span data-ttu-id="a9aa1-108">Microsoft. AspNetCore. Components. Authorization</span><span class="sxs-lookup"><span data-stu-id="a9aa1-108">Microsoft.AspNetCore.Components.Authorization</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Authorization)
* [<span data-ttu-id="a9aa1-109">Microsoft. AspNetCore. Components. Forms</span><span class="sxs-lookup"><span data-stu-id="a9aa1-109">Microsoft.AspNetCore.Components.Forms</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Forms)
* [<span data-ttu-id="a9aa1-110">Microsoft. AspNetCore. Components. Web</span><span class="sxs-lookup"><span data-stu-id="a9aa1-110">Microsoft.AspNetCore.Components.Web</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web)
* [<span data-ttu-id="a9aa1-111">Microsoft. AspNetCore. Components. webassembly</span><span class="sxs-lookup"><span data-stu-id="a9aa1-111">Microsoft.AspNetCore.Components.WebAssembly</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly)
* [<span data-ttu-id="a9aa1-112">Microsoft. AspNetCore. Components. webassembly. Authentication</span><span class="sxs-lookup"><span data-stu-id="a9aa1-112">Microsoft.AspNetCore.Components.WebAssembly.Authentication</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly.Authentication)
* [<span data-ttu-id="a9aa1-113">Microsoft.JSmiędzyoperacyjny</span><span class="sxs-lookup"><span data-stu-id="a9aa1-113">Microsoft.JSInterop</span></span>](https://www.nuget.org/packages/Microsoft.JSInterop)
* [<span data-ttu-id="a9aa1-114">Microsoft.JSInterop. webassembly</span><span class="sxs-lookup"><span data-stu-id="a9aa1-114">Microsoft.JSInterop.WebAssembly</span></span>](https://www.nuget.org/packages/Microsoft.JSInterop.WebAssembly)
* [<span data-ttu-id="a9aa1-115">Microsoft. Authentication. webassembly. Msal</span><span class="sxs-lookup"><span data-stu-id="a9aa1-115">Microsoft.Authentication.WebAssembly.Msal</span></span>](https://www.nuget.org/packages/Microsoft.Authentication.WebAssembly.Msal)

<span data-ttu-id="a9aa1-116">Aby zapoznać się z omówieniem, zobacz sekcję dotyczącą usługi GitHub wydaj [/aspnetcore # 23424](https://github.com/dotnet/aspnetcore/issues/23424).</span><span class="sxs-lookup"><span data-stu-id="a9aa1-116">For discussion, see GitHub issue [dotnet/aspnetcore#23424](https://github.com/dotnet/aspnetcore/issues/23424).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="a9aa1-117">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="a9aa1-117">Version introduced</span></span>

<span data-ttu-id="a9aa1-118">5,0 wersja zapoznawcza 7</span><span class="sxs-lookup"><span data-stu-id="a9aa1-118">5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="a9aa1-119">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="a9aa1-119">Old behavior</span></span>

<span data-ttu-id="a9aa1-120">W Blazor 3,1 i 3,2 pakiety są przeznaczone dla .NET Standard 2,1 i .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-120">In Blazor 3.1 and 3.2, packages target .NET Standard 2.1 and .NET Core 3.1.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="a9aa1-121">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="a9aa1-121">New behavior</span></span>

<span data-ttu-id="a9aa1-122">W ASP.NET Core 5,0 pakiety są przeznaczone dla platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-122">In ASP.NET Core 5.0, packages target .NET 5.0.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="a9aa1-123">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="a9aa1-123">Reason for change</span></span>

<span data-ttu-id="a9aa1-124">Wprowadzono zmiany w celu lepszego dostosowania z wymaganiami programu .NET Target Framework.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-124">The change was made to better align with .NET target framework requirements.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a9aa1-125">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="a9aa1-125">Recommended action</span></span>

<span data-ttu-id="a9aa1-126">Projekty zestawu webassembly Blazor 3,2 powinny kierować platformą .NET 5,0 w ramach aktualizowania odwołań do pakietów do 5. x.x.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-126">Blazor 3.2 WebAssembly projects should target .NET 5.0 as part of updating their package references to 5.x.x.</span></span> <span data-ttu-id="a9aa1-127">Biblioteki odwołujące się do jednego z tych pakietów mogą wskazywać na platformę .NET 5,0 lub wiele obiektów docelowych w zależności od ich wymagań.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-127">Libraries that reference one of these packages can either target .NET 5.0 or multi-target depending on their requirements.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="a9aa1-128">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="a9aa1-128">Affected APIs</span></span>

<span data-ttu-id="a9aa1-129">Brak</span><span class="sxs-lookup"><span data-stu-id="a9aa1-129">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
