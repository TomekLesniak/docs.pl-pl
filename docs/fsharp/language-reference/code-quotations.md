---
title: Cytaty kodu
description: 'Dowiedz się więcej o cytatach kodu języka F # — funkcja języka, która umożliwia programowe generowanie i Używanie wyrażeń kodu w języku F #.'
ms.date: 08/13/2020
ms.openlocfilehash: dc37fdbd6cd29e5ee94e5c0186dfe2bfeb666f32
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557197"
---
# <a name="code-quotations"></a>Cytaty kodu

W tym artykule opisano *notowania kodu* , funkcję języka, która umożliwia programowe generowanie i Używanie wyrażeń kodu w języku F #. Ta funkcja umożliwia wygenerowanie drzewa składni abstrakcyjnej, które reprezentuje kod F #. Drzewo składni abstrakcyjnej można następnie przetworzyć i przetwarzać w zależności od potrzeb aplikacji. Można na przykład użyć drzewa do wygenerowania kodu F # lub wygenerowania kodu w innym języku.

## <a name="quoted-expressions"></a>Wyrażenia cytowane

*Wyrażenie cytowane* jest wyrażeniem języka F # w kodzie, który jest rozdzielony w taki sposób, że nie jest kompilowany jako część programu, ale zamiast tego jest kompilowany do obiektu, który reprezentuje wyrażenie języka F #. Wyrażenie ujęte w cudzysłów można oznaczyć na jeden z dwóch sposobów: z informacjami o typie lub bez informacji o typie. Jeśli chcesz dołączyć informacje o typie, Użyj symboli i, aby rozdzielić `<@` `@>` wyrażenie ujęte w cudzysłów. Jeśli nie potrzebujesz informacji o typie, Użyj symboli `<@@` i `@@>` . Poniższy kod przedstawia wpisane i niewpisywane cudzysłowy.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

Przechodzenie przez duże drzewo wyrażeń jest szybsze, jeśli nie zostaną uwzględnione informacje o typie. Typ wyniku wyrażenia cytowanego za pomocą wpisanych symboli to `Expr<'T>` , gdzie parametr typu ma typ wyrażenia określony przez algorytm wnioskowania o typie kompilatora F #. W przypadku używania cudzysłowów kodu bez informacji o typie, typ wyrażenia w cudzysłowie jest [wyrażeniem](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html)typu innego niż ogólny. Można wywołać Właściwość [RAW](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr-1.html#Raw) klasy z określonym typem, `Expr` Aby uzyskać obiekt bez typu `Expr` .

Istnieją różne metody statyczne, które umożliwiają programistyczne Generowanie obiektów wyrażeń języka F # w `Expr` klasie bez użycia wyrażeń ujętych w cudzysłów.

Należy zauważyć, że cytat kodu musi zawierać pełne wyrażenie. Na `let` przykład dla powiązania, potrzebna jest zarówno definicja powiązanej nazwy, jak i dodatkowe wyrażenie, które używa powiązania. W pełnej składni jest to wyrażenie zgodne ze `in` słowem kluczowym. Na najwyższego poziomu w module jest to tylko następne wyrażenie w module, ale w cudzysłowie jest to jawnie wymagane.

W związku z tym następujące wyrażenie jest nieprawidłowe.

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

Ale poniższe wyrażenia są prawidłowe.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

Aby oszacować Cytaty w języku F #, należy użyć [ewaluatora oferty f #](https://github.com/fsprojects/FSharp.Quotations.Evaluator). Zapewnia obsługę oceniania i wykonywania obiektów wyrażeń języka F #.

Cytaty języka F # zachowują również informacje dotyczące ograniczenia typu. Rozpatrzmy następujący przykład:

```fsharp
open FSharp.Linq.RuntimeHelpers

let eval q = LeafExpressionConverter.EvaluateQuotation q

let inline negate x = -x
// val inline negate: x: ^a ->  ^a when  ^a : (static member ( ~- ) :  ^a ->  ^a)

<@ negate 1.0 @>  |> eval
```

Ograniczenie generowane przez `inline` funkcję jest zachowywane w kodzie qutoation. `negate`Można teraz ocenić formularz quotated funkcji.

## <a name="expr-type"></a>Typ wyrażenia

Wystąpienie `Expr` typu reprezentuje wyrażenie języka F #. Typy ogólne i nieogólne `Expr` są udokumentowane w dokumentacji biblioteki języka F #. Aby uzyskać więcej informacji, zobacz [FSharp. cudzysłóws i Namespace](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations.html) [. Expr klasy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html).

