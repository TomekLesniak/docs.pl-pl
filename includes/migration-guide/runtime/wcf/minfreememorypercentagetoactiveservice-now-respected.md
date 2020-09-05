---
ms.openlocfilehash: b23182ad1da8208a69b78fc7bc872780d386a59a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496939"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a>MinFreeMemoryPercentageToActiveService jest teraz przestrzegane

#### <a name="details"></a>Szczegóły

To ustawienie określa minimalną ilość pamięci, która musi być dostępna na serwerze, zanim będzie można aktywować usługę WCF. Jest ona przeznaczona do zapobiegania <xref:System.OutOfMemoryException?displayProperty=fullName> wyjątkom. W .NET Framework 4,5 to ustawienie nie ma żadnego wpływu. W .NET Framework 4.5.1 zostanie zaobserwowane ustawienie.

#### <a name="suggestion"></a>Sugestia

Wyjątek występuje, jeśli wolna ilość dostępnej pamięci na serwerze sieci Web jest mniejsza niż wartość procentowa zdefiniowana przez ustawienie konfiguracji. Niektóre usługi WCF, które zostały pomyślnie uruchomione i działały w ograniczonym środowisku pamięci, mogą teraz kończyć się niepowodzeniem.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5.1|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
