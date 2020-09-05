---
ms.openlocfilehash: 09bd2c6312493f8b6369d05d8f1c4e88e4c05ece
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497120"
---
### <a name="listsort-algorithm-changed"></a>Zmieniono algorytm list. Sort

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4,5, <xref:System.Collections.Generic.List%601?displayProperty=fullName> algorytm sortowania został zmieniony (algorytmu sortowanie zamiast szybkiego sortowania). <xref:System.Collections.Generic.List%601?displayProperty=fullName>sortowanie nigdy nie było stabilne, ale ta zmiana może spowodować, że inne scenariusze będą sortowane w niestabilny sposób. Oznacza to po prostu, że równoważne elementy mogą sortować w różnych zamówieniach w kolejnych wywołaniach interfejsu API.

#### <a name="suggestion"></a>Sugestia

Ponieważ stary algorytm sortowania był również niestabilny (choć nieco inaczej), nie powinien być kod, który zależy od elementów równoważnych zawsze sortowanych w określonej kolejności. Jeśli istnieją wystąpienia kodu, w zależności od tego i są cieszymy ze starym zachowaniem, kod ten należy zaktualizować, aby użyć funkcji porównującej, która będzie w sposób jednoznaczny sortować elementy w żądanej kolejności.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Przezroczyste|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Collections.Generic.List%601.Sort?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601.Sort(System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601.Sort(System.Comparison{%600})?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Generic.List`1.Sort``
- ``M:System.Collections.Generic.List`1.Sort(System.Collections.Generic.IComparer{`0})``
- ``M:System.Collections.Generic.List`1.Sort(System.Comparison{`0})``
- ``M:System.Collections.Generic.List`1.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{`0})``

-->
