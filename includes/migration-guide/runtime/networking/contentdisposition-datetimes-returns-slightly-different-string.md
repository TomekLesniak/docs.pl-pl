---
ms.openlocfilehash: eb5c032a020799fa19cc0a8cfaabb56e01417ff4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496952"
---
### <a name="contentdisposition-datetimes-returns-slightly-different-string"></a>ContentDisposition DateTimes zwraca nieco inny ciąg

#### <a name="details"></a>Szczegóły

Reprezentacje ciągów dla <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName> zostały zaktualizowane, począwszy od 4,6, do zawsze reprezentujące składnik godziny z <xref:System.DateTime?displayProperty=fullName> dwoma cyframi. Jest to zgodne z [RFC822](https://www.ietf.org/rfc/rfc0822.txt) i [RFC2822](https://www.ietf.org/rfc/rfc2822.txt). Powoduje to <xref:System.Net.Mime.ContentDisposition.ToString> zwrócenie nieco innego ciągu w 4,6 w scenariuszach, w których jeden z elementów czasu dyspozycji był wcześniejszy niż 10:00 am. Należy zauważyć, że ContentDispositions są czasami serializowane przez konwersję do ciągów, więc <xref:System.Net.Mime.ContentDisposition.ToString> należy przejrzeć wszystkie wywołania operacji, serializacji lub GetHashCode.

#### <a name="suggestion"></a>Sugestia

Nie należy oczekiwać, że reprezentacje ciągów ContentDispositions z różnych wersji .NET Framework będą prawidłowo porównywane ze sobą. Przed przeprowadzeniem porównania przekonwertuj ciągi z powrotem do ContentDispositions, jeśli jest to możliwe.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4,6|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=nameWithType>
- <xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Net.Mime.ContentDisposition.ToString`
- `M:System.Net.Mime.ContentDisposition.GetHashCode`

-->
