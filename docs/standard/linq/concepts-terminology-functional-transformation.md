---
title: Pojęcia i terminologia (transformacja funkcjonalna) — LINQ to XML
description: Poznaj koncepcje i terminologię czystych transformacji funkcjonalnych.
ms.date: 07/20/2015
ms.assetid: 03defb3a-7e17-4ab1-8efa-4dd66621e860
ms.openlocfilehash: 0ecdbdf88ee9f868143f466222fa06f0ccf641d8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558112"
---
# <a name="concepts-and-terminology-functional-transformation-linq-to-xml"></a>Pojęcia i terminologia (przekształcenie funkcjonalne) (LINQ to XML)

W tym artykule przedstawiono koncepcje i terminologię czystych transformacji funkcjonalnych. Podejście transformacji funkcjonalnej do przekształcania danych generuje kod, który jest często szybszy w programie, bardziej wyraźny i łatwiejszy w debugowaniu i utrzymaniu niż bardziej tradycyjne, bezużyteczne programowanie.

Należy zauważyć, że artykuły w tej sekcji nie są przeznaczone do pełnego wyjaśnienia programowania funkcjonalnego. Zamiast tego Artykuły te identyfikują niektóre funkcje programowania funkcjonalnego, które ułatwiają przekształcenie XML z jednego kształtu do drugiego.

## <a name="what-is-pure-functional-transformation"></a>Co to jest czysta funkcjonalna transformacja

W *czystej transformacji funkcjonalnej*zestaw funkcji, zwany *czystymi funkcjami*, definiuje sposób przekształcania zestawu danych strukturalnych z jego oryginalnego formularza na inny formularz. Słowo "czysty" wskazuje, że funkcje są przeznaczone do *składania*, które wymagają:

- Samodzielne, dzięki czemu mogą być swobodnie uporządkowane i *rozmieszczone*bez Entanglement lub współzależności z resztą programu. Czyste przekształcenia nie mają żadnej znajomości środowiska ani nie mają na nie wpływu. Oznacza to, że funkcje używane w transformację nie mają żadnych *efektów ubocznych*.
- *Bezstanowa*, dzięki czemu wykonywanie tej samej funkcji lub określonego zestawu funkcji na tym samym wejściu będzie zawsze powodowało te same dane wyjściowe. Czyste przekształcenia nie mają wolnej pamięci.

> [!IMPORTANT]
> W pozostałej części tego samouczka termin "czysta funkcja" jest używany w ogólnym sensie, aby wskazać podejście programistyczne i nie konkretną funkcję języka.
>
> Należy zauważyć, że czyste funkcje muszą być zaimplementowane jako metody w C# i jako funkcje w Visual Basic.
>
> Nie należy mylić czystych funkcji z czystymi metodami wirtualnymi w języku C++. Ten drugi wskazuje, że Klasa zawierająca jest abstrakcyjna i nie dostarczono treści metody.

### <a name="functional-programming"></a>Programowanie funkcjonalne

*Programowanie funkcjonalne* jest podejściem programistycznym, które bezpośrednio obsługuje funkcję czystego przekształcania funkcjonalności.

W historycznych językach programowania, takich jak ML, schematy, Haskell i F #, zostały przede wszystkim interesujące dla społeczności akademickiej. Mimo że zawsze było możliwe zapisanie czystych transformacji funkcjonalnych w języku C# i Visual Basic, trudności tego typu nie spowodowały, aby była to atrakcyjna opcja dla większości programistów. W ostatnich wersjach tych języków, jednak nowe konstrukcje języka, takie jak wyrażenia lambda i wnioskowanie, sprawiają, że programowanie funkcjonalne znacznie prostsze i bardziej produktywne.

Aby uzyskać więcej informacji na temat programowania funkcjonalnego, zobacz [programowanie funkcjonalne a](functional-vs-imperative-programming.md)bezwzględne programowanie.

#### <a name="domain-specific-functional-programming-languages"></a>Języki programowania funkcjonalnego specyficzne dla domeny

Mimo że ogólne funkcjonalne Języki programowania nie zostały szeroko wdrożone, niektóre specyficzne dla domeny Języki programowania mają lepszy sukces. Na przykład kaskadowe arkusze stylów (CSS) służy do określania wyglądu i sposobu działania wielu stron sieci Web, a arkusze stylów Extensible Stylesheet Language Transformations (XSLT) są szeroko używane w manipulowaniu danymi XML. Aby uzyskać więcej informacji na temat XSLT, zobacz [XSLT Transformations](../data/xml/xslt-transformations.md).

