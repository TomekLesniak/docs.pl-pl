---
ms.openlocfilehash: bca76daca6e9c424377a80aa56e1a5ff191be5ca
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496695"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>Sporadycznie nie można przewijać do ostatniego elementu w ItemsControls (na przykład ListBox i DataGrid) przy użyciu niestandardowych szablonów datatemplates

#### <a name="details"></a>Szczegóły

W niektórych przypadkach usterka w .NET Framework 4,5 powoduje, że w <xref:System.Windows.Controls.ListBox?displayProperty=fullName> <xref:System.Windows.Controls.ComboBox?displayProperty=fullName> <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> przypadku korzystania z niestandardowych szablonów datatemplates ItemsControls (np., itp.). W przypadku próby przeprowadzenia przewijania po raz drugi (po przeprowadzeniu przewijania kopii zapasowej) działanie zostanie wykonane.

#### <a name="suggestion"></a>Sugestia

Ten problem został rozwiązany w .NET Framework 4.5.2 i może zostać rozwiązany przez uaktualnienie do tej wersji (lub nowszej) .NET Framework. Alternatywnie użytkownicy nadal mogą przeciągać paski przewijania do elementów końcowych w tych kolekcjach, ale może być konieczne dwukrotne wykonanie tej czynności.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
