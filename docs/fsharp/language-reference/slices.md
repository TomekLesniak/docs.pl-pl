---
title: Wycinki
description: 'Dowiedz się, jak używać wycinków dla istniejących typów danych F # i jak definiować własne wycinki dla innych typów danych.'
ms.date: 12/23/2019
ms.openlocfilehash: a3920ad9e1b205b506aaee92c4606bcebf94feba
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557080"
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

## <a name="built-in-f-empty-slices"></a>Wbudowane puste wycinki języka F #

Listy F #, tablice, sekwencje, ciągi, tablice 2D, tablice 3W i 4D tablice będą generować pusty plasterek, Jeśli składnia może utworzyć wycinek, który nie istnieje.

Rozważ następujące źródła:

```fsharp
let l = [ 1..10 ]
let a = [| 1..10 |]
let s = "hello!"

let emptyList = l.[-2..(-1)]
let emptyArray = a.[-2..(-1)]
let emptyString = s.[-2..(-1)]
```

Deweloperzy języka C# mogą oczekiwać, że nie generują pustego wycinka. Jest to podjęcie decyzji dotyczącej projektu w przypadku, gdy puste kolekcje tworzą w języku F #. Pusta lista języka F # może być złożona z inną listą języka F #, pusty ciąg może zostać dodany do istniejącego ciągu i tak dalej. Może ona często przyjmować plasterki na podstawie wartości przeprowadzonych jako parametry i polegających na odporności poza granice przez produkowanie pustej kolekcji, która pasuje do charakteru składowego kodu F #.

## <a name="fixed-index-slices-for-3d-and-4d-arrays"></a>Wycinków o stałym indeksie dla tablic 3W i 4D

W przypadku tablic języka F # 3D i 4D można poprawić określony indeks i wydzielić Inne wymiary przy użyciu tego indeksu.

Aby to zilustrować, weź pod uwagę następującą tablicę 3W:

*z = 0*
| x\y   | 0 | 1 |
|-------|---|---|
| **0** | 0 | 1 |
| **1** | 2 | 3 |

*z = 1*
| x\y   | 0 | 1 |
|-------|---|---|
| **0** | 4 | 5 |
| **1** | 6 | 7 |

Jeśli chcesz wyodrębnić wycinek `[| 4; 5 |]` z tablicy, użyj wycinka o stałym indeksie.

```fsharp
let dim = 2
let m = Array3D.zeroCreate<int> dim dim dim

let mutable count = 0

for z in 0..dim-1 do
    for y in 0..dim-1 do
        for x in 0..dim-1 do
            m.[x,y,z] <- count
            count <- count + 1

// Now let's get the [4;5] slice!
m.[*, 0, 1]
```

Ostatni wiersz naprawia `y` i `z` indyjskich macierzy 3W i pobiera resztę `x` wartości, które odpowiadają macierzy.

## <a name="see-also"></a>Zobacz też

- [Właściwości indeksowane](./members/indexed-properties.md)
