---
ms.openlocfilehash: 584014572ab799e1e3ab2f02c9fbf4fe6b0c17e7
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804932"
---
### <a name="blazor-updated-browser-support"></a><span data-ttu-id="aaa6f-101">Blazor: Zaktualizowano obsługę przeglądarki</span><span class="sxs-lookup"><span data-stu-id="aaa6f-101">Blazor: Updated browser support</span></span>

<span data-ttu-id="aaa6f-102">W ASP.NET Core 5,0 wprowadzono [nowe funkcje Blazor](https://github.com/dotnet/aspnetcore/issues/21514), a niektóre z nich są niezgodne ze starszymi przeglądarkami.</span><span class="sxs-lookup"><span data-stu-id="aaa6f-102">ASP.NET Core 5.0 introduces [new Blazor features](https://github.com/dotnet/aspnetcore/issues/21514), some of which are incompatible with older browsers.</span></span> <span data-ttu-id="aaa6f-103">Lista przeglądarek obsługiwanych przez Blazor w ASP.NET Core 5,0 została odpowiednio zaktualizowana.</span><span class="sxs-lookup"><span data-stu-id="aaa6f-103">The list of browsers supported by Blazor in ASP.NET Core 5.0 has been updated accordingly.</span></span>

<span data-ttu-id="aaa6f-104">Aby zapoznać się z omówieniem, zobacz sekcję dotyczącą usługi GitHub wydaj [/aspnetcore # 26475](https://github.com/dotnet/aspnetcore/issues/26475).</span><span class="sxs-lookup"><span data-stu-id="aaa6f-104">For discussion, see GitHub issue [dotnet/aspnetcore#26475](https://github.com/dotnet/aspnetcore/issues/26475).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="aaa6f-105">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="aaa6f-105">Version introduced</span></span>

<span data-ttu-id="aaa6f-106">5,0</span><span class="sxs-lookup"><span data-stu-id="aaa6f-106">5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="aaa6f-107">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="aaa6f-107">Old behavior</span></span>

<span data-ttu-id="aaa6f-108">Serwer Blazor obsługuje program Microsoft Internet Explorer 11 z odpowiednimi wypełnieniami.</span><span class="sxs-lookup"><span data-stu-id="aaa6f-108">Blazor Server supports Microsoft Internet Explorer 11 with sufficient polyfills.</span></span> <span data-ttu-id="aaa6f-109">Blazor Server i Blazor webassembly działają również w [starszej wersji programu Microsoft Edge](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy).</span><span class="sxs-lookup"><span data-stu-id="aaa6f-109">Blazor Server and Blazor WebAssembly are also functional in [Microsoft Edge Legacy](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy).</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="aaa6f-110">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="aaa6f-110">New behavior</span></span>

<span data-ttu-id="aaa6f-111">Serwer Blazor w ASP.NET Core 5,0 nie jest obsługiwany przez program Microsoft Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="aaa6f-111">Blazor Server in ASP.NET Core 5.0 isn't supported with Microsoft Internet Explorer 11.</span></span> <span data-ttu-id="aaa6f-112">Blazor Server i Blazor webassembly nie działają w pełni ze starszymi wersjami programu Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="aaa6f-112">Blazor Server and Blazor WebAssembly aren't fully functional in Microsoft Edge Legacy.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="aaa6f-113">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="aaa6f-113">Reason for change</span></span>

<span data-ttu-id="aaa6f-114">Nowe funkcje Blazor w ASP.NET Core 5,0 są niezgodne ze starszymi przeglądarkami, a korzystanie z tych starszych przeglądarek jest zmniejszane.</span><span class="sxs-lookup"><span data-stu-id="aaa6f-114">New Blazor features in ASP.NET Core 5.0 are incompatible with these older browsers, and use of these older browsers is diminishing.</span></span> <span data-ttu-id="aaa6f-115">Więcej informacji można znaleźć w następujących zasobach:</span><span class="sxs-lookup"><span data-stu-id="aaa6f-115">For more information, see the following resources:</span></span>

* [<span data-ttu-id="aaa6f-116">Obsługa systemu Windows dla starszej wersji programu Microsoft Edge kończy się również 9 marca 2021</span><span class="sxs-lookup"><span data-stu-id="aaa6f-116">Windows support for Microsoft Edge Legacy is also ending on March 9, 2021</span></span>](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy)
* [<span data-ttu-id="aaa6f-117">Microsoft 365 aplikacje i usługi zakończą obsługę programu Microsoft Internet Explorer 11 do 17 sierpnia 2021</span><span class="sxs-lookup"><span data-stu-id="aaa6f-117">Microsoft 365 apps and services will end support for Microsoft Internet Explorer 11 by August 17, 2021</span></span>](/lifecycle/announcements/m365-ie11-microsoft-edge-legacy)

#### <a name="recommended-action"></a><span data-ttu-id="aaa6f-118">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="aaa6f-118">Recommended action</span></span>

<span data-ttu-id="aaa6f-119">Uaktualnij te starsze przeglądarki do [nowej, opartej na formacie chromu Microsoft Edge](https://www.microsoft.com/edge).</span><span class="sxs-lookup"><span data-stu-id="aaa6f-119">Upgrade from these older browsers to the [new, Chromium-based Microsoft Edge](https://www.microsoft.com/edge).</span></span> <span data-ttu-id="aaa6f-120">W przypadku aplikacji Blazor, które muszą obsługiwać te starsze przeglądarki, użyj ASP.NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="aaa6f-120">For Blazor apps that need to support these older browsers, use ASP.NET Core 3.1.</span></span> <span data-ttu-id="aaa6f-121">Lista obsługiwanych przeglądarek dla Blazor w ASP.NET Core 3,1 nie zmieniła się i została udokumentowana na [obsługiwanych platformach](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1).</span><span class="sxs-lookup"><span data-stu-id="aaa6f-121">The supported browsers list for Blazor in ASP.NET Core 3.1 hasn't changed and is documented at [Supported platforms](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1).</span></span>

#### <a name="category"></a><span data-ttu-id="aaa6f-122">Kategoria</span><span class="sxs-lookup"><span data-stu-id="aaa6f-122">Category</span></span>

<span data-ttu-id="aaa6f-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="aaa6f-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="aaa6f-124">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="aaa6f-124">Affected APIs</span></span>

<span data-ttu-id="aaa6f-125">Brak</span><span class="sxs-lookup"><span data-stu-id="aaa6f-125">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
