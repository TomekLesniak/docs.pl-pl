---
ms.openlocfilehash: a51160a8ab5a4b437e51db31def577f8d8f50182
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065182"
---
### <a name="ca2014-do-not-use-stackalloc-in-loops"></a>CA2014: Nie używaj słowa kluczowego stackalloc w pętlach

Reguła analizatora kodu platformy .NET [CA2014](/visualstudio/code-quality/ca2014) jest domyślnie włączona, począwszy od platformy .NET 5,0. Generuje ostrzeżenie kompilacji dla dowolnego kodu C#, gdzie wyrażenie [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) jest używane wewnątrz pętli.

#### <a name="change-description"></a>Zmień opis

Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Niektóre z tych reguł są domyślnie włączone, w tym [CA2014](/visualstudio/code-quality/ca2014). Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.

CA2014 reguł wyszukuje kod C#, gdzie [wyrażenie stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) jest używane wewnątrz pętli. [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) przydziela pamięć z bieżącej ramki stosu. Pamięć nie zostanie wydzielona do momentu, gdy bieżące wywołanie metody nie zwróci, co może prowadzić do przepełnienia stosu. Ponieważ nie można przechwytywać wyjątków przepełnienia stosu, aplikacja zostanie zakończona w przypadku przepełnienia stosu.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 8

#### <a name="recommended-action"></a>Zalecana akcja

- Unikaj używania [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) wewnątrz pętli. Przydziel blok pamięci poza pętlą i ponownie Użyj go wewnątrz pętli. Aby uzyskać więcej informacji, zobacz [CA2014](/visualstudio/code-quality/ca2014).

- Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu. Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Kategoria

Analiza kodu

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
