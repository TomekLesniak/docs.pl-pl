---
ms.openlocfilehash: 277a91fbfbf0c6aaaa0dc044ef0c079ad8607699
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496840"
---
### <a name="blockingcollectionlttgttrytakefromany-does-not-throw-anymore"></a>BlockingCollection &lt; T &gt; . TryTakeFromAny nie generują się już

#### <a name="details"></a>Szczegóły

Jeśli jedna z kolekcji wejściowych jest oznaczona jako ukończona, <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> nie zwraca już wartości-1 i już <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> nie zgłasza wyjątku. Ta zmiana umożliwia pracę z wykorzystaniem kolekcji, kiedy jedna z kolekcji jest pusta lub ukończona, ale inna kolekcja ma elementy, które mogą zostać pobrane.

#### <a name="suggestion"></a>Sugestia

Jeśli TryTakeFromAny zwracające wartość-1 lub wyrzucanie TakeFromAny zostało użyte do celów sterowania przepływem w przypadku, gdy trwa zablokowanie kolekcji, taki kod powinien teraz zostać zmieniony, aby można było <code>.Any(b =&gt; b.IsCompleted)</code> wykryć ten warunek.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Int32)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Concurrent.BlockingCollection`1.TakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.Threading.CancellationToken)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.Int32)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.TimeSpan)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.TimeSpan)``

-->
