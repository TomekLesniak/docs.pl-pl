---
title: Zmiany w analizie kodu
description: Wyświetla listę istotnych zmian w analizatorach kodu źródłowego platformy .NET.
ms.date: 08/22/2020
ms.openlocfilehash: 8b2b50c5f03a3ca971aefd0f2cf53624dfa82274
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465589"
---
# <a name="code-analysis-breaking-changes"></a>Zmiany w analizie kodu

Następujące istotne zmiany zostały udokumentowane na tej stronie:

| Zmiana podziału | Wprowadzona wersja |
| - | :-: |
| [CA1831: Użyj AsSpan lub AsMemory zamiast indeksatora opartego na zakresie](#ca1831-use-asspan-or-asmemory-instead-of-range-based-indexer) | 5,0 |
| [CA2014: Nie używaj słowa kluczowego stackalloc w pętlach](#ca2014-do-not-use-stackalloc-in-loops) | 5,0 |
| [CA2015: nie Definiuj finalizatorów dla typów pochodnych z pamięci\<T>](#ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert) | 5,0 |
| [CA2247: argumentem konstruktora TaskCompletionSource powinien być wartość opcji TaskCreationOptions](#ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value) | 5,0 |

## <a name="net-50"></a>.NET 5,0

[!INCLUDE [range-based-indexer-on-string](../../../includes/core-changes/codeanalysis/5.0/range-based-indexer-on-string.md)]

***

[!INCLUDE [stackalloc-in-loops](../../../includes/core-changes/codeanalysis/5.0/stackalloc-in-loops.md)]

***

[!INCLUDE [finalizers-for-memorymanager-types](../../../includes/core-changes/codeanalysis/5.0/finalizers-for-memorymanager-types.md)]

***

[!INCLUDE [ctor-arg-should-be-taskcreationoptions](../../../includes/core-changes/codeanalysis/5.0/ctor-arg-should-be-taskcreationoptions.md)]

***
