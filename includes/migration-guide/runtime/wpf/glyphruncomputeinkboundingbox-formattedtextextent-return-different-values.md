---
ms.openlocfilehash: d9e1624bbeb91db63bc284b8eb52643938eb42e5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496412"
---
### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-framework-45"></a>GlyphRun. ComputeInkBoundingBox () i FormattedText. zakres zwracają różne wartości zaczynające się na .NET Framework 4,5

#### <a name="details"></a>Szczegóły

Wprowadzono ulepszenia <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> i <xref:System.Windows.Media.FormattedText.Extent> w .NET Framework 4,5 do rozwiązywania problemów, gdy pola są zbyt małe dla zawartych symboli w niektórych przypadkach w .NET Framework 4,0. W wyniku tego niektóre pola ograniczające będą większe od początku .NET Framework 4,5, co spowodowało delikatne różnice w układzie interfejsu użytkownika.

#### <a name="suggestion"></a>Sugestia

Należy pamiętać, że niektóre rozmiary pól ograniczających glify zostały powiększone. Te zmiany zwykle ulepszają testowanie i pole trafień, ale jeśli jest wymagane zachowanie starsze (pre-.NET 4,5), można je dodać, dodając następujący wpis do pliku app.config:<pre><code class="lang-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType>
- <xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Media.GlyphRun.ComputeInkBoundingBox`
- `P:System.Windows.Media.FormattedText.Extent`

-->
