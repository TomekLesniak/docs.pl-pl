---
title: 'Funkcje rekurencyjne: rec — Słowo kluczowe'
description: 'Dowiedz się, w jaki sposób słowo kluczowe "Rec" języka F # jest używane z słowem kluczowym "let" w celu zdefiniowania funkcji cyklicznej.'
ms.date: 08/12/2020
ms.openlocfilehash: 389357bd13cef39b1d07972c1a3167320b61612b
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558715"
---
# <a name="recursive-functions-the-rec-keyword"></a>Funkcje rekurencyjne: rec — Słowo kluczowe

`rec`Słowo kluczowe jest używane razem ze `let` słowem kluczowym w celu zdefiniowania funkcji cyklicznej.

## <a name="syntax"></a>Składnia

```fsharp
// Recursive function:
let rec function-nameparameter-list =
    function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
    function1-body

and function2-nameparameter-list =
    function2-body
...
```

## <a name="remarks"></a>Uwagi

Funkcje cykliczne — funkcje, które wywołują siebie, są jawnie identyfikowane w języku F # ze `rec` słowem kluczowym. `rec`Słowo kluczowe udostępnia nazwę `let` powiązania w treści.

Poniższy przykład pokazuje funkcję cykliczną, która oblicza n- *n*<sup>ty</sup> numer Fibonacci przy użyciu definicji matematycznej.

```fsharp
let fib n =
    match n with
    | 0 | 1 -> 1
    | n -> fib (n-1) + fib (n-2)
```

> [!NOTE]
> W ćwiczenia, kod, taki jak poprzedni przykład, nie jest idealnym rozwiązaniem, ponieważ unecessarily ponownie oblicza wartości, które zostały już obliczone. Jest to spowodowane tym, że nie jest to cykliczne zakończenie, co zostało wyjaśnione w dalszej części tego artykułu.

Metody są niejawnie cykliczne w obrębie typu, w którym są zdefiniowane, co oznacza, że nie ma potrzeby dodawania `rec` słowa kluczowego. Na przykład:

```fsharp
type MyClass() =
    member this.Fib(n) =
        match n with
        | 0 | 1 -> 1
        | n -> this.Fib(n-1) + this.Fib(n-2)
```

Zezwól na powiązania w klasach niejawnie cyklicznie, chociaż. Wszystkie `let` funkcje z ograniczeniami wymagają `rec` słowa kluczowego.

## <a name="tail-recursion"></a>Rekursja ogona

W przypadku niektórych funkcji cyklicznych należy resłużyć do refaktoryzacji bardziej "czystej" definicji dla jednej, która jest [cykliczna](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion). Zapobiega to niepotrzebnemu ponownemu obliczaniu. Na przykład poprzedni generator numerów Fibonacci można napisać ponownie w następujący sposób:

```fsharp
let fib n =
    let rec loop acc1 acc2 n =
        match n with
        | 0 -> acc1
        | 1 -> acc2
        | _ ->
            loop acc2 (acc1 + acc2) (n - 1)
    loop 0 1 n
```

Jest to bardziej skomplikowana implementacja. Generowanie numeru Fibonacci to doskonały przykład algorytmu "algorytmie", który jest matematycznie czysty, ale niewydajny. Kilka aspektów sprawia, że jest to wydajne w języku F #, a pozostałe zdefiniowane cyklicznie:

* Cykliczna funkcja wewnętrzna o nazwie `loop` , która jest wzorcem języka F # idiomatyczne.
* Dwa parametry modułu, które są przekazywane wartości do wywołań cyklicznych.
* Sprawdzenie wartości `n` w celu zwrócenia określonego akumulacji.

Jeśli ten przykład został zapisaną iteracyjnie przy użyciu pętli, kod będzie wyglądać podobnie z dwoma różnymi wartościami sumowania liczb do momentu spełnienia określonego warunku.

Powód, dla którego jest to cykliczne, jest spowodowane tym, że wywołanie cykliczne nie musi zapisywać żadnych wartości w stosie wywołań. Wszystkie obliczane wartości pośrednie są sumowane za pośrednictwem danych wejściowych funkcji wewnętrznej. Pozwala to również kompilatorowi języka F # zoptymalizować kod tak szybko, jakby Zapisano coś takiego jak `while` pętla.

Często należy napisać kod języka F #, który cyklicznie przetwarza coś przy użyciu funkcji wewnętrznej i zewnętrznej, jak pokazano w poprzednim przykładzie. Funkcja wewnętrzna używa rekursji tail, natomiast funkcja zewnętrzna ma lepszy interfejs dla wywołań.

## <a name="mutually-recursive-functions"></a>Funkcje wzajemnie cykliczne

Czasami funkcje są *wzajemnie cykliczne*, co oznacza, że wywołuje postać okręgu, w którym jedna funkcja wywołuje inną funkcję, która z kolei wywołuje pierwszy, z dowolną liczbą wywołań między. Należy zdefiniować takie funkcje razem w jednym `let` powiązaniu, używając `and` słowa kluczowego, aby połączyć je ze sobą.

Poniższy przykład pokazuje dwie funkcje wzajemnie cykliczne.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="recursive-values"></a>Wartości cykliczne

Można również zdefiniować `let` wartość powiązaną z rekursywą. Jest to czasami gotowe do rejestrowania. Za pomocą języka F # 5 i `nameof` funkcji można wykonać następujące czynności:

```fsharp
let rec nameDoubles = nameof nameDoubles + nameof nameDoubles
```

## <a name="see-also"></a>Zobacz też

- [Funkcje](index.md)
