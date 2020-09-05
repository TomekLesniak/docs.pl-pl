---
ms.openlocfilehash: 415eb1960c20fb662469e126560d6f366309eb0d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496146"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a>Ulepszenia siatki z gwiazdkami — przydzielenie algorytmu w przestrzeni wierszy

#### <a name="details"></a>Szczegóły

Rozwiązano usterkę w [algorytmie przydzielania rozmiarów do](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)programu w ramach <xref:System.Windows.Controls.Grid> wprowadzenia w .NET Framework 4,7.  W niektórych przypadkach, takich jak siatka <code>Height=&quot;Auto&quot;</code> zawierająca puste wiersze, wiersze były ułożone w niewłaściwej pozycji, prawdopodobnie poza siatką.

#### <a name="suggestion"></a>Sugestia

Aby aplikacja mogła korzystać z tych zmian, należy ją uruchomić w .NET Framework 4,8 lub nowszej.

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
