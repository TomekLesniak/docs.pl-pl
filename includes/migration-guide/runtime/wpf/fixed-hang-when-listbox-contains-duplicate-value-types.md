---
ms.openlocfilehash: 7637c2d96aef93b4cf8f2314c1dd1edba51d553c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496237"
---
### <a name="fixed-a-hang-when-listbox-contains-duplicate-value-types"></a>Naprawiono zawieszenie, gdy pole listy zawiera zduplikowane typy wartości

#### <a name="details"></a>Szczegóły

Rozwiązano problem polegający na tym, że wirtualizacja <xref:System.Windows.Controls.ItemsControl> może się zawiesić podczas przewijania, gdy kolekcja elementów zawiera zduplikowane obiekty z typem wartości.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Duży|
|Wersja|4,8|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
