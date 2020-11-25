---
title: 'Zmiana podziału: NegotiateStream i SslStream umożliwiają wykonywanie kolejnych operacji BEGIN'
description: Zapoznaj się z istotną zmianą w programie .NET 5,0, w której przypadki błędów w strumieniach zabezpieczeń są obsługiwane inaczej, a kolejne wywołania do BeginAuthenticateAsServer lub BeginAuthenticateAsClient mogą przestać kończyć się niepowodzeniem.
ms.date: 10/18/2020
ms.openlocfilehash: e0226d0f5586efca050ca3497ca1490fa21fd943
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761436"
---
# <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a>NegotiateStream i SslStream Zezwalaj na kolejne operacje BEGIN

Przypadki błędów w strumieniach zabezpieczeń są obsługiwane inaczej, a kolejne wywołania `BeginAuthenticateAsServer` lub `BeginAuthenticateAsClient` mogą przestać kończyć się niepowodzeniem.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach .NET, wywoływanie `BeginAuthenticateAsServer` lub `BeginAuthenticateAsClient` kolejno bez uprzedniego wywołania `EndAuthenticateAsServer` lub `EndAuthenticateAsClient` w wyniku <xref:System.NotSupportedException> . Począwszy od platformy .NET 5,0, kolejne wywołania `BeginAuthenticateAsServer` lub `BeginAuthenticateAsClient` nie będą już powodować <xref:System.NotSupportedException> , ponieważ te interfejsy API są obsługiwane przez <xref:System.Threading.Tasks.Task> implementację opartą na bazie.

## <a name="reason-for-change"></a>Przyczyna zmiany

Przełączenie wewnętrznej implementacji z modelu programowania asynchronicznego (APM) na oparty na programie <xref:System.Threading.Tasks.Task> zwiększa wydajność i zmniejsza złożoność kodu.

## <a name="recommended-action"></a>Zalecana akcja

W części dewelopera nie jest wymagana żadna akcja.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Net.Security.SslStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.SslStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsClient`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient`

### Category

Networking

-->
