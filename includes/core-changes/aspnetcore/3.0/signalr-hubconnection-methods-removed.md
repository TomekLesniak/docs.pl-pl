---
ms.openlocfilehash: de06825f1031d05bc83183a83bae165e2f9512ff
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032878"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a>Sygnalizujący: HubConnection ResetSendPing i ResetTimeout metod

`ResetSendPing`Metody i `ResetTimeout` zostały usunięte z interfejsu API sygnalizującego `HubConnection` . Metody te były pierwotnie przeznaczone wyłącznie do użytku wewnętrznego, ale zostały udostępnione w ASP.NET Core 2,2. Te metody nie będą dostępne od momentu wydania w ASP.NET Core 3,0 wersja zapoznawcza 4. Aby zapoznać się z omówieniem, zobacz [dotnet/aspnetcore # 8543](https://github.com/dotnet/aspnetcore/issues/8543).

#### <a name="version-introduced"></a>Wprowadzona wersja

3.0

#### <a name="old-behavior"></a>Stare zachowanie

Dostępne interfejsy API.

#### <a name="new-behavior"></a>Nowe zachowanie

Interfejsy API są usuwane.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Metody te były pierwotnie przeznaczone wyłącznie do użytku wewnętrznego, ale zostały udostępnione w ASP.NET Core 2,2.

#### <a name="recommended-action"></a>Zalecana akcja

Nie używaj tych metod.

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing`
- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout`

-->
