---
title: 'Nieprzerwana zmiana: CA2013: nie należy używać ReferenceEquals z typami wartości'
description: Zapoznaj się z nieprzerwaną zmianą w programie .NET 5,0 spowodowaną przez włączenie reguły analizy kodu CA2013.
ms.date: 09/03/2020
ms.openlocfilehash: ca2b845427eff547b996b577394c6859e30f50bf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761328"
---
# <a name="warning-ca2013-do-not-use-referenceequals-with-value-types"></a>Ostrzeżenie CA2013: nie należy używać ReferenceEquals z typami wartości

Reguła analizatora kodu platformy .NET [CA2013](/visualstudio/code-quality/ca2013) jest domyślnie włączona, począwszy od platformy .NET 5,0. Generuje ostrzeżenie kompilacji dla dowolnego kodu, gdzie <xref:System.Object.ReferenceEquals(System.Object,System.Object)> jest używany do porównywania co najmniej jednego typu wartości dla równości.

## <a name="change-description"></a>Zmień opis

Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../fundamentals/code-analysis/overview.md). Niektóre z tych reguł są domyślnie włączone, w tym [CA2013](/visualstudio/code-quality/ca2013). Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.

CA2013 reguły znajduje wystąpienia <xref:System.Object.ReferenceEquals(System.Object,System.Object)> , gdzie jest używany do porównywania co najmniej jednego typu wartości dla równości. Porównywanie typów wartości dla równości w ten sposób może prowadzić do niepoprawnych wyników, ponieważ wartości są opakowane przed ich porównaniem. <xref:System.Object.ReferenceEquals(System.Object,System.Object)> zwróci `false` nawet wtedy, gdy porównane wartości reprezentują to samo wystąpienie typu wartości.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

- Zmień kod, aby użyć odpowiedniego operatora równości, takiego jak `==` . Nie należy pomijać tego ostrzeżenia.

- Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu. Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

### Category

Code analysis

-->