## <a name="splicing-operators"></a>Łączenie operatorów

Metoda łączenia umożliwia łączenie literałów kodu w znakach z wyrażeniami utworzonymi programowo lub z innej oferty kodu. `%`Operatory i `%%` umożliwiają dodanie obiektu wyrażenia F # do cudzysłowu kodu. Możesz użyć `%` operatora, aby wstawić obiekt wyrażenia z wpisaną do wpisanej cudzysłowu. Użyj `%%` operatora, aby wstawić nieokreślony obiekt wyrażenia do cudzysłowu nietypu. Oba operatory są jednoargumentowymi operatorami prefiksu. W takim przypadku `expr` , jeśli jest wyrażeniem typu untyped `Expr` , poniższy kod jest prawidłowy.

```fsharp
<@@ 1 + %%expr @@>
```

A jeśli `expr` jest wpisanym cytatem typu `Expr<int>` , poniższy kod jest prawidłowy.

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>Przykład

### <a name="description"></a>Opis

Poniższy przykład ilustruje użycie cytatów kodu w celu umieszczenia kodu F # w obiekcie Expression, a następnie drukuje kod F #, który reprezentuje wyrażenie. `println`Zdefiniowano funkcję, która zawiera funkcję cykliczną `print` , która wyświetla obiekt wyrażenia F # (typu `Expr` ) w przyjaznym formacie. Istnieje kilka aktywnych wzorców w modułach [FSharp. Patterns. wzorców](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-patternsmodule.html) i [FSharp. cytats. DerivedPatterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html) , których można użyć do analizowania obiektów wyrażeń. Ten przykład nie obejmuje wszystkich możliwych wzorców, które mogą być wyświetlane w wyrażeniu języka F #. Każdy nierozpoznany wzorzec wyzwala dopasowanie do wzorca wieloznacznego ( `_` ) i jest renderowany przy użyciu `ToString` metody, która w `Expr` typie, pozwala znać Aktywny wzorzec do dodania do wyrażenia dopasowania.

### <a name="code"></a>Kod

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a>Dane wyjściowe

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a>Przykład

### <a name="description"></a>Opis

Można również użyć trzech aktywnych wzorców w [module ExprShape](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html) do przechodzenia między drzewami wyrażeń i mniejszą liczbą aktywnych wzorców. Te aktywne wzorce mogą być przydatne, gdy chcesz przechodzenie przez drzewo, ale nie potrzebujesz wszystkich informacji w większości węzłów. W przypadku używania tych wzorców każde wyrażenie F # pasuje do jednego z następujących trzech wzorców: `ShapeVar` Jeśli wyrażenie jest zmienną, `ShapeLambda` Jeśli wyrażenie jest wyrażeniem lambda lub `ShapeCombination` wyrażenie jest inne. Jeśli przejdziesz do drzewa wyrażenia przy użyciu aktywnych wzorców, jak w poprzednim przykładzie kodu, musisz użyć więcej wzorców, aby obsłużyć wszystkie możliwe typy wyrażeń języka F #, a kod będzie bardziej skomplikowany. Aby uzyskać więcej informacji, zobacz [ExprShape. ShapeVar&#124;ShapeLambda&#124;ShapeCombination — Active Pattern](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html#(%20|ShapeVar|ShapeLambda|ShapeCombination|%20)).

Poniższy przykład kodu może służyć jako podstawa dla bardziej złożonych przechodzenia. W tym kodzie jest tworzone drzewo wyrażenia dla wyrażenia, które obejmuje wywołanie funkcji `add` . Aktywny wzorzec [SpecificCall —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html#(%20|SpecificCall|_|%20)) jest używany do wykrywania dowolnego wywołania `add` w drzewie wyrażenia. Ten Aktywny wzorzec przypisuje argumenty wywołania do `exprList` wartości. W tym przypadku istnieją tylko dwa, więc są one ściągane i funkcja jest wywoływana cyklicznie na argumentach. Wyniki są wstawiane do cudzysłowu kodu, który reprezentuje wywołanie przy `mul` użyciu operatora splice ( `%%` ). `println`Funkcja z poprzedniego przykładu służy do wyświetlania wyników.

Kod w innych gałęziach aktywnego wzorca tylko generuje to samo drzewo wyrażenia, więc jedyną zmianą w wyrażeniu wynikiem jest zmiana z `add` na `mul` .

### <a name="code"></a>Kod

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a>Dane wyjściowe

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka F #](index.md)
