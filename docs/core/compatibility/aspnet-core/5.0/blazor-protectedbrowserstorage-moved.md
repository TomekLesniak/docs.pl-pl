---
title: 'Nieprzerwana zmiana: Blazor: funkcja ProtectedBrowserStorage została przeniesiona do platformy udostępnionej'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej Blazor: ProtectedBrowserStorage funkcja została przeniesiona do platformy udostępnionej'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c8058adf8b66aef8dd011ea672cd306ae4de60a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761479"
---
# <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a><span data-ttu-id="30c43-103">Blazor: funkcja ProtectedBrowserStorage została przeniesiona do platformy udostępnionej</span><span class="sxs-lookup"><span data-stu-id="30c43-103">Blazor: ProtectedBrowserStorage feature moved to shared framework</span></span>

<span data-ttu-id="30c43-104">W ramach wersji ASP.NET Core 5,0 RC2 `ProtectedBrowserStorage` funkcja została przeniesiona do ASP.NET Core udostępnionej platformy.</span><span class="sxs-lookup"><span data-stu-id="30c43-104">As part of the ASP.NET Core 5.0 RC2 release, the `ProtectedBrowserStorage` feature moved to the ASP.NET Core shared framework.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="30c43-105">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="30c43-105">Version introduced</span></span>

<span data-ttu-id="30c43-106">5,0 RC2</span><span class="sxs-lookup"><span data-stu-id="30c43-106">5.0 RC2</span></span>

## <a name="old-behavior"></a><span data-ttu-id="30c43-107">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="30c43-107">Old behavior</span></span>

<span data-ttu-id="30c43-108">W ASP.NET Core 5,0 wersja zapoznawcza 8 funkcja jest dostępna jako część pakietu [Microsoft. AspNetCore. Components. Web. Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) , ale była użyteczna tylko w Blazor webassembly.</span><span class="sxs-lookup"><span data-stu-id="30c43-108">In ASP.NET Core 5.0 Preview 8, the feature is available as a part of the [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) package but was only usable in Blazor WebAssembly.</span></span>

<span data-ttu-id="30c43-109">W ASP.NET Core 5,0 RC1 funkcja jest dostępna jako część pakietu [Microsoft. AspNetCore. Components. ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) , który odwołuje się do `Microsoft.AspNetCore.App` udostępnionej platformy.</span><span class="sxs-lookup"><span data-stu-id="30c43-109">In ASP.NET Core 5.0 RC1, the feature is available as part of the [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) package, which references the `Microsoft.AspNetCore.App` shared framework.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="30c43-110">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="30c43-110">New behavior</span></span>

<span data-ttu-id="30c43-111">W ASP.NET Core 5,0 RC2 odwołanie do pakietu NuGet nie jest już potrzebne do odwoływania się do tej funkcji i korzystania z niej.</span><span class="sxs-lookup"><span data-stu-id="30c43-111">In ASP.NET Core 5.0 RC2, a NuGet package reference is no longer needed to reference and use the feature.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="30c43-112">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="30c43-112">Reason for change</span></span>

<span data-ttu-id="30c43-113">Przejście do udostępnionej struktury jest lepszym rozwiązaniem dla klientów środowiska użytkownika.</span><span class="sxs-lookup"><span data-stu-id="30c43-113">The move to the shared framework is a better fit for the user experience customers expect.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="30c43-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="30c43-114">Recommended action</span></span>

<span data-ttu-id="30c43-115">W przypadku uaktualniania z ASP.NET Core 5,0 RC1 wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="30c43-115">If upgrading from ASP.NET Core 5.0 RC1, complete the following steps:</span></span>

1. <span data-ttu-id="30c43-116">Usuń `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` odwołanie do pakietu z projektu.</span><span class="sxs-lookup"><span data-stu-id="30c43-116">Remove the `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` package reference from the project.</span></span>
1. <span data-ttu-id="30c43-117">Zastąp element `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` pytaniem `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="30c43-117">Replace `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="30c43-118">Usuń wywołanie `AddProtectedBrowserStorage` z `Startup` klasy.</span><span class="sxs-lookup"><span data-stu-id="30c43-118">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

<span data-ttu-id="30c43-119">Jeśli uaktualniasz program ASP.NET Core 5,0 w wersji zapoznawczej 8, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="30c43-119">If upgrading from ASP.NET Core 5.0 Preview 8, complete the following steps:</span></span>

1. <span data-ttu-id="30c43-120">Usuń `Microsoft.AspNetCore.Components.Web.Extensions` odwołanie do pakietu z projektu.</span><span class="sxs-lookup"><span data-stu-id="30c43-120">Remove the `Microsoft.AspNetCore.Components.Web.Extensions` package reference from the project.</span></span>
1. <span data-ttu-id="30c43-121">Zastąp element `using Microsoft.AspNetCore.Components.Web.Extensions;` pytaniem `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="30c43-121">Replace `using Microsoft.AspNetCore.Components.Web.Extensions;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="30c43-122">Usuń wywołanie `AddProtectedBrowserStorage` z `Startup` klasy.</span><span class="sxs-lookup"><span data-stu-id="30c43-122">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="30c43-123">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="30c43-123">Affected APIs</span></span>

<span data-ttu-id="30c43-124">Brak</span><span class="sxs-lookup"><span data-stu-id="30c43-124">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
