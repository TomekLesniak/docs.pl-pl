---
ms.openlocfilehash: 3c32d2e13447f8fd9aa6b185b5fc7e60f9e1bb61
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496267"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a>Obsługa specjalnej notacji względnych identyfikatorów URI, gdy występuje Unicode

#### <a name="details"></a>Szczegóły

<xref:System.Uri> nie będzie już zgłaszać <xref:System.NullReferenceException> w przypadku wywołania <xref:System.Uri.TryCreate%2A> określonych względnych identyfikatorów URI zawierających Unicode. Najprostsza reprodukcja <xref:System.NullReferenceException> znajduje się poniżej, przy czym dwie instrukcje są równoważne:<pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre>Aby odtworzyć <xref:System.NullReferenceException> , należy wykonać następujące czynności:<ul><li>Identyfikator URI musi być określony jako względny przez zaczekanie z "http:" i nie jest następujący z "//".</li><li>Identyfikator URI musi zawierać zakodowane w procentach symbole Unicode lub unzastrzeżone.</li></ul>

#### <a name="suggestion"></a>Sugestia

Użytkownicy w zależności od tego zachowania, aby nie zezwalać na względne identyfikatory URI, należy zamiast tego określić <xref:System.UriKind.Absolute?displayProperty=nameWithType> podczas tworzenia identyfikatora URI.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.7.2|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)`
- `M:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)`
- `M:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)`

-->