## <a name="terminology"></a>Terminologia

Poniższa lista zawiera definicje warunków związanych z transformacjami funkcjonalnymi.

Funkcja wyższej kolejności (pierwszej klasy) \
Funkcja, która może być traktowana jako obiekt programistyczny. Na przykład funkcja wyższego rzędu może być przekazana do lub zwrócona z innych funkcji. W języku C# i Visual Basic, Delegaty i wyrażenia lambda są funkcjami językowymi, które obsługują funkcje wyższego rzędu. Aby napisać funkcję wyższego rzędu, należy zadeklarować jeden lub więcej argumentów do przejęcia delegatów i często używać wyrażeń lambda podczas wywoływania. Wiele standardowych operatorów zapytań to funkcje wyższego rzędu.

Aby uzyskać więcej informacji, zobacz [standardowe operatory zapytań — Omówienie (C#)](../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) i [standardowe operatory zapytań — Omówienie (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).

wyrażenie lambda \
Zasadniczo Wbudowana funkcja anonimowa, która może być używana wszędzie tam, gdzie jest oczekiwany typ delegata. Jest to uproszczona definicja wyrażeń lambda, ale jest odpowiednia do celów tego samouczka.

Aby uzyskać więcej informacji, zobacz [wyrażenia lambda (Przewodnik programowania w języku C#)](../../csharp/language-reference/operators/lambda-expressions.md) i [wyrażenia lambda (Visual Basic))](../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).

zbiera
Strukturalny zestaw danych, zazwyczaj o jednolitym typie. Aby była zgodna z LINQ, kolekcja musi implementować <xref:System.Collections.IEnumerable> interfejs lub <xref:System.Linq.IQueryable> interfejs (lub jeden z ich rodzajowych odpowiedników <xref:System.Collections.Generic.IEnumerator%601> lub <xref:System.Linq.IQueryable%601> ).

Krotka (typy anonimowe) \
Koncepcja matematyczna, krotka jest skończoną sekwencją obiektów, każdego określonego typu. Spójna kolekcja jest również nazywana listą uporządkowaną. Typy anonimowe to implementacje języka tego koncepcji, które umożliwiają zadeklarowanie nienazwanego typu klasy i obiekt tego typu do wystąpienia w tym samym czasie.

Aby uzyskać więcej informacji, zobacz [Typy anonimowe (Przewodnik programowania w języku C#)](../../csharp/programming-guide/classes-and-structs/anonymous-types.md) i [Typy anonimowe (Visual Basic)](../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).

Wnioskowanie o typie (niejawne wpisywanie) \
Możliwość kompilatora, aby określić typ zmiennej w nieobecności jawnej deklaracji typu.

Aby uzyskać więcej informacji, zobacz [niejawnie wpisane zmienne lokalne (Przewodnik programowania w języku C#)](../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) i [wnioskowanie o typie lokalnym (Visual Basic)](../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).

wykonywanie odroczone i Ocena z opóźnieniem \
Opóźnienie obliczania wyrażenia do momentu, gdy jego rozpoznana wartość nie jest wymagana. Wykonywanie odroczone jest obsługiwane w kolekcjach.

Aby uzyskać więcej informacji na temat języka C#, zobacz [wprowadzenie do zapytań LINQ (C#)](../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) i [wykonywanie odroczone oraz obliczanie z opóźnieniem w LINQ to XML (c#)](./deferred-execution-lazy-evaluation.md).

Aby uzyskać więcej Visual Basic informacji, zobacz [podstawowe operacje zapytań (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md) i [wykonywanie odroczone oraz obliczanie z opóźnieniem w LINQ to XML (Visual Basic)](./deferred-execution-lazy-evaluation.md).

Te funkcje języka będą używane w przykładach kodu w tej sekcji.

## <a name="see-also"></a>Zobacz także

- [Wprowadzenie do czystych przekształceń funkcjonalnych](introduction-pure-functional-transformations.md)
- [Programowanie funkcjonalne a programowanie imperatywne](functional-vs-imperative-programming.md)
