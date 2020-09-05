---
ms.openlocfilehash: 05f60978f5380c406c43aa98ded0c812b1d50694
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496931"
---
### <a name="enumerableemptylttresultgt-always-returns-cached-instance"></a>Wyliczalne. Empty &lt; TResult &gt; zawsze zwraca buforowane wystąpienie

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4,5, <xref:System.Linq.Enumerable.Empty%60%601> zawsze zwraca buforowane wystąpienie wewnętrzne <xref:System.Collections.Generic.IEnumerable%601> . Wcześniej <xref:System.Linq.Enumerable.Empty%60%601> pamięć podręczna powinna <xref:System.Collections.Generic.IEnumerable%601> być pusta w momencie wywołania interfejsu API, co oznacza, że w niektórych przypadkach, w których <xref:System.Linq.Enumerable.Empty%60%601> została wywołana szybko i współbieżnie, różne wystąpienia typu mogą zostać zwrócone dla różnych wywołań interfejsu API.

#### <a name="suggestion"></a>Sugestia

Ze względu na to, że poprzednie zachowanie dotyczyło niedeterministyczności, kod prawdopodobnie nie zależy od niego. Jednak w nieprawdopodobnym przypadku, gdy puste wartości wyliczalne są porównywane i oczekiwano, że czasami nie są równe, należy utworzyć jawne puste tablice ( <code>new T[0]</code> ) zamiast używać <xref:System.Linq.Enumerable.Empty%60%601> .

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Linq.Enumerable.Empty``1``

-->
