---
title: Opcje
description: 'Dowiedz się, jak używać typów opcji języka F #, gdy rzeczywista wartość może nie istnieć dla nazwanej wartości lub zmiennej.'
ms.date: 08/13/2020
ms.openlocfilehash: 0618590c10f6ecac51a23483ca0ab6cd66f2df4f
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557571"
---
# <a name="options"></a>Opcje

Typ opcji w F # jest używany, gdy rzeczywista wartość może nie istnieć dla nazwanej wartości lub zmiennej. Opcja ma typ podstawowy i może zawierać wartość tego typu lub może nie mieć wartości.

## <a name="remarks"></a>Uwagi

Poniższy kod ilustruje funkcję, która generuje typ opcji.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

Jak widać, jeśli dane wejściowe `a` są większe niż 0, `Some(a)` jest generowany.  W przeciwnym razie `None` jest generowany.

Wartość `None` jest używana, gdy opcja nie ma rzeczywistej wartości. W przeciwnym razie wyrażenie `Some( ... )` przypisuje opcję wartość. Wartości `Some` i `None` są przydatne w dopasowaniu do wzorców, jak w następującej funkcji `exists` , która zwraca, `true` Jeśli opcja ma wartość i `false` Jeśli nie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>Korzystanie z opcji

Opcje są często używane, gdy wyszukiwanie nie zwraca pasującego wyniku, jak pokazano w poniższym kodzie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

W poprzednim kodzie lista jest przeszukiwana cyklicznie. Funkcja `tryFindMatch` przyjmuje funkcję predykatu `pred` zwracającą wartość logiczną i listę do wyszukania. Jeśli zostanie znaleziony element, który spełnia predykat, rekursja zostanie zakończona, a funkcja zwraca wartość jako opcję w wyrażeniu `Some(head)` . Rekursja jest zakończona, gdy pusta lista zostanie dopasowana. W tym momencie wartość `head` nie została znaleziona i `None` jest zwracana.

Wiele funkcji biblioteki języka F #, które przeszukują kolekcję dla wartości, która może lub nie istnieje Zwróć `option` Typ. Zgodnie z Konwencją te funkcje zaczynają się od `try` prefiksu, na przykład [`Seq.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFindIndex) .

Opcje mogą być również przydatne, gdy wartość może nie istnieć, na przykład jeśli jest możliwe, że wyjątek zostanie wygenerowany podczas próby skonstruowania wartości. Pokazano to w poniższym przykładzie kodu.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

`openFile`Funkcja w poprzednim przykładzie ma typ `string -> File option` , ponieważ zwraca `File` obiekt, jeśli plik zostanie otwarty pomyślnie i wystąpił `None` wyjątek. W zależności od sytuacji może nie być odpowiedni wybór projektu, aby przechwytywać wyjątek, zamiast zezwalać na propagację.

Ponadto nadal możliwe jest przekazywanie `null` lub wartość o wartości null w `Some` przypadku opcji. Jest to ogólnie konieczne, a zwykle jest to rutynowe programowanie w języku F #, ale jest możliwe ze względu na charakter typów referencyjnych w programie .NET.

## <a name="option-properties-and-methods"></a>Właściwości i metody opcji

Typ opcji obsługuje następujące właściwości i metody.

|Właściwość lub metoda|Typ|Opis|
|------------------|----|-----------|
|[Brak](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#None)|`'T option`|Właściwość statyczna, która umożliwia utworzenie wartości opcji, która ma `None` wartość.|
|[IsNone —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#IsNone)|`bool`|Zwraca `true` czy opcja ma `None` wartość.|
|[IsSome —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#IsSome)|`bool`|Zwraca `true` czy opcja ma wartość, która nie jest wartością `None` .|
|[Niektóre](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#Some)|`'T option`|Statyczny element członkowski, który tworzy opcję, która ma wartość, która nie jest `None` .|
|[Wartość](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#Value)|`'T`|Zwraca wartość bazową lub zgłasza `System.NullReferenceException` wartość `None` .|

## <a name="option-module"></a>Moduł opcji

Istnieje moduł, który zawiera użyteczne [funkcje, które](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html)wykonują operacje na opcjach. Niektóre funkcje powtarzają funkcjonalność właściwości, ale są przydatne w kontekstach, w których jest wymagana funkcja. [Opcja.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#isSome) ISA i [Option. isNone](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#isNone) są funkcjami modułu, które sprawdzają, czy opcja ma wartość. [Opcja. Get](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#get) uzyskuje wartość, jeśli istnieje. Jeśli nie ma wartości, zgłasza `System.ArgumentException` .

Funkcja [Option. bind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#bind) wykonuje funkcję na wartości, jeśli istnieje wartość. Funkcja musi mieć dokładnie jeden argument, a jej typem parametru musi być typ opcji. Wartość zwracana przez funkcję jest innym typem opcji.

Moduł opcji zawiera również funkcje, które odpowiadają funkcjom dostępnym dla list, tablic, sekwencji i innych typów kolekcji. Te funkcje obejmują,,,,, [`Option.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#map) [`Option.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#iter) [`Option.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#forall) [`Option.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#exists) [`Option.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#foldBack) [`Option.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#fold) i [`Option.count`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#count) . Te funkcje umożliwiają użycie opcji, takich jak kolekcja elementów zero lub jeden. Aby uzyskać więcej informacji i przykładów, zobacz Omówienie funkcji kolekcji na [listach](lists.md).

## <a name="converting-to-other-types"></a>Konwertowanie na inne typy

Opcje można przekonwertować na listy lub tablice. Gdy opcja jest konwertowana na jedną z tych struktur danych, utworzona struktura danych ma zero lub jeden element. Aby skonwertować opcję na tablicę, użyj [`Option.toArray`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#toArray) . Aby skonwertować opcję na listę, użyj [`Option.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#toList) .

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka F #](index.md)
- [Typy F#](fsharp-types.md)
