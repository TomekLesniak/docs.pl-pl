---
title: 'Nieprzerwana zmiana: CA2247: argument konstruktora TaskCompletionSource powinien być wartością opcji TaskCreationOptions'
description: Zapoznaj się z nieprzerwaną zmianą w programie .NET 5,0 spowodowaną przez włączenie reguły analizy kodu CA2247.
ms.date: 09/03/2020
ms.openlocfilehash: 323fd5a05da4dfeb68ef75d88d5d293ba01c8ade
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761535"
---
# <a name="warning-ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a>Ostrzeżenie CA2247: argument konstruktora TaskCompletionSource powinien być wartością opcji TaskCreationOptions

Reguła analizatora kodu platformy .NET [CA2247](/visualstudio/code-quality/ca2247) jest domyślnie włączona, począwszy od platformy .NET 5,0. Generuje ostrzeżenie kompilacji dla wywołań <xref:System.Threading.Tasks.TaskCompletionSource%601> konstruktora, który przekazuje argument typu <xref:System.Threading.Tasks.TaskContinuationOptions> .

## <a name="change-description"></a>Zmień opis

Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../fundamentals/code-analysis/overview.md). Niektóre z tych reguł są domyślnie włączone, w tym [CA2247](/visualstudio/code-quality/ca2247). Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.

CA2247 reguły odnajduje wywołania <xref:System.Threading.Tasks.TaskCompletionSource%601> konstruktora, które przekazują argument typu <xref:System.Threading.Tasks.TaskContinuationOptions> . <xref:System.Threading.Tasks.TaskCompletionSource%601>Typ ma konstruktora, który akceptuje <xref:System.Threading.Tasks.TaskCreationOptions> wartość i inny Konstruktor akceptujący <xref:System.Object> . Jeśli przypadkowo przeszedł <xref:System.Threading.Tasks.TaskContinuationOptions> wartość zamiast <xref:System.Threading.Tasks.TaskCreationOptions> wartości, Konstruktor z <xref:System.Object> parametrem jest wywoływany w czasie wykonywania. Kod zostanie skompilowany i uruchomiony, ale nie będzie miał zamierzonego zachowania.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

- Zamień <xref:System.Threading.Tasks.TaskContinuationOptions> argument na odpowiadającą <xref:System.Threading.Tasks.TaskCreationOptions> wartość. Nie pomijaj tego ostrzeżenia, ponieważ prawie zawsze wyróżnia usterkę w kodzie. Aby uzyskać więcej informacji, zobacz [CA2247](/visualstudio/code-quality/ca2247).

- Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu. Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

### Category

Code analysis

-->
