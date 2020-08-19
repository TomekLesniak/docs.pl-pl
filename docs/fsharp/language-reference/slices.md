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
# <a name="slices"></a><span data-ttu-id="cd851-103">Wycinki</span><span class="sxs-lookup"><span data-stu-id="cd851-103">Slices</span></span>

<span data-ttu-id="cd851-104">W języku F # wycinek jest podzbiorem dowolnego typu danych, który ma `GetSlice` metodę w definicji lub w [rozszerzeniu typu](type-extensions.md)w zakresie.</span><span class="sxs-lookup"><span data-stu-id="cd851-104">In F#, a slice is a subset of any data type that has a `GetSlice` method in its definition or in an in-scope [type extension](type-extensions.md).</span></span> <span data-ttu-id="cd851-105">Jest najczęściej używany z tablicami i listami języka F #.</span><span class="sxs-lookup"><span data-stu-id="cd851-105">It is most commonly used with F# arrays and lists.</span></span> <span data-ttu-id="cd851-106">W tym artykule wyjaśniono, jak korzystać z wycinków z istniejących typów języka F # i jak definiować własne wycinki.</span><span class="sxs-lookup"><span data-stu-id="cd851-106">This article explains how to take slices from existing F# types and how to define your own slices.</span></span>

<span data-ttu-id="cd851-107">Wycinki są podobne do [indeksatorów](./members/indexed-properties.md), ale zamiast zwracać jedną wartość z bazowej struktury danych, uzyskują wiele z nich.</span><span class="sxs-lookup"><span data-stu-id="cd851-107">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="cd851-108">W języku F # jest obecnie obsługiwana wewnętrzna obsługa ciągów, list, tablic i tablic 2D.</span><span class="sxs-lookup"><span data-stu-id="cd851-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="cd851-109">Podstawowe cięcie z listami i tablicami języka F #</span><span class="sxs-lookup"><span data-stu-id="cd851-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="cd851-110">Najpopularniejsze typy danych, które są pofragmentowane, to listy i tablice języka F #.</span><span class="sxs-lookup"><span data-stu-id="cd851-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="cd851-111">Poniższy przykład ilustruje, jak to zrobić za pomocą list:</span><span class="sxs-lookup"><span data-stu-id="cd851-111">The following example demonstrates how to do this with lists:</span></span>

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

<span data-ttu-id="cd851-112">Tablice odcięć są podobne do list wycinków:</span><span class="sxs-lookup"><span data-stu-id="cd851-112">Slicing arrays is just like slicing lists:</span></span>

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

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="cd851-113">Dzielenie tablic wielowymiarowych</span><span class="sxs-lookup"><span data-stu-id="cd851-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="cd851-114">Język F # obsługuje tablice wielowymiarowe w podstawowej bibliotece języka F #.</span><span class="sxs-lookup"><span data-stu-id="cd851-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="cd851-115">Podobnie jak w przypadku tablic jednowymiarowych, wycinki tablic wielowymiarowych mogą być również użyteczne.</span><span class="sxs-lookup"><span data-stu-id="cd851-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="cd851-116">Jednak wprowadzenie dodatkowych wymiarów zezwala na nieznacznie inną składnię, dzięki czemu można przyjmować plasterki określonych wierszy i kolumn.</span><span class="sxs-lookup"><span data-stu-id="cd851-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="cd851-117">W poniższych przykładach pokazano, jak wydzielić tablicę 2D:</span><span class="sxs-lookup"><span data-stu-id="cd851-117">The following examples demonstrate how to slice a 2D array:</span></span>

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

<span data-ttu-id="cd851-118">Biblioteka podstawowa F # nie definiuje obecnie `GetSlice` dla tablic 3W.</span><span class="sxs-lookup"><span data-stu-id="cd851-118">The F# core library does not currently define `GetSlice` for 3D arrays.</span></span> <span data-ttu-id="cd851-119">Jeśli chcesz wycinków macierzy 3D lub innych tablic o większej liczbie wymiarów, zdefiniuj `GetSlice` element członkowski samodzielnie.</span><span class="sxs-lookup"><span data-stu-id="cd851-119">If you wish to slice 3D arrays or other arrays of more dimensions, define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="cd851-120">Definiowanie wycinków dla innych struktur danych</span><span class="sxs-lookup"><span data-stu-id="cd851-120">Defining slices for other data structures</span></span>

<span data-ttu-id="cd851-121">Biblioteka podstawowa F # definiuje wycinki dla ograniczonego zestawu typów.</span><span class="sxs-lookup"><span data-stu-id="cd851-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="cd851-122">Jeśli chcesz zdefiniować wycinki dla większej liczby typów danych, możesz to zrobić w samej definicji typu lub w rozszerzeniu typu.</span><span class="sxs-lookup"><span data-stu-id="cd851-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="cd851-123">Na przykład poniżej przedstawiono sposób definiowania wycinków klasy umożliwiającej <xref:System.ArraySegment%601> wygodne manipulowanie danymi:</span><span class="sxs-lookup"><span data-stu-id="cd851-123">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

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

<span data-ttu-id="cd851-124">Inny przykład użycia <xref:System.Span%601> typów i <xref:System.ReadOnlySpan%601> :</span><span class="sxs-lookup"><span data-stu-id="cd851-124">Another example using the <xref:System.Span%601> and <xref:System.ReadOnlySpan%601> types:</span></span>

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

## <a name="built-in-f-slices-are-end-inclusive"></a><span data-ttu-id="cd851-125">Wbudowane wycinki języka F # to wszystko końcowe</span><span class="sxs-lookup"><span data-stu-id="cd851-125">Built-in F# slices are end-inclusive</span></span>

<span data-ttu-id="cd851-126">Wszystkie wycinki wewnętrzne w języku F # są końcowe włącznie; oznacza to, że górna granica jest uwzględniona w wycinku.</span><span class="sxs-lookup"><span data-stu-id="cd851-126">All intrinsic slices in F# are end-inclusive; that is, the upper bound is included in the slice.</span></span> <span data-ttu-id="cd851-127">Dla danego wycinka z indeksem początkowym `x` i końcowym indeksem `y` , powstający wycink będzie zawierać wartość *Yth* .</span><span class="sxs-lookup"><span data-stu-id="cd851-127">For a given slice with starting index `x` and ending index `y`, the resulting slice will include the *yth* value.</span></span>

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="see-also"></a><span data-ttu-id="cd851-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cd851-128">See also</span></span>

- [<span data-ttu-id="cd851-129">Właściwości indeksowane</span><span class="sxs-lookup"><span data-stu-id="cd851-129">Indexed properties</span></span>](./members/indexed-properties.md)
