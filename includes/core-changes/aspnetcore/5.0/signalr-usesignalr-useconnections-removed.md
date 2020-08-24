---
ms.openlocfilehash: 329ef39c7626ecd743577f336a4c8cd4a38fb082
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291637"
---
### <a name="signalr-usesignalr-and-useconnections-methods-removed"></a>Sygnalizacja: Usunięto metody UseSignalR i UseConnections

W ASP.NET Core 3,0, sygnalizujący przyjął Routing punktów końcowych. W ramach tej zmiany,, <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A> <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A> i niektóre powiązane metody zostały oznaczone jako przestarzałe. W ASP.NET Core 5,0 te przestarzałe metody zostały usunięte. Aby zapoznać się z pełną listą metod, zobacz [interfejsy API, których to dotyczy](#affected-apis).

Aby zapoznać się z omówieniem tego problemu, zobacz [dotnet/aspnetcore # 20082](https://github.com/dotnet/aspnetcore/issues/20082).

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 — wersja zapoznawcza 3

#### <a name="old-behavior"></a>Stare zachowanie

Centra sygnałów i programy obsługi połączeń mogą być rejestrowane w potoku pośredniczącym przy użyciu `UseSignalR` metod lub `UseConnections` .

#### <a name="new-behavior"></a>Nowe zachowanie

Centra sygnałów i programy obsługi połączeń powinny być zarejestrowane w ramach <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> przy użyciu <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> metod rozszerzenia i <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder> .

#### <a name="reason-for-change"></a>Przyczyna zmiany

Stare metody miały niestandardową logikę routingu, która nie współdziała z innymi składnikami routingu w ASP.NET Core. W ASP.NET Core 3,0 wprowadzono nowy system routingu ogólnego przeznaczenia o nazwie Routing punktu końcowego. Sygnalizacja włączonego routingu punktu końcowego do współpracy z innymi składnikami routingu. Przełączenie do tego modelu pozwala użytkownikom na korzystanie z pełnych korzyści z routingu punktów końcowych. W związku z tym stare metody zostały usunięte.

#### <a name="recommended-action"></a>Zalecana akcja

Usuń kod, który wywołuje `UseSignalR` lub `UseConnections` z metody projektu `Startup.Configure` . Zastąp go wywołaniami `MapHub` lub `MapConnectionHandler` odpowiednio w treści wywołania do `UseEndpoints` . Na przykład:

**Stary kod:**

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

**Nowy kod:**

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

Ogólnie rzecz biorąc poprzednie `MapHub` i `MapConnectionHandler` wywołania można przenieść bezpośrednio z treści `UseSignalR` i `UseConnections` do `UseEndpoints` z niezbędną zmianą.

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

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
