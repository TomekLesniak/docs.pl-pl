---
title: Eksplorowanie zakresów danych przy użyciu indeksów i zakresów
description: Ten zaawansowany samouczek umożliwia Eksplorowanie danych przy użyciu indeksów i zakresów w celu zbadania ciągłego zakresu sekwencyjnego zestawu danych.
ms.date: 09/11/2020
ms.technology: csharp-fundamentals
ms.custom: mvc
ms.openlocfilehash: cf6c83484332ed517b2326b3fd9d7458f191227e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "90738869"
---
# <a name="indices-and-ranges"></a>Indeksy i zakresy

Zakresy i indeksy zapewniają zwięzłą składnię do uzyskiwania dostępu do pojedynczych elementów lub zakresów w sekwencji.

Z tego samouczka dowiesz się, jak wykonywać następujące czynności:

> [!div class="checklist"]
>
> - Użyj składni dla zakresów w sekwencji.
> - Poznaj decyzje projektowe dotyczące początku i końca każdej sekwencji.
> - Poznaj scenariusze dla <xref:System.Index> typów i <xref:System.Range> .

## <a name="language-support-for-indices-and-ranges"></a>Obsługa języków w przypadku indeksów i zakresów

Ten język obsługuje dwa nowe typy i dwa nowe operatory:

- <xref:System.Index?displayProperty=nameWithType> reprezentuje indeks w sekwencji.
- Indeks od operatora końcowego `^` , który określa, że indeks jest względem końca sekwencji.
- <xref:System.Range?displayProperty=nameWithType> reprezentuje Podzakres sekwencji.
- Operator zakresu `..` , który określa początek i koniec zakresu jako jego operandy.

Zacznijmy od reguł dotyczących indeksów. Weź pod uwagę tablicę `sequence` . `0`Indeks jest taki sam jak `sequence[0]` . `^0`Indeks jest taki sam jak `sequence[sequence.Length]` . Wyrażenie `sequence[^0]` generuje wyjątek, podobnie jak `sequence[sequence.Length]` . Dla dowolnej liczby `n` indeks jest taki `^n` sam jak `sequence[sequence.Length - n]` .

```csharp
string[] words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};              // 9 (or words.Length) ^0
```

Można pobrać ostatni wyraz z `^1` indeksem. Dodaj następujący kod poniżej inicjalizacji:

