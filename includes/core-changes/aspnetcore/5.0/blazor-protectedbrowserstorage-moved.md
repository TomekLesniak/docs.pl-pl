---
ms.openlocfilehash: a9545c66d3873b5114fe66e13c77ddc28e20020e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077608"
---
### <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a><span data-ttu-id="57dae-101">Blazor: funkcja ProtectedBrowserStorage została przeniesiona do platformy udostępnionej</span><span class="sxs-lookup"><span data-stu-id="57dae-101">Blazor: ProtectedBrowserStorage feature moved to shared framework</span></span>

<span data-ttu-id="57dae-102">W ramach wersji ASP.NET Core 5,0 RC2 `ProtectedBrowserStorage` funkcja została przeniesiona do ASP.NET Core udostępnionej platformy.</span><span class="sxs-lookup"><span data-stu-id="57dae-102">As part of the ASP.NET Core 5.0 RC2 release, the `ProtectedBrowserStorage` feature moved to the ASP.NET Core shared framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="57dae-103">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="57dae-103">Version introduced</span></span>

<span data-ttu-id="57dae-104">5,0 RC2</span><span class="sxs-lookup"><span data-stu-id="57dae-104">5.0 RC2</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="57dae-105">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="57dae-105">Old behavior</span></span>

<span data-ttu-id="57dae-106">W ASP.NET Core 5,0 wersja zapoznawcza 8 funkcja jest dostępna jako część pakietu [Microsoft. AspNetCore. Components. Web. Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) , ale była użyteczna tylko w Blazor webassembly.</span><span class="sxs-lookup"><span data-stu-id="57dae-106">In ASP.NET Core 5.0 Preview 8, the feature is available as a part of the [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) package but was only usable in Blazor WebAssembly.</span></span>

<span data-ttu-id="57dae-107">W ASP.NET Core 5,0 RC1 funkcja jest dostępna jako część pakietu [Microsoft. AspNetCore. Components. ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) , który odwołuje się do `Microsoft.AspNetCore.App` udostępnionej platformy.</span><span class="sxs-lookup"><span data-stu-id="57dae-107">In ASP.NET Core 5.0 RC1, the feature is available as part of the [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) package, which references the `Microsoft.AspNetCore.App` shared framework.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="57dae-108">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="57dae-108">New behavior</span></span>

<span data-ttu-id="57dae-109">W ASP.NET Core 5,0 RC2 odwołanie do pakietu NuGet nie jest już potrzebne do odwoływania się do tej funkcji i korzystania z niej.</span><span class="sxs-lookup"><span data-stu-id="57dae-109">In ASP.NET Core 5.0 RC2, a NuGet package reference is no longer needed to reference and use the feature.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="57dae-110">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="57dae-110">Reason for change</span></span>

<span data-ttu-id="57dae-111">Przejście do udostępnionej struktury jest lepszym rozwiązaniem dla klientów środowiska użytkownika.</span><span class="sxs-lookup"><span data-stu-id="57dae-111">The move to the shared framework is a better fit for the user experience customers expect.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="57dae-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="57dae-112">Recommended action</span></span>

<span data-ttu-id="57dae-113">W przypadku uaktualniania z ASP.NET Core 5,0 RC1 wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="57dae-113">If upgrading from ASP.NET Core 5.0 RC1, complete the following steps:</span></span>

1. <span data-ttu-id="57dae-114">Usuń `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` odwołanie do pakietu z projektu.</span><span class="sxs-lookup"><span data-stu-id="57dae-114">Remove the `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` package reference from the project.</span></span>
1. <span data-ttu-id="57dae-115">Zastąp element `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` pytaniem `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="57dae-115">Replace `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="57dae-116">Usuń wywołanie `AddProtectedBrowserStorage` z `Startup` klasy.</span><span class="sxs-lookup"><span data-stu-id="57dae-116">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

<span data-ttu-id="57dae-117">Jeśli uaktualniasz program ASP.NET Core 5,0 w wersji zapoznawczej 8, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="57dae-117">If upgrading from ASP.NET Core 5.0 Preview 8, complete the following steps:</span></span>

1. <span data-ttu-id="57dae-118">Usuń `Microsoft.AspNetCore.Components.Web.Extensions` odwołanie do pakietu z projektu.</span><span class="sxs-lookup"><span data-stu-id="57dae-118">Remove the `Microsoft.AspNetCore.Components.Web.Extensions` package reference from the project.</span></span>
1. <span data-ttu-id="57dae-119">Zastąp element `using Microsoft.AspNetCore.Components.Web.Extensions;` pytaniem `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="57dae-119">Replace `using Microsoft.AspNetCore.Components.Web.Extensions;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="57dae-120">Usuń wywołanie `AddProtectedBrowserStorage` z `Startup` klasy.</span><span class="sxs-lookup"><span data-stu-id="57dae-120">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

#### <a name="category"></a><span data-ttu-id="57dae-121">Kategoria</span><span class="sxs-lookup"><span data-stu-id="57dae-121">Category</span></span>

<span data-ttu-id="57dae-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="57dae-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="57dae-123">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="57dae-123">Affected APIs</span></span>

<span data-ttu-id="57dae-124">Brak</span><span class="sxs-lookup"><span data-stu-id="57dae-124">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
