---
title: Wykonywanie odroczone i Ocena z opóźnieniem — LINQ to XML
description: Poznaj zalety i wymagania odroczonego wykonywania oraz Zaimplementuj go przy użyciu operacji zapytań i osi.
ms.date: 07/20/2015
ms.assetid: 8683d1b4-b7ec-407b-be12-906ebe958a09
ms.openlocfilehash: 21b1c7b7d54e7f787919f1e1601fc36bc8c1caff
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552921"
---
# <a name="deferred-execution-and-lazy-evaluation-linq-to-xml"></a>Wykonywanie odroczone i Ocena z opóźnieniem (LINQ to XML)

Operacje zapytań i osi często są implementowane w celu użycia odroczonego wykonania. W tym artykule opisano wymagania i zalety odroczonego wykonywania oraz niektóre zagadnienia dotyczące implementacji.

## <a name="deferred-execution"></a>Wykonanie odroczone

Wykonywanie odroczone oznacza, że Obliczanie wyrażenia jest opóźnione do momentu, gdy wartość *rzeczywista* jest wymagana. Wykonywanie odroczone może znacznie poprawić wydajność, gdy trzeba manipulować dużymi kolekcjami danych, szczególnie w programach, które zawierają serię zapytań lub manipulacji łańcucha. W najlepszym przypadku wykonywanie odroczone włącza tylko jedną iterację za pomocą kolekcji źródłowej.

Technologie LINQ umożliwiają użycie odroczonego wykonania w obu elementach członkowskich <xref:System.Linq?displayProperty=nameWithType> klas podstawowych i w metodach rozszerzających w różnych przestrzeniach nazw LINQ, takich jak <xref:System.Xml.Linq.Extensions?displayProperty=nameWithType> .

Wykonywanie odroczone jest obsługiwane bezpośrednio w języku C# za pomocą słowa kluczowego [yield (odwołanie w C#)](../../csharp/language-reference/keywords/yield.md) (w formie `yield-return` instrukcji), gdy jest używana w bloku iteratora. Taki iterator musi zwracać kolekcję typu <xref:System.Collections.IEnumerator> lub <xref:System.Collections.Generic.IEnumerator%601> (lub typu pochodnego).

## <a name="eager-vs-lazy-evaluation"></a>Ocena eager a z opóźnieniem

Podczas pisania metody, która implementuje wykonywanie odroczone, należy również zdecydować, czy zaimplementować metodę przy użyciu oceny z opóźnieniem czy oceny eager.

- W *ocenie z opóźnieniem*pojedynczy element kolekcji źródłowej jest przetwarzany podczas każdego wywołania iteratora. Jest to typowy sposób implementacji iteratorów.
- W *ocenie eager*pierwsze wywołanie iteratora spowoduje przetworzenie całej kolekcji. Może być również wymagana tymczasowa kopia kolekcji źródłowej. Na przykład <xref:System.Linq.Enumerable.OrderBy%2A> Metoda musi sortować całą kolekcję przed zwróceniem pierwszego elementu.

Ocena z opóźnieniem zwykle zapewnia lepszą wydajność, ponieważ dystrybuuje przetwarzanie narzutowe równomiernie przez oszacowanie kolekcji i minimalizuje użycie danych tymczasowych. Oczywiście w przypadku niektórych operacji nie ma żadnej innej opcji, aby zmaterializowania wyniki pośrednie.

Zobacz [przykład odroczonego wykonania](deferred-execution-example.md) , aby zapoznać się z przykładem wykonania odroczonego wykonywania w języku C# i Visual Basic.

## <a name="see-also"></a>Zobacz też

- [Samouczek: zapytania łańcuchowe razem w języku C #](chain-queries-example.md)
- [Pojęcia i terminologia (przekształcenie funkcjonalne)](concepts-terminology-functional-transformation.md)
- [Operacje agregacji (C#)](../../csharp/programming-guide/concepts/linq/aggregation-operations.md)
- [Operacje agregacji (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)
- [yield (odwołanie w C#)](../../csharp/language-reference/keywords/yield.md)