[!code-csharp[LastIndex](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

Zakres określa *początek* i *koniec* zakresu. Zakresy są na wyłączność, co oznacza, że *koniec* nie znajduje się w zakresie. Zakres `[0..^0]` reprezentuje cały zakres, tak jak `[0..sequence.Length]` reprezentuje cały zakres.

Poniższy kod tworzy Podzakres słowami "Quick", "brązowy" i "Fox". Zawiera `words[1]` `words[3]` . Element `words[4]` nie należy do zakresu. Dodaj następujący kod do tej samej metody. Skopiuj i wklej go u dołu okna interaktywnego.

[!code-csharp[Range](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

Poniższy kod zwraca zakres z "z opóźnieniem" i "Dog". Obejmuje `words[^2]` i `words[^1]` . Indeks końcowy `words[^0]` nie jest uwzględniony. Dodaj również następujący kod:

[!code-csharp[LastRange](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

W poniższych przykładach zostały utworzone zakresy, które są otwarte dla początku, końca lub obu:

[!code-csharp[PartialRange](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

Można również zadeklarować zakresy lub indeksy jako zmienne. Zmienna może być używana wewnątrz `[` `]` znaków i:

[!code-csharp[IndexRangeTypes](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

Poniższy przykład pokazuje wiele przyczyn tego wyboru. Zmodyfikuj `x` , `y` i, `z` Aby wypróbować różne kombinacje. Podczas eksperymentowania Użyj wartości, gdzie `x` jest mniejsza niż `y` i `y` jest mniejsze niż `z` w przypadku prawidłowych kombinacji. Dodaj następujący kod w nowej metodzie. Wypróbuj różne kombinacje:

[!code-csharp[SemanticsExamples](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="type-support-for-indices-and-ranges"></a>Obsługa typów indeksów i zakresów

Indeksy i zakresy zapewniają jednoznaczne, zwięzłą składnię, aby uzyskać dostęp do pojedynczego elementu lub zakresu elementów w sekwencji. Wyrażenie indeksu zwykle zwraca typ elementów sekwencji. Wyrażenie zakresu zwykle zwraca ten sam typ sekwencji co sekwencja źródłowa.

Każdy typ, który zapewnia [indeksator](../programming-guide/indexers/index.md) z <xref:System.Index> <xref:System.Range> parametrem lub jawnie obsługuje odpowiednio indeksy lub zakresy. Indeksator, który przyjmuje jeden <xref:System.Range> parametr, może zwracać inny typ sekwencji, taki jak <xref:System.Span%601?displayProperty=nameWithType> .

> [!IMPORTANT]
> Wydajność kodu przy użyciu operatora Range zależy od typu operandu sekwencji.
>
> Stopień złożoności operatora zakresu zależy od typu sekwencji. Na przykład, jeśli sekwencja jest `string` lub tablicą, wynikiem jest kopia określonej sekcji danych wejściowych, więc złożoność czasu wynosi *O (n)* (gdzie N jest długością zakresu). Z drugiej strony, jeśli jest <xref:System.Span%601?displayProperty=nameWithType> lub a <xref:System.Memory%601?displayProperty=nameWithType> , wynik odwołuje się do tego samego magazynu zapasowego, co oznacza, że nie ma kopii, a operacja ma wartość *O (1)*.
>
> W uzupełnieniu do stopnia złożoności powoduje to dodatkowe alokacje i kopie, co wpływa na wydajność. W kodzie wrażliwym na wydajność Rozważ użycie `Span<T>` lub `Memory<T>` jako typ sekwencji, ponieważ operator zakresu nie przydzieli do nich.

Typ jest możliwy do **zliczenia** , jeśli ma właściwość o nazwie `Length` lub `Count` z dostępną metodę pobierającą i zwracanym typem `int` . Typ z liczbą, która nie obsługuje jawnie indeksów lub zakresów może zapewnić niejawną obsługę. Aby uzyskać więcej informacji, zapoznaj się z sekcją obsługa niejawnych [indeksów](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support) i [Obsługa niejawnego zakresu](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support) w artykule [propozycja funkcji](~/_csharplang/proposals/csharp-8.0/ranges.md). Zakresy korzystające z obsługi niejawnego zakresu zwracają ten sam typ sekwencji co sekwencja źródłowa.

Na przykład następujące typy .NET obsługują zarówno indeksy, jak i zakresy: <xref:System.String> , <xref:System.Span%601> , i <xref:System.ReadOnlySpan%601> . <xref:System.Collections.Generic.List%601>Obsługuje indeksy, ale nie obsługuje zakresów.

<xref:System.Array> ma więcej zachowań złożonych. Pojedyncze tablice wymiarów obsługują zarówno indeksy, jak i zakresy. Wielowymiarowe tablice nie są. Indeksator dla wielowymiarowej tablicy ma wiele parametrów, a nie jeden parametr. Tablice nieregularne, nazywane również tablicą tablic, obsługują zarówno zakresy, jak i indeksatory. Poniższy przykład pokazuje, jak wykonać iterację prostokątnej podsekcji tablicy nieregularnej. Iteruje sekcję w środku, wykluczając pierwsze i ostatnie trzy wiersze, a pierwsze i ostatnie dwie kolumny z każdego zaznaczonego wiersza:

[!code-csharp[JaggedArrays](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_JaggedArrays)]

We wszystkich przypadkach operator zakresu <xref:System.Array> przydziela tablicę do przechowywania zwracanych elementów.

## <a name="scenarios-for-indices-and-ranges"></a>Scenariusze dotyczące indeksów i zakresów

Jeśli chcesz analizować część większej sekwencji, często używasz zakresów i indeksów. Nowa składnia jest przejrzysta w celu odczytu dokładnej części sekwencji. Funkcja lokalna `MovingAverage` przyjmuje <xref:System.Range> jako argument. Następnie Metoda wylicza tylko ten zakres przy obliczaniu wartości minimalnej, maksymalnej i średniej. Wypróbuj następujący kod w projekcie:

[!code-csharp[MovingAverages](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]
