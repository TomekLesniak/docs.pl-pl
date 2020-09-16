---
ms.openlocfilehash: b697bbf6844759de8babd4245667e7b333884ff8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538930"
---
### <a name="ca2200-rethrow-to-preserve-stack-details"></a>CA2200: Ponowie zgłoś wyjątek, aby zachować szczegóły stosu

Reguła analizatora kodu platformy .NET [CA2200](/visualstudio/code-quality/ca2200) jest domyślnie włączona, począwszy od platformy .NET 5,0. Generuje ostrzeżenie kompilacji dla wszystkich `catch` bloków, które ponownie generują wyjątek, a wyjątek jest jawnie określony w `throw` instrukcji.

#### <a name="change-description"></a>Zmień opis

Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Niektóre z tych reguł są domyślnie włączone, w tym [CA2200](/visualstudio/code-quality/ca2200). Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.

Reguła CA2200 flagi kodu, w którym wyjątki są ponownie zgłaszane i zmienna wyjątku została określona w `throw` instrukcji. Gdy wyjątek jest zgłaszany, część informacji, którą wykonuje, jest śladem stosu. Ślad stosu jest listą hierarchii wywołań metody, która rozpoczyna się od metody, która zgłasza wyjątek i kończą się metodą, która przechwytuje wyjątek. Jeśli wyjątek jest zgłaszany ponownie przez określenie wyjątku w `throw` instrukcji, ślad stosu zostanie uruchomiony w bieżącej metodzie, a lista wywołań metod między oryginalną metodą, która wywołała wyjątek, a bieżąca metoda zostanie utracona. Aby zachować oryginalne informacje śledzenia stosu z wyjątkiem, należy użyć `throw` instrukcji bez określenia wyjątku.

Poniższy fragment kodu nie tworzy ostrzeżenia dla reguły CA2200. Jednak *wiersz z* komentarzem wywoła naruszenie.

```csharp
catch (ArithmeticException e)
{
    // throw e;
    throw;
}
```

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC1

#### <a name="recommended-action"></a>Zalecana akcja

- Ponownie zgłoś wyjątki bez określania wyjątku jawnie. Aby uzyskać więcej informacji, zobacz [CA2200](/visualstudio/code-quality/ca2200).

- Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu. Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Kategoria

Analiza kodu

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
