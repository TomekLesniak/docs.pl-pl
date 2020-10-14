---
ms.openlocfilehash: 16994e9cd97b31a30c8c5ce49d2042ff79b3f60b
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050529"
---
### <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a>NegotiateStream i SslStream Zezwalaj na kolejne operacje BEGIN

Przypadki błędów w strumieniach zabezpieczeń są obsługiwane inaczej, a kolejne wywołania `BeginAuthenticateAsServer` lub `BeginAuthenticateAsClient` mogą przestać kończyć się niepowodzeniem.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC1

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach .NET, wywoływanie `BeginAuthenticateAsServer` lub `BeginAuthenticateAsClient` kolejno bez uprzedniego wywołania `EndAuthenticateAsServer` lub `EndAuthenticateAsClient` w wyniku <xref:System.NotSupportedException> . Począwszy od platformy .NET 5,0, kolejne wywołania `BeginAuthenticateAsServer` lub `BeginAuthenticateAsClient` nie będą już powodować <xref:System.NotSupportedException> , ponieważ te interfejsy API są obsługiwane przez <xref:System.Threading.Tasks.Task> implementację opartą na bazie.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Przełączenie wewnętrznej implementacji z modelu programowania asynchronicznego (APM) na oparty na programie <xref:System.Threading.Tasks.Task> zwiększa wydajność i zmniejsza złożoność kodu.

#### <a name="recommended-action"></a>Zalecana akcja

W części dewelopera nie jest wymagana żadna akcja.

#### <a name="category"></a>Kategoria

Sieć

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Net.Security.SslStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.SslStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsClient`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient`

-->
