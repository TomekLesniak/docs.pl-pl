---
title: Zmiany w analizie kodu
description: Wyświetla listę istotnych zmian w analizatorach kodu źródłowego platformy .NET.
ms.date: 09/02/2020
ms.openlocfilehash: 20badd69b316e1d87700b3c5061a71d648b71c64
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065204"
---
# <a name="code-analysis-breaking-changes"></a>Zmiany w analizie kodu

Następujące istotne zmiany zostały udokumentowane na tej stronie:

| Zmiana podziału | Wprowadzona wersja |
| - | :-: |
| [CA1416: zgodność platformy](#ca1416-platform-compatibility) | 5,0 |
| [CA1417: atrybut unattribute dla parametru String dla elementu P/Invoke](#ca1417-outattribute-on-string-parameter-for-pinvoke) | 5,0 |
| [CA1831: Użyj AsSpan zamiast indeksatorów opartych na zakresie dla ciągu](#ca1831-use-asspan-instead-of-range-based-indexers-for-string) | 5,0 |
| [CA2013: Nie używaj metody ReferenceEquals z typami wartości](#ca2013-do-not-use-referenceequals-with-value-types) | 5,0 |
| [CA2014: Nie używaj słowa kluczowego stackalloc w pętlach](#ca2014-do-not-use-stackalloc-in-loops) | 5,0 |
| [CA2015: nie Definiuj finalizatorów dla typów pochodnych z pamięci\<T>](#ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert) | 5,0 |
| [CA2247: argumentem konstruktora TaskCompletionSource powinien być wartość opcji TaskCreationOptions](#ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value) | 5,0 |

## <a name="net-50"></a>.NET 5,0

[!INCLUDE [ca1416-platform-compatibility-analyzer](../../../includes/core-changes/codeanalysis/5.0/ca1416-platform-compatibility-analyzer.md)]

***

[!INCLUDE [outattributes-on-pinvoke-string-parameters](../../../includes/core-changes/codeanalysis/5.0/ca1417-outattributes-on-pinvoke-string-parameters.md)]

***

[!INCLUDE [range-based-indexer-on-string](../../../includes/core-changes/codeanalysis/5.0/ca1831-range-based-indexer-on-string.md)]

***

[!INCLUDE [referenceequals-on-value-types](../../../includes/core-changes/codeanalysis/5.0/ca2013-referenceequals-on-value-types.md)]

***

[!INCLUDE [stackalloc-in-loops](../../../includes/core-changes/codeanalysis/5.0/ca2014-stackalloc-in-loops.md)]

***

[!INCLUDE [finalizers-for-memorymanager-types](../../../includes/core-changes/codeanalysis/5.0/ca2015-finalizers-for-memorymanager-types.md)]

***

[!INCLUDE [ctor-arg-should-be-taskcreationoptions](../../../includes/core-changes/codeanalysis/5.0/ca2247-ctor-arg-should-be-taskcreationoptions.md)]

***
