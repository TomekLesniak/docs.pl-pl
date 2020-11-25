---
title: 'Zmiana podziału: CA2200: ponownie zgłoś, aby zachować szczegóły stosu'
description: Zapoznaj się z nieprzerwaną zmianą w programie .NET 5,0 spowodowaną przez włączenie reguły analizy kodu CA2200.
ms.date: 09/03/2020
ms.openlocfilehash: 74e169906a8b826328de8d4c5f69c32234c2ce95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761532"
---
# <a name="warning-ca2200-rethrow-to-preserve-stack-details"></a>Ostrzeżenie CA2200: ponownie zgłoś, aby zachować szczegóły stosu

Reguła analizatora kodu platformy .NET [CA2200](/visualstudio/code-quality/ca2200) jest domyślnie włączona, począwszy od platformy .NET 5,0. Generuje ostrzeżenie kompilacji dla wszystkich `catch` bloków, które ponownie generują wyjątek, a wyjątek jest jawnie określony w `throw` instrukcji.

## <a name="change-description"></a>Zmień opis

Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../fundamentals/code-analysis/overview.md). Niektóre z tych reguł są domyślnie włączone, w tym [CA2200](/visualstudio/code-quality/ca2200). Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.

Reguła CA2200 flagi kodu, w którym wyjątki są ponownie zgłaszane i zmienna wyjątku została określona w `throw` instrukcji. Gdy wyjątek jest zgłaszany, część informacji, którą wykonuje, jest śladem stosu. Ślad stosu jest listą hierarchii wywołań metody, która rozpoczyna się od metody, która zgłasza wyjątek i kończą się metodą, która przechwytuje wyjątek. Jeśli wyjątek jest zgłaszany ponownie przez określenie wyjątku w `throw` instrukcji, ślad stosu zostanie uruchomiony w bieżącej metodzie, a lista wywołań metod między oryginalną metodą, która wywołała wyjątek, a bieżąca metoda zostanie utracona. Aby zachować oryginalne informacje śledzenia stosu z wyjątkiem, należy użyć `throw` instrukcji bez określenia wyjątku.

Poniższy fragment kodu nie tworzy ostrzeżenia dla reguły CA2200. Jednak *wiersz z* komentarzem wywoła naruszenie.

```csharp
catch (ArithmeticException e)
{
    // throw e;
    throw;
}
```

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

- Ponownie zgłoś wyjątki bez określania wyjątku jawnie. Aby uzyskać więcej informacji, zobacz [CA2200](/visualstudio/code-quality/ca2200).

- Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu. Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
