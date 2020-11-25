---
ms.openlocfilehash: 2a65caedea2af65796267aa145e275ebff814bf8
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032888"
---
### <a name="signalr-usesignalr-and-useconnections-methods-marked-obsolete"></a><span data-ttu-id="d4ca1-101">Sygnalizujący: metody UseSignalR i UseConnections oznaczone jako przestarzałe</span><span class="sxs-lookup"><span data-stu-id="d4ca1-101">SignalR: UseSignalR and UseConnections methods marked obsolete</span></span>

<span data-ttu-id="d4ca1-102">Metody `UseConnections` i `UseSignalR` i klasy `ConnectionsRouteBuilder` i `HubRouteBuilder` są oznaczone jako przestarzałe w ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="d4ca1-102">The methods `UseConnections` and `UseSignalR` and the classes `ConnectionsRouteBuilder` and `HubRouteBuilder` are marked as obsolete in ASP.NET Core 3.0.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d4ca1-103">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="d4ca1-103">Version introduced</span></span>

<span data-ttu-id="d4ca1-104">3.0</span><span class="sxs-lookup"><span data-stu-id="d4ca1-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d4ca1-105">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="d4ca1-105">Old behavior</span></span>

<span data-ttu-id="d4ca1-106">Routing centrum sygnałów został skonfigurowany przy użyciu `UseSignalR` lub `UseConnections` .</span><span class="sxs-lookup"><span data-stu-id="d4ca1-106">SignalR hub routing was configured using `UseSignalR` or `UseConnections`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d4ca1-107">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="d4ca1-107">New behavior</span></span>

<span data-ttu-id="d4ca1-108">Stary sposób konfigurowania routingu został przestarzały i zastąpiony przez Routing punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="d4ca1-108">The old way of configuring routing has been obsoleted and replaced with endpoint routing.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d4ca1-109">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="d4ca1-109">Reason for change</span></span>

<span data-ttu-id="d4ca1-110">Oprogramowanie pośredniczące jest przenoszone do nowego systemu routingu punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="d4ca1-110">Middleware is being moved to the new endpoint routing system.</span></span> <span data-ttu-id="d4ca1-111">Stary sposób dodawania oprogramowania pośredniczącego jest przestarzały.</span><span class="sxs-lookup"><span data-stu-id="d4ca1-111">The old way of adding middleware is being obsoleted.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d4ca1-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="d4ca1-112">Recommended action</span></span>

<span data-ttu-id="d4ca1-113">Zamień `UseSignalR` na `UseEndpoints` :</span><span class="sxs-lookup"><span data-stu-id="d4ca1-113">Replace `UseSignalR` with `UseEndpoints`:</span></span>

<span data-ttu-id="d4ca1-114">**Stary kod:**</span><span class="sxs-lookup"><span data-stu-id="d4ca1-114">**Old code:**</span></span>

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="d4ca1-115">**Nowy kod:**</span><span class="sxs-lookup"><span data-stu-id="d4ca1-115">**New code:**</span></span>

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

#### <a name="category"></a><span data-ttu-id="d4ca1-116">Kategoria</span><span class="sxs-lookup"><span data-stu-id="d4ca1-116">Category</span></span>

<span data-ttu-id="d4ca1-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d4ca1-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d4ca1-118">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d4ca1-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections(Microsoft.AspNetCore.Builder.IApplicationBuilder,System.Action{Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder})?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR(Microsoft.AspNetCore.Builder.IApplicationBuilder,System.Action{Microsoft.AspNetCore.SignalR.HubRouteBuilder})?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections(Microsoft.AspNetCore.Builder.IApplicationBuilder,System.Action{Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder})`
- `M:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR(Microsoft.AspNetCore.Builder.IApplicationBuilder,System.Action{Microsoft.AspNetCore.SignalR.HubRouteBuilder})`
- `T:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder`
- `T:Microsoft.AspNetCore.SignalR.HubRouteBuilder`

-->
