---
title: Wycinki
description: 'Dowiedz się, jak używać wycinków dla istniejących typów danych F # i jak definiować własne wycinki dla innych typów danych.'
ms.date: 12/23/2019
ms.openlocfilehash: d3ddb2c247c36a85842f565f051372c5f2c9a9e9
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559014"
---
# <a name="slices"></a>Wycinki

W języku F # wycinek jest podzbiorem dowolnego typu danych, który ma `GetSlice` metodę w definicji lub w [rozszerzeniu typu](type-extensions.md)w zakresie. Jest najczęściej używany z tablicami i listami języka F #. W tym artykule wyjaśniono, jak korzystać z wycinków z istniejących typów języka F # i jak definiować własne wycinki.

Wycinki są podobne do [indeksatorów](./members/indexed-properties.md), ale zamiast zwracać jedną wartość z bazowej struktury danych, uzyskują wiele z nich.

W języku F # jest obecnie obsługiwana wewnętrzna obsługa ciągów, list, tablic i tablic 2D.

## <a name="basic-slicing-with-f-lists-and-arrays"></a>Podstawowe cięcie z listami i tablicami języka F #

Najpopularniejsze typy danych, które są pofragmentowane, to listy i tablice języka F #. Poniższy przykład ilustruje, jak to zrobić za pomocą list:

```fsharp
// Generate a list of 100 integers
let fullList = [ 1 .. 100 ]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullList.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullList.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullList.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

Tablice odcięć są podobne do list wycinków:

```fsharp
// Generate an array of 100 integers
let fullArray = [| 1 .. 100 |]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullArray.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullArray.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullArray.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

## <a name="slicing-multidimensional-arrays"></a>Dzielenie tablic wielowymiarowych

Język F # obsługuje tablice wielowymiarowe w podstawowej bibliotece języka F #. Podobnie jak w przypadku tablic jednowymiarowych, wycinki tablic wielowymiarowych mogą być również użyteczne. Jednak wprowadzenie dodatkowych wymiarów zezwala na nieznacznie inną składnię, dzięki czemu można przyjmować plasterki określonych wierszy i kolumn.

W poniższych przykładach pokazano, jak wydzielić tablicę 2D:

```fsharp
// Generate a 3x3 2D matrix
let A = array2D [[1;2;3];[4;5;6];[7;8;9]]
printfn "Full matrix:\n %A" A

// Take the first row
let row0 = A.[0,*]
printfn "Row 0: %A" row0

// Take the first column
let col0 = A.[*,0]
printfn "Column 0: %A" col0

// Take all rows but only two columns
let subA = A.[*,0..1]
printfn "%A" subA

// Take two rows and all columns
let subA' = A.[0..1,*]
printfn "%A" subA'

// Slice a 2x2 matrix out of the full 3x3 matrix
let twoByTwo = A.[0..1,0..1]
printfn "%A" twoByTwo
```

Biblioteka podstawowa F # nie definiuje obecnie `GetSlice` dla tablic 3W. Jeśli chcesz wycinków macierzy 3D lub innych tablic o większej liczbie wymiarów, zdefiniuj `GetSlice` element członkowski samodzielnie.

## <a name="defining-slices-for-other-data-structures"></a>Definiowanie wycinków dla innych struktur danych

Biblioteka podstawowa F # definiuje wycinki dla ograniczonego zestawu typów. Jeśli chcesz zdefiniować wycinki dla większej liczby typów danych, możesz to zrobić w samej definicji typu lub w rozszerzeniu typu.

Na przykład poniżej przedstawiono sposób definiowania wycinków klasy umożliwiającej <xref:System.ArraySegment%601> wygodne manipulowanie danymi:

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(start, finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

Inny przykład użycia <xref:System.Span%601> typów i <xref:System.ReadOnlySpan%601> :

```fsharp
open System

type ReadOnlySpan<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

type Span<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..3] // |2; 3|]
```

## <a name="built-in-f-slices-are-end-inclusive"></a>Wbudowane wycinki języka F # to wszystko końcowe

Wszystkie wycinki wewnętrzne w języku F # są końcowe włącznie; oznacza to, że górna granica jest uwzględniona w wycinku. Dla danego wycinka z indeksem początkowym `x` i końcowym indeksem `y` , powstający wycink będzie zawierać wartość *Yth* .

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="see-also"></a>Zobacz też

- [Właściwości indeksowane](./members/indexed-properties.md)
