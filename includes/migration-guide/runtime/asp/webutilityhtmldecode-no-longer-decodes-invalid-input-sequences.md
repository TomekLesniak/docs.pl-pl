---
ms.openlocfilehash: ef3114a4eb9f62030c3ec36d3b463d07ccd59f6d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497850"
---
### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>WebUtility.HtmlDecode nie może już dekodować nieprawidłowych sekwencji wejściowych

#### <a name="details"></a>Szczegóły

Domyślnie metody dekodowania nie dekodują już nieprawidłowych sekwencji wejściowych na nieprawidłowy ciąg UTF-16. Zamiast tego zwracają oryginalne dane wejściowe.

#### <a name="suggestion"></a>Sugestia

Zmiana w danych wyjściowych dekodera powinna mieć znaczenie tylko wtedy, gdy w ciągach zamiast danych UTF-16 są przechowywane dane binarne. Aby jawnie kontrolować to zachowanie, ustaw <code>aspnet:AllowRelaxedUnicodeDecoding</code> atrybut elementu [AppSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) na <code>true</code> , aby włączyć starsze zachowanie lub aby <code>false</code> włączyć bieżące zachowanie.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Net.WebUtility.HtmlDecode(System.String)`
- `M:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)`
- `M:System.Net.WebUtility.UrlDecode(System.String)`

-->
