---
title: 'Nieprzerwana zmiana: CA2014: nie używaj stackalloc w pętlach'
description: Zapoznaj się z nieprzerwaną zmianą w programie .NET 5,0 spowodowaną przez włączenie reguły analizy kodu CA2014.
ms.date: 09/03/2020
ms.openlocfilehash: 7ad6203c0edd930bbbe43cdb8df0413cba833d8e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761327"
---
# <a name="warning-ca2014-do-not-use-stackalloc-in-loops"></a>Ostrzeżenie CA2014: nie używaj stackalloc w pętlach

Reguła analizatora kodu platformy .NET [CA2014](/visualstudio/code-quality/ca2014) jest domyślnie włączona, począwszy od platformy .NET 5,0. Generuje ostrzeżenie kompilacji dla dowolnego kodu C#, gdzie wyrażenie [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) jest używane wewnątrz pętli.

## <a name="change-description"></a>Zmień opis

Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../fundamentals/code-analysis/overview.md). Niektóre z tych reguł są domyślnie włączone, w tym [CA2014](/visualstudio/code-quality/ca2014). Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.

CA2014 reguł wyszukuje kod C#, gdzie [wyrażenie stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) jest używane wewnątrz pętli. [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) przydziela pamięć z bieżącej ramki stosu. Pamięć nie zostanie wydzielona do momentu, gdy bieżące wywołanie metody nie zwróci, co może prowadzić do przepełnienia stosu. Ponieważ nie można przechwytywać wyjątków przepełnienia stosu, aplikacja zostanie zakończona w przypadku przepełnienia stosu.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

- Unikaj używania [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) wewnątrz pętli. Przydziel blok pamięci poza pętlą i ponownie Użyj go wewnątrz pętli. Aby uzyskać więcej informacji, zobacz [CA2014](/visualstudio/code-quality/ca2014).

- Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu. Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
