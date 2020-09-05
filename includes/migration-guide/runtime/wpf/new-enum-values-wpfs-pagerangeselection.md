---
ms.openlocfilehash: 61749f59f9379a6d18bb013b2612a07cb7822b3a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497649"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a>Nowe wartości wyliczeniowe w PageRangeSelection WPF

#### <a name="details"></a>Szczegóły

Dodano dwóch nowych członków ( <xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> i <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName> ) do <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> wyliczenia.

#### <a name="suggestion"></a>Sugestia

W większości przypadków te zmiany nie wpłyną na kod użytkownika. Kod, który zależy od określonej liczby elementów istniejących w <xref:System.Enum.GetNames(System.Type)> lub <xref:System.Enum.GetValues(System.Type)> wywołania <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> typu należy zmodyfikować, chociaż.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.PageRangeSelection`

-->
