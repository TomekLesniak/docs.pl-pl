---
ms.openlocfilehash: b01424c63d6e7956127bf889c53422b60ba2f219
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598089"
---
### <a name="ca2013-do-not-use-referenceequals-with-value-types"></a>CA2013: Nie używaj metody ReferenceEquals z typami wartości

Reguła analizatora kodu platformy .NET [CA2013](/visualstudio/code-quality/ca2013) jest domyślnie włączona, począwszy od platformy .NET 5,0. Generuje ostrzeżenie kompilacji dla dowolnego kodu, gdzie <xref:System.Object.ReferenceEquals(System.Object,System.Object)> jest używany do porównywania co najmniej jednego typu wartości dla równości.

#### <a name="change-description"></a>Zmień opis

Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Niektóre z tych reguł są domyślnie włączone, w tym [CA2013](/visualstudio/code-quality/ca2013). Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.

CA2013 reguły znajduje wystąpienia <xref:System.Object.ReferenceEquals(System.Object,System.Object)> , gdzie jest używany do porównywania co najmniej jednego typu wartości dla równości. Porównywanie typów wartości dla równości w ten sposób może prowadzić do niepoprawnych wyników, ponieważ wartości są opakowane przed ich porównaniem. <xref:System.Object.ReferenceEquals(System.Object,System.Object)> zwróci `false` nawet wtedy, gdy porównane wartości reprezentują to samo wystąpienie typu wartości.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 8

#### <a name="recommended-action"></a>Zalecana akcja

- Zmień kod, aby użyć odpowiedniego operatora równości, takiego jak `==` . Nie należy pomijać tego ostrzeżenia.

- Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu. Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Kategoria

Analiza kodu

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

-->
