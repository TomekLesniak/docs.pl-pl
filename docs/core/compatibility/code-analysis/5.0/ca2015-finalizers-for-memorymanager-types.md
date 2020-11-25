---
title: 'Nieprzerwana zmiana: CA2015: nie Definiuj finalizatorów dla typów pochodzących z pamięci<T>'
description: Zapoznaj się z nieprzerwaną zmianą w programie .NET 5,0 spowodowaną przez włączenie reguły analizy kodu CA2015.
ms.date: 09/03/2020
ms.openlocfilehash: 5d0ba0546b5a72363559f23713c8af4bb4e26e48
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761324"
---
# <a name="warning-ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a>Ostrzeżenie CA2015: nie Definiuj finalizatorów dla typów pochodzących z pamięci\<T>

Reguła analizatora kodu platformy .NET [CA2015](/visualstudio/code-quality/ca2015) jest domyślnie włączona, począwszy od platformy .NET 5,0. Generuje ostrzeżenie kompilacji dla dowolnego typu, który pochodzi od <xref:System.Buffers.MemoryManager%601> , który definiuje finalizator.

## <a name="change-description"></a>Zmień opis

Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../fundamentals/code-analysis/overview.md). Niektóre z tych reguł są domyślnie włączone, w tym [CA2015](/visualstudio/code-quality/ca2015). Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.

Reguły CA2015 typy flag, które pochodzą od <xref:System.Buffers.MemoryManager%601> elementu, który definiuje finalizator. Dodanie finalizatora do typu, który pochodzi od, <xref:System.Buffers.MemoryManager%601> prawdopodobnie wskazuje na błąd. Sugeruje to, że zasób natywny, który mógł zostać uzyskany w <xref:System.Span%601> trakcie, jest wyczyszczony, prawdopodobnie w czasie, gdy jest nadal używany przez <xref:System.Span%601> .

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

- Usuń definicję finalizatora. Aby uzyskać więcej informacji, zobacz [CA2015](/visualstudio/code-quality/ca2015).

- Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu. Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
