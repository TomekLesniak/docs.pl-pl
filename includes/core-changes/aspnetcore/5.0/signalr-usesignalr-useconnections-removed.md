---
ms.openlocfilehash: 329ef39c7626ecd743577f336a4c8cd4a38fb082
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291637"
---
### <a name="signalr-usesignalr-and-useconnections-methods-removed"></a><span data-ttu-id="37c3e-101">Sygnalizacja: Usunięto metody UseSignalR i UseConnections</span><span class="sxs-lookup"><span data-stu-id="37c3e-101">SignalR: UseSignalR and UseConnections methods removed</span></span>

<span data-ttu-id="37c3e-102">W ASP.NET Core 3,0, sygnalizujący przyjął Routing punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="37c3e-102">In ASP.NET Core 3.0, SignalR adopted endpoint routing.</span></span> <span data-ttu-id="37c3e-103">W ramach tej zmiany,, <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A> <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A> i niektóre powiązane metody zostały oznaczone jako przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="37c3e-103">As part of that change, the <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A>, and some related methods were marked as obsolete.</span></span> <span data-ttu-id="37c3e-104">W ASP.NET Core 5,0 te przestarzałe metody zostały usunięte.</span><span class="sxs-lookup"><span data-stu-id="37c3e-104">In ASP.NET Core 5.0, those obsolete methods were removed.</span></span> <span data-ttu-id="37c3e-105">Aby zapoznać się z pełną listą metod, zobacz [interfejsy API, których to dotyczy](#affected-apis).</span><span class="sxs-lookup"><span data-stu-id="37c3e-105">For the full list of methods, see [Affected APIs](#affected-apis).</span></span>

<span data-ttu-id="37c3e-106">Aby zapoznać się z omówieniem tego problemu, zobacz [dotnet/aspnetcore # 20082](https://github.com/dotnet/aspnetcore/issues/20082).</span><span class="sxs-lookup"><span data-stu-id="37c3e-106">For discussion on this issue, see [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="37c3e-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="37c3e-107">Version introduced</span></span>

<span data-ttu-id="37c3e-108">5,0 — wersja zapoznawcza 3</span><span class="sxs-lookup"><span data-stu-id="37c3e-108">5.0 Preview 3</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="37c3e-109">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="37c3e-109">Old behavior</span></span>

<span data-ttu-id="37c3e-110">Centra sygnałów i programy obsługi połączeń mogą być rejestrowane w potoku pośredniczącym przy użyciu `UseSignalR` metod lub `UseConnections` .</span><span class="sxs-lookup"><span data-stu-id="37c3e-110">SignalR hubs and connection handlers could be registered in the middleware pipeline using the `UseSignalR` or `UseConnections` methods.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="37c3e-111">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="37c3e-111">New behavior</span></span>

<span data-ttu-id="37c3e-112">Centra sygnałów i programy obsługi połączeń powinny być zarejestrowane w ramach <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> przy użyciu <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> metod rozszerzenia i <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder> .</span><span class="sxs-lookup"><span data-stu-id="37c3e-112">SignalR hubs and connection handlers should be registered within <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> using the <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> and <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> extension methods on <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="37c3e-113">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="37c3e-113">Reason for change</span></span>

<span data-ttu-id="37c3e-114">Stare metody miały niestandardową logikę routingu, która nie współdziała z innymi składnikami routingu w ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="37c3e-114">The old methods had custom routing logic that didn't interact with other routing components in ASP.NET Core.</span></span> <span data-ttu-id="37c3e-115">W ASP.NET Core 3,0 wprowadzono nowy system routingu ogólnego przeznaczenia o nazwie Routing punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="37c3e-115">In ASP.NET Core 3.0, a new general-purpose routing system, called endpoint routing, was introduced.</span></span> <span data-ttu-id="37c3e-116">Sygnalizacja włączonego routingu punktu końcowego do współpracy z innymi składnikami routingu.</span><span class="sxs-lookup"><span data-stu-id="37c3e-116">Endpoint routing enabled SignalR to interact with other routing components.</span></span> <span data-ttu-id="37c3e-117">Przełączenie do tego modelu pozwala użytkownikom na korzystanie z pełnych korzyści z routingu punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="37c3e-117">Switching to this model allows users to realize the full benefits of endpoint routing.</span></span> <span data-ttu-id="37c3e-118">W związku z tym stare metody zostały usunięte.</span><span class="sxs-lookup"><span data-stu-id="37c3e-118">Consequently, the old methods have been removed.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="37c3e-119">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="37c3e-119">Recommended action</span></span>

<span data-ttu-id="37c3e-120">Usuń kod, który wywołuje `UseSignalR` lub `UseConnections` z metody projektu `Startup.Configure` .</span><span class="sxs-lookup"><span data-stu-id="37c3e-120">Remove code that calls `UseSignalR` or `UseConnections` from your project's `Startup.Configure` method.</span></span> <span data-ttu-id="37c3e-121">Zastąp go wywołaniami `MapHub` lub `MapConnectionHandler` odpowiednio w treści wywołania do `UseEndpoints` .</span><span class="sxs-lookup"><span data-stu-id="37c3e-121">Replace it with calls to `MapHub` or `MapConnectionHandler`, respectively, within the body of a call to `UseEndpoints`.</span></span> <span data-ttu-id="37c3e-122">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="37c3e-122">For example:</span></span>

<span data-ttu-id="37c3e-123">**Stary kod:**</span><span class="sxs-lookup"><span data-stu-id="37c3e-123">**Old code:**</span></span>

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="37c3e-124">**Nowy kod:**</span><span class="sxs-lookup"><span data-stu-id="37c3e-124">**New code:**</span></span>

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="37c3e-125">Ogólnie rzecz biorąc poprzednie `MapHub` i `MapConnectionHandler` wywołania można przenieść bezpośrednio z treści `UseSignalR` i `UseConnections` do `UseEndpoints` z niezbędną zmianą.</span><span class="sxs-lookup"><span data-stu-id="37c3e-125">In general, your previous `MapHub` and `MapConnectionHandler` calls can be transferred directly from the body of `UseSignalR` and `UseConnections` to `UseEndpoints` with little-to-no change needed.</span></span>

#### <a name="category"></a><span data-ttu-id="37c3e-126">Kategoria</span><span class="sxs-lookup"><span data-stu-id="37c3e-126">Category</span></span>

<span data-ttu-id="37c3e-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="37c3e-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="37c3e-128">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="37c3e-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections`
- `Overload:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler`
- `Overload:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub`

-->
