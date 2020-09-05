---
ms.openlocfilehash: 12a26030a9a336d887ae9d53994a9daf13356618
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496376"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>Zmiana właściwości IsEnabled elementu nadrzędnego formantu TextBlock ma wpływ na wszystkie kontrolki podrzędne

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4.6.2, zmiana <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> właściwości elementu nadrzędnego <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> formantu ma wpływ na wszystkie kontrolki podrzędne (takie jak hiperłącza i przyciski) <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> formantu. W .NET Framework 4.6.1 i starszych wersji, formanty wewnątrz <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> nie zawsze odzwierciedlają stan <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> właściwości <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> elementu nadrzędnego.

#### <a name="suggestion"></a>Sugestia

Brak. Ta zmiana jest zgodna z oczekiwanym zachowaniem formantów wewnątrz <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> kontrolki.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.6.2|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.UIElement.IsEnabled`

-->
