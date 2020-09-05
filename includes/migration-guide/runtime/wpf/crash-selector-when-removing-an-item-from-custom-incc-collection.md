---
ms.openlocfilehash: f50022d9a7bacd7be40fe3050ced26e7c25cf7aa
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497772"
---
### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a>Awaria w selektorze podczas usuwania elementu z niestandardowej kolekcji INCC

#### <a name="details"></a>Szczegóły

<code>T:System.InvalidOperationException</code>Może wystąpić w następującym scenariuszu:<ul><li>ItemsSource dla elementu <code>T:System.Windows.Controls.Primitives.Selector</code> to kolekcja z niestandardową implementacją programu <code>T:System.Collections.Specialized.INotifyCollectionChanged</code> .</li><li>Wybrany element zostanie usunięty z kolekcji.</li><li><code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code>Ma <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> =-1 (wskazuje nieznaną pozycję).</li></ul>Stosu wywołań wyjątku rozpoczyna się od system. Windows. Threading. Dyspozytor. VerifyAccess () w System. Windows. DependencyObject. GetValue (DependencyProperty dp) w System. Windows. Controls. elementy pierwotne. Selector. GetIsSelected (DependencyObject element) ten wyjątek może wystąpić w .NET Framework 4,5, jeśli aplikacja ma więcej niż jeden wątek dyspozytora. W .NET Framework 4,7 wyjątek może wystąpić również w aplikacjach z pojedynczym wątkiem dyspozytora. Problem został rozwiązany w .NET Framework 4.7.1.

#### <a name="suggestion"></a>Sugestia

Uaktualnij do .NET Framework 4.7.1.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4,7|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
