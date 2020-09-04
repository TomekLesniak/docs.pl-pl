---
ms.openlocfilehash: 4fc31f75e8f8cdd50abebd399d9749688e6faa5a
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465592"
---
### <a name="ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a>CA2015: Nie definiuj finalizatorów dla typów pochodzących od typu MemoryManager\<T>

Reguła analizatora kodu platformy .NET [CA2015](/visualstudio/code-quality/ca2015) jest domyślnie włączona, począwszy od platformy .NET 5,0. Generuje ostrzeżenie kompilacji dla dowolnego typu, który pochodzi od <xref:System.Buffers.MemoryManager%601> , który definiuje finalizator.

#### <a name="change-description"></a>Zmień opis

Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Niektóre z tych reguł są domyślnie włączone, w tym [CA2015](/visualstudio/code-quality/ca2015). Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.

Reguły CA2015 typy flag, które pochodzą od <xref:System.Buffers.MemoryManager%601> elementu, który definiuje finalizator. Dodanie finalizatora do typu, który pochodzi od, <xref:System.Buffers.MemoryManager%601> prawdopodobnie wskazuje na błąd. Sugeruje to, że zasób natywny, który mógł zostać uzyskany w <xref:System.Span%601> trakcie, jest wyczyszczony, prawdopodobnie w czasie, gdy jest nadal używany przez <xref:System.Span%601> .

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 8

#### <a name="recommended-action"></a>Zalecana akcja

- Usuń definicję finalizatora. Aby uzyskać więcej informacji, zobacz [CA2015](/visualstudio/code-quality/ca2015).

- Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu. Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Kategoria

Analiza kodu

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
