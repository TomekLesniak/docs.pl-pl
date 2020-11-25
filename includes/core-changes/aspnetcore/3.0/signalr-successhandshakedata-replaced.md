---
ms.openlocfilehash: 05aec429e28ef74515ef6988d5b064e6d16b7c1b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032895"
---
### <a name="signalr-handshakeprotocolsuccesshandshakedata-replaced"></a>Sygnalizujący: HandshakeProtocol. SuccessHandshakeData został zastąpiony

Pole [HandshakeProtocol. SuccessHandshakeData](https://github.com/dotnet/aspnetcore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) zostało usunięte i zastąpione metodą pomocnika, która generuje pomyślną odpowiedź uzgadniania z określonym `IHubProtocol` .

#### <a name="version-introduced"></a>Wprowadzona wersja

3.0

#### <a name="old-behavior"></a>Stare zachowanie

`HandshakeProtocol.SuccessHandshakeData` była `public static ReadOnlyMemory<byte>` polem.

#### <a name="new-behavior"></a>Nowe zachowanie

`HandshakeProtocol.SuccessHandshakeData` został zastąpiony przez `static` `GetSuccessfulHandshake(IHubProtocol protocol)` metodę, która zwraca w `ReadOnlyMemory<byte>` oparciu o określony protokół.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Dodatkowe pola zostały dodane do _odpowiedzi_ uzgadniania, które nie są stałe i zmieniają się w zależności od wybranego protokołu.

#### <a name="recommended-action"></a>Zalecana akcja

Brak. Ten typ nie jest przeznaczony do użycia z kodu użytkownika. Jest to `public` , więc może być współużytkowany przez serwer sygnalizujący i klienta. Mogą być również używane przez klientów sygnalizujących klientów pisanych w programie .NET. Ta zmiana nie powinna mieć żadnego wpływ na **użytkowników** sygnalizującego.

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

<xref:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData?displayProperty=nameWithType>

<!--

#### Affected APIs

`F:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData`

-->
