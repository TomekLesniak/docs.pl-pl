---
title: 'Nieprzerwana zmiana: sygnalizująca: UseSignalR i UseConnections metody'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 z tytułem: metody UseSignalR i UseConnections zostały usunięte'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 1b1fce04518e69927cdc1650cc1e19107cc81e3b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761404"
---
# <a name="signalr-usesignalr-and-useconnections-methods-removed"></a><span data-ttu-id="940e6-103">Sygnalizacja: Usunięto metody UseSignalR i UseConnections</span><span class="sxs-lookup"><span data-stu-id="940e6-103">SignalR: UseSignalR and UseConnections methods removed</span></span>

<span data-ttu-id="940e6-104">W ASP.NET Core 3,0, sygnalizujący przyjął Routing punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="940e6-104">In ASP.NET Core 3.0, SignalR adopted endpoint routing.</span></span> <span data-ttu-id="940e6-105">W ramach tej zmiany,, <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A> <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A> i niektóre powiązane metody zostały oznaczone jako przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="940e6-105">As part of that change, the <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A>, and some related methods were marked as obsolete.</span></span> <span data-ttu-id="940e6-106">W ASP.NET Core 5,0 te przestarzałe metody zostały usunięte.</span><span class="sxs-lookup"><span data-stu-id="940e6-106">In ASP.NET Core 5.0, those obsolete methods were removed.</span></span> <span data-ttu-id="940e6-107">Aby zapoznać się z pełną listą metod, zobacz [interfejsy API, których to dotyczy](#affected-apis).</span><span class="sxs-lookup"><span data-stu-id="940e6-107">For the full list of methods, see [Affected APIs](#affected-apis).</span></span>

<span data-ttu-id="940e6-108">Aby zapoznać się z omówieniem tego problemu, zobacz [dotnet/aspnetcore # 20082](https://github.com/dotnet/aspnetcore/issues/20082).</span><span class="sxs-lookup"><span data-stu-id="940e6-108">For discussion on this issue, see [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="940e6-109">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="940e6-109">Version introduced</span></span>

<span data-ttu-id="940e6-110">5,0 — wersja zapoznawcza 3</span><span class="sxs-lookup"><span data-stu-id="940e6-110">5.0 Preview 3</span></span>

## <a name="old-behavior"></a><span data-ttu-id="940e6-111">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="940e6-111">Old behavior</span></span>

<span data-ttu-id="940e6-112">Centra sygnałów i programy obsługi połączeń mogą być rejestrowane w potoku pośredniczącym przy użyciu `UseSignalR` metod lub `UseConnections` .</span><span class="sxs-lookup"><span data-stu-id="940e6-112">SignalR hubs and connection handlers could be registered in the middleware pipeline using the `UseSignalR` or `UseConnections` methods.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="940e6-113">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="940e6-113">New behavior</span></span>

<span data-ttu-id="940e6-114">Centra sygnałów i programy obsługi połączeń powinny być zarejestrowane w ramach <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> przy użyciu <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> metod rozszerzenia i <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder> .</span><span class="sxs-lookup"><span data-stu-id="940e6-114">SignalR hubs and connection handlers should be registered within <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> using the <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> and <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> extension methods on <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="940e6-115">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="940e6-115">Reason for change</span></span>

<span data-ttu-id="940e6-116">Stare metody miały niestandardową logikę routingu, która nie współdziała z innymi składnikami routingu w ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="940e6-116">The old methods had custom routing logic that didn't interact with other routing components in ASP.NET Core.</span></span> <span data-ttu-id="940e6-117">W ASP.NET Core 3,0 wprowadzono nowy system routingu ogólnego przeznaczenia o nazwie Routing punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="940e6-117">In ASP.NET Core 3.0, a new general-purpose routing system, called endpoint routing, was introduced.</span></span> <span data-ttu-id="940e6-118">Sygnalizacja włączonego routingu punktu końcowego do współpracy z innymi składnikami routingu.</span><span class="sxs-lookup"><span data-stu-id="940e6-118">Endpoint routing enabled SignalR to interact with other routing components.</span></span> <span data-ttu-id="940e6-119">Przełączenie do tego modelu pozwala użytkownikom na korzystanie z pełnych korzyści z routingu punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="940e6-119">Switching to this model allows users to realize the full benefits of endpoint routing.</span></span> <span data-ttu-id="940e6-120">W związku z tym stare metody zostały usunięte.</span><span class="sxs-lookup"><span data-stu-id="940e6-120">Consequently, the old methods have been removed.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="940e6-121">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="940e6-121">Recommended action</span></span>

<span data-ttu-id="940e6-122">Usuń kod, który wywołuje `UseSignalR` lub `UseConnections` z metody projektu `Startup.Configure` .</span><span class="sxs-lookup"><span data-stu-id="940e6-122">Remove code that calls `UseSignalR` or `UseConnections` from your project's `Startup.Configure` method.</span></span> <span data-ttu-id="940e6-123">Zastąp go wywołaniami `MapHub` lub `MapConnectionHandler` odpowiednio w treści wywołania do `UseEndpoints` .</span><span class="sxs-lookup"><span data-stu-id="940e6-123">Replace it with calls to `MapHub` or `MapConnectionHandler`, respectively, within the body of a call to `UseEndpoints`.</span></span> <span data-ttu-id="940e6-124">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="940e6-124">For example:</span></span>

<span data-ttu-id="940e6-125">**Stary kod:**</span><span class="sxs-lookup"><span data-stu-id="940e6-125">**Old code:**</span></span>

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="940e6-126">**Nowy kod:**</span><span class="sxs-lookup"><span data-stu-id="940e6-126">**New code:**</span></span>

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="940e6-127">Ogólnie rzecz biorąc poprzednie `MapHub` i `MapConnectionHandler` wywołania można przenieść bezpośrednio z treści `UseSignalR` i `UseConnections` do `UseEndpoints` z niezbędną zmianą.</span><span class="sxs-lookup"><span data-stu-id="940e6-127">In general, your previous `MapHub` and `MapConnectionHandler` calls can be transferred directly from the body of `UseSignalR` and `UseConnections` to `UseEndpoints` with little-to-no change needed.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="940e6-128">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="940e6-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections`
- `Overload:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler`
- `Overload:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub`

-->
