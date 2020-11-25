---
title: 'Istotna zmiana: Autoryzacja: zasób w routingu punktu końcowego jest obiektem HttpContext'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej autoryzacja: zasób w routingu punktu końcowego jest obiektem HttpContext'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 7c5a77cb8999c60a7780b9b4f7ad2a1c79fd8310
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761676"
---
# <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a><span data-ttu-id="326b3-103">Autoryzacja: zasób w routingu punktu końcowego jest obiektem HttpContext</span><span class="sxs-lookup"><span data-stu-id="326b3-103">Authorization: Resource in endpoint routing is HttpContext</span></span>

<span data-ttu-id="326b3-104">W przypadku korzystania z routingu punktów końcowych w ASP.NET Core 3,1, zasób używany do autoryzacji jest punktem końcowym.</span><span class="sxs-lookup"><span data-stu-id="326b3-104">When using endpoint routing in ASP.NET Core 3.1, the resource used for authorization is the endpoint.</span></span> <span data-ttu-id="326b3-105">Takie podejście było niewystarczające do uzyskania dostępu do danych trasy ( <xref:Microsoft.AspNetCore.Routing.RouteData> ).</span><span class="sxs-lookup"><span data-stu-id="326b3-105">This approach was insufficient for gaining access to the route data (<xref:Microsoft.AspNetCore.Routing.RouteData>).</span></span> <span data-ttu-id="326b3-106">Wcześniej w MVC <xref:Microsoft.AspNetCore.Http.HttpContext> zasób został przekazano, co umożliwia dostęp do punktu końcowego ( <xref:Microsoft.AspNetCore.Http.Endpoint> ) i danych trasy.</span><span class="sxs-lookup"><span data-stu-id="326b3-106">Previously in MVC, an <xref:Microsoft.AspNetCore.Http.HttpContext> resource was passed in, which allows access to both the endpoint (<xref:Microsoft.AspNetCore.Http.Endpoint>) and the route data.</span></span> <span data-ttu-id="326b3-107">Ta zmiana gwarantuje, że zasób przeszedł do autoryzacji jest zawsze `HttpContext` .</span><span class="sxs-lookup"><span data-stu-id="326b3-107">This change ensures that the resource passed to authorization is always the `HttpContext`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="326b3-108">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="326b3-108">Version introduced</span></span>

<span data-ttu-id="326b3-109">5,0 wersja zapoznawcza 7</span><span class="sxs-lookup"><span data-stu-id="326b3-109">5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="326b3-110">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="326b3-110">Old behavior</span></span>

<span data-ttu-id="326b3-111">W przypadku używania routingu punktów końcowych i atrybutów autoryzacji oprogramowania pośredniczącego ( <xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware> ) lub [[autoryzuje]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) zasób przeszedł do autoryzacji jest zgodnym punktem końcowym.</span><span class="sxs-lookup"><span data-stu-id="326b3-111">When using endpoint routing and the authorization middleware (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) or [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) attributes, the resource passed to authorization is the matching endpoint.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="326b3-112">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="326b3-112">New behavior</span></span>

<span data-ttu-id="326b3-113">Routing punktów końcowych przekazuje `HttpContext` do autoryzacji.</span><span class="sxs-lookup"><span data-stu-id="326b3-113">Endpoint routing passes the `HttpContext` to authorization.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="326b3-114">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="326b3-114">Reason for change</span></span>

<span data-ttu-id="326b3-115">Możesz przejść do punktu końcowego z `HttpContext` .</span><span class="sxs-lookup"><span data-stu-id="326b3-115">You can get to the endpoint from the `HttpContext`.</span></span> <span data-ttu-id="326b3-116">Nie ma jednak możliwości uzyskania od punktu końcowego do elementów, takich jak dane trasy.</span><span class="sxs-lookup"><span data-stu-id="326b3-116">However, there was no way to get from the endpoint to things like the route data.</span></span> <span data-ttu-id="326b3-117">Nastąpiła utrata funkcjonalności z poziomu routingu spoza punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="326b3-117">There was a loss in functionality from non-endpoint routing.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="326b3-118">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="326b3-118">Recommended action</span></span>

<span data-ttu-id="326b3-119">Jeśli aplikacja korzysta z zasobu punktu końcowego, wywołaj polecenie, <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> `HttpContext` Aby kontynuować dostęp do punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="326b3-119">If your app uses the endpoint resource, call <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> on the `HttpContext` to continue accessing the endpoint.</span></span>

<span data-ttu-id="326b3-120">W ASP.NET Core 5,0 wersji zapoznawczej 8 i nowszych można przywrócić stare zachowanie przy użyciu programu <xref:System.AppContext.SetSwitch%2A> .</span><span class="sxs-lookup"><span data-stu-id="326b3-120">In ASP.NET Core 5.0 Preview 8 and later, you can revert to the old behavior with <xref:System.AppContext.SetSwitch%2A>.</span></span> <span data-ttu-id="326b3-121">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="326b3-121">For example:</span></span>

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

## <a name="affected-apis"></a><span data-ttu-id="326b3-122">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="326b3-122">Affected APIs</span></span>

<span data-ttu-id="326b3-123">Brak</span><span class="sxs-lookup"><span data-stu-id="326b3-123">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
