---
ms.openlocfilehash: 06424c4fa40343a881356c20003300f65e93efbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496487"
---
### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>Funkcja WF serializować wyrażenia. literały &lt; T &gt; datetimes są teraz inaczej (dzieli Niestandardowe analizatory języka XAML)

#### <a name="details"></a>Szczegóły

Skojarzony <xref:System.Windows.Markup.ValueSerializer> obiekt spowoduje przekonwertowanie <xref:System.DateTime?displayProperty=fullName> obiektu lub, <xref:System.DateTimeOffset?displayProperty=fullName> którego sekunda i <xref:System.DateTime.Millisecond?displayProperty=fullName> składniki są inne niż zero i (dla <xref:System.DateTime?displayProperty=fullName> wartości), których <xref:System.DateTime.Kind> Właściwość nie została określona jako składnia elementu właściwości zamiast ciągu. Ta zmiana umożliwia <xref:System.DateTime?displayProperty=fullName> i <xref:System.DateTimeOffset?displayProperty=fullName> wartości, które mają być okrężne. Niestandardowe analizatory języka XAML, które zakładają, że wejściowy kod XAML znajduje się w składni atrybutów, nie będą działać poprawnie.

#### <a name="suggestion"></a>Sugestia

Ta zmiana umożliwia <xref:System.DateTime?displayProperty=fullName> i <xref:System.DateTimeOffset?displayProperty=fullName> wartości, które mają być okrężne. Niestandardowe analizatory języka XAML, które zakładają, że wejściowy kod XAML znajduje się w składni atrybutów, nie będą działać poprawnie.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
