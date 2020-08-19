---
title: Sekwencje
description: 'Dowiedz się, jak używać sekwencji F #, gdy masz dużą, uporządkowaną kolekcję danych, ale niekoniecznie używać wszystkich elementów.'
ms.date: 08/13/2020
ms.openlocfilehash: c84e0aebcc79a595c0ae3b9075648fb629bdd65c
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559040"
---
# <a name="sequences"></a>Sekwencje

*Sekwencja* jest logiczną serią wszystkich elementów jednego typu. Sekwencje są szczególnie przydatne w przypadku dużej, uporządkowanej kolekcji danych, ale niekoniecznie używać wszystkich elementów. Poszczególne elementy sekwencji są obliczane tylko w razie potrzeby, dlatego sekwencja może zapewnić lepszą wydajność niż lista w sytuacjach, w których nie wszystkie elementy są używane. Sekwencje są reprezentowane przez `seq<'T>` Typ, który jest aliasem dla <xref:System.Collections.Generic.IEnumerable%601> . W związku z tym każdy typ .NET, który implementuje <xref:System.Collections.Generic.IEnumerable%601> interfejs, może być używany jako sekwencja. [Moduł SEQ](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html) zapewnia obsługę operacji dla operacji związanych z sekwencjami.

## <a name="sequence-expressions"></a>Wyrażenia sekwencji

*Wyrażenie sekwencji* jest wyrażeniem, którego wynikiem jest sekwencja. Wyrażenia sekwencji mogą przyjmować wiele form. Najprostsza forma określa zakres. Na przykład `seq { 1 .. 5 }` tworzy sekwencję zawierającą pięć elementów, w tym punkty końcowe 1 i 5. Możesz również określić przyrost (lub zmniejszany) między dwoma podwójnymi kropkami. Na przykład poniższy kod tworzy sekwencję wielokrotności 10.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

Wyrażenia sekwencji składają się z wyrażeń F #, które tworzą wartości sekwencji. Można również programowo generować wartości:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

Poprzedni przykład używa `->` operatora, który pozwala określić wyrażenie, którego wartość stanie się częścią sekwencji. Można używać tylko `->` wtedy, gdy każda część kodu, który następuje po zwraca wartość.

Alternatywnie możesz określić `do` słowo kluczowe, używając opcjonalnego `yield` :

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

Poniższy kod generuje listę par współrzędnych wraz z indeksem do tablicy, która reprezentuje siatkę. Należy zauważyć, że pierwsze `for` wyrażenie wymaga `do` określenia.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

`if`Wyrażenie użyte w sekwencji jest filtrem. Na przykład, aby wygenerować sekwencję tylko liczb pierwszych, przy założeniu, że masz funkcję `isprime` typu `int -> bool` , Konstruuj sekwencję w następujący sposób.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

Jak wspomniano wcześniej, w `do` tym miejscu jest wymagane, ponieważ nie ma `else` rozgałęzienia z `if` . Jeśli spróbujesz użyć, otrzymasz komunikat `->` o błędzie informujący, że nie wszystkie gałęzie zwracają wartość.

## <a name="the-yield-keyword"></a>Słowo kluczowe `yield!`

Czasami może być konieczne dołączenie sekwencji elementów do innej sekwencji. Aby dołączyć sekwencję w innej sekwencji, należy użyć `yield!` słowa kluczowego:

```fsharp
// Repeats '1 2 3 4 5' ten times
seq {
    for _ in 1..10 do
        yield! seq { 1; 2; 3; 4; 5}
}
```

Innym sposobem na zastanawianie `yield!` się jest to, że spłaszcza sekwencję wewnętrzną, a następnie dołącza ją w sekwencji zawierającej.

Gdy `yield!` jest używany w wyrażeniu, wszystkie pozostałe pojedyncze wartości muszą używać `yield` słowa kluczowego:

```fsharp
// Combine repeated values with their values
seq {
    for x in 1..10 do
        yield x
        yield! seq { for i in 1..x -> i}
}
```

Poprzedni przykład spowoduje utworzenie wartości `x` oprócz wszystkich wartości z `1` do `x` dla każdego z nich `x` .

## <a name="examples"></a>Przykłady

W pierwszym przykładzie używane jest wyrażenie sekwencji zawierające iterację, filtr i wartość Yield do wygenerowania tablicy. Ten kod drukuje sekwencję numerów pierwszych z zakresu od 1 do 100 w konsoli programu.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

Poniższy przykład tworzy tabelę mnożenia, która składa się z krotek trzech elementów, z których każdy składa się z dwóch czynników i produktu:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

Poniższy przykład ilustruje użycie, `yield!` Aby połączyć poszczególne sekwencje w jedną końcową sekwencję. W takim przypadku sekwencje dla każdego poddrzewa w drzewie binarnym są łączone w funkcji cyklicznej, aby utworzyć ostateczną sekwencję.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]

## <a name="using-sequences"></a>Używanie sekwencji

Sekwencje obsługują wiele takich samych funkcji, jak [listy](lists.md). Sekwencje obsługują również operacje, takie jak grupowanie i zliczanie przy użyciu funkcji generujących klucze. Sekwencje obsługują również bardziej różnorodne funkcje wyodrębniania podsekwencji.

Wiele typów danych, takich jak listy, tablice, zestawy i mapy, to niejawne sekwencje, ponieważ są wyliczalnymi kolekcjami. Funkcja, która przyjmuje sekwencję jako argument, działa z dowolnym ze wspólnych typów danych F #, oprócz dowolnego typu danych platformy .NET, który implementuje `System.Collections.Generic.IEnumerable<'T>` . W przeciwieństwie do funkcji, która przyjmuje listę jako argument, który może przyjmować tylko listy. Typ `seq<'T>` jest skrótem typu dla `IEnumerable<'T>` . Oznacza to, że każdy typ implementujący rodzaj ogólny `System.Collections.Generic.IEnumerable<'T>` , który obejmuje tablice, listy, zestawy i mapy w języku F #, a także większość typów kolekcji .NET, jest zgodny z `seq` typem i można go używać wszędzie tam, gdzie jest oczekiwana sekwencja.

## <a name="module-functions"></a>Funkcje modułu

[Moduł SEQ](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html) w [przestrzeni nazw FSharp. Collections](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections.html) zawiera funkcje do pracy z sekwencjami. Te funkcje działają również z listami, tablicami, mapami i zestawami, ponieważ wszystkie te typy są wyliczalne i dlatego mogą być traktowane jako sekwencje.

## <a name="creating-sequences"></a>Tworzenie sekwencji

Sekwencje można tworzyć przy użyciu wyrażeń sekwencji, jak opisano wcześniej lub korzystając z określonych funkcji.

Można utworzyć pustą sekwencję przy użyciu [SEQ. Empty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#empty)lub można utworzyć sekwencję tylko jednego określonego elementu przy użyciu [SEQ. singleton](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#singleton).

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet9.fs)]

Za pomocą [Seq.init](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#init) można utworzyć sekwencję, dla której elementy są tworzone za pomocą podania funkcji. Możesz również podać rozmiar sekwencji. Ta funkcja jest tak samo jak [List.init](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#init), z tą różnicą, że elementy nie są tworzone, dopóki nie przeprowadzisz iteracji przez sekwencję. Poniższy kod ilustruje użycie `Seq.init` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet10.fs)]

Dane wyjściowe to

```console
0 10 20 30 40
```

Za pomocą [SEQ. ofArray —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#ofArray) i [seq. ofList —&#60;&#62; funkcji](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#ofList)można tworzyć sekwencje z tablic i list. Można jednak skonwertować tablice i listy na sekwencje przy użyciu operatora rzutowania. W poniższym kodzie przedstawiono obie techniki.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet11.fs)]

Za pomocą [SEQ. Cast](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#cast)można utworzyć sekwencję z niejednoznacznie wpisanej kolekcji, takiej jak te zdefiniowane w `System.Collections` . Takie kolekcje o jednoznacznie określonym typie mają typ elementu `System.Object` i są wyliczane przy użyciu typu niegenerycznego `System.Collections.Generic.IEnumerable&#96;1` . Poniższy kod ilustruje użycie programu `Seq.cast` w celu przekonwertowania na `System.Collections.ArrayList` sekwencję.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet12.fs)]

Można zdefiniować nieskończone sekwencje przy użyciu funkcji [Seq.initInfinite](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#initInfinite) . Dla takiej sekwencji można dostarczyć funkcję, która generuje każdy element z indeksu elementu. Nieskończone sekwencje są możliwe z powodu oceny z opóźnieniem; elementy są tworzone zgodnie z wymaganiami, wywołując funkcję, którą określisz. Poniższy przykład kodu tworzy nieskończoną sekwencję liczb zmiennoprzecinkowych, w tym przypadku przemienny szereg reciprocals kwadratów kolejnych liczb całkowitych.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet13.fs)]

[SEQ. unfold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#unfold) generuje sekwencję z funkcji obliczeniowej, która przyjmuje stan i przekształca ją w celu utworzenia każdego kolejnego elementu w sekwencji. Stan to tylko wartość, która jest używana do obliczenia każdego elementu i może ulec zmianie, gdy każdy element jest obliczany. Drugi argument `Seq.unfold` jest wartością początkową, która jest używana do uruchomienia sekwencji. `Seq.unfold` używa typu opcji dla stanu, który umożliwia zakończenie sekwencji przez zwrócenie `None` wartości. Poniższy kod przedstawia dwa przykłady sekwencji `seq1` i `fib` , które są generowane przez `unfold` operację. Pierwszy, `seq1` , jest prostą sekwencją z liczbami do 20. Sekunda, `fib` ,, używa `unfold` do obliczania sekwencji Fibonacci. Ponieważ każdy element w sekwencji Fibonacci jest sumą poprzednich dwóch liczb Fibonacci, wartość stanu jest krotką, która składa się z poprzednich dwóch liczb w sekwencji. Wartość początkowa to `(1,1)` , pierwsze dwie liczby w sekwencji.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet14.fs)]

Wynik jest następujący:

```console
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

Poniższy kod to przykład, który używa wielu funkcji modułu sekwencji opisanych tutaj do generowania i obliczania wartości nieskończonych sekwencji. Uruchomienie kodu może potrwać kilka minut.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet15.fs)]

## <a name="searching-and-finding-elements"></a>Wyszukiwanie i znajdowanie elementów

Funkcje obsługi sekwencji dostępne dla list: [SEQ. Exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#exists), [SEQ. exists2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#exists), [SEQ. Find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#find), [SEQ. FindIndex —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#findIndex), [SEQ. pobranie](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#pick), [SEQ. tryFind —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFind)i [SEQ. tryFindIndex —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFindIndex). Wersje tych funkcji, które są dostępne dla sekwencji, ocenią sekwencję tylko do elementu, który jest wyszukiwany. Aby zapoznać się z przykładami, zobacz [listy](lists.md).

## <a name="obtaining-subsequences"></a>Uzyskiwanie podsekwencji

[SEQ. Filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#filter) i [SEQ. Choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#choose) przypomina odpowiadające im funkcje, które są dostępne dla list, z tą różnicą, że filtrowanie i wybór nie występują do momentu obliczenia elementów sekwencji.

[SEQ. Truncate](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#truncate) tworzy sekwencję z innej sekwencji, ale ogranicza sekwencję do określonej liczby elementów. [SEQ. Take](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#take) tworzy nową sekwencję zawierającą tylko określoną liczbę elementów na początku sekwencji. Jeśli w sekwencji znajduje się mniej elementów niż określono do wykonania, program `Seq.take` wygeneruje `System.InvalidOperationException` . Różnica między `Seq.take` i `Seq.truncate` jest `Seq.truncate` niegenerująca błędu, jeśli liczba elementów jest mniejsza niż liczba określona przez użytkownika.

Poniższy kod przedstawia zachowanie i różnice między `Seq.truncate` i `Seq.take` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet16.fs)]

Dane wyjściowe przed wystąpieniem błędu są następujące.

```console
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
```

Za pomocą [SEQ. TakeWhile —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#takeWhile), można określić funkcję predykatu (funkcję logiczną) i utworzyć sekwencję z innej sekwencji składającej się z tych elementów oryginalnej sekwencji, która jest predykatem `true` , ale zatrzymać przed pierwszym elementem, dla którego zwracany jest predykat `false` . [SEQ. Skip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#skip) zwraca sekwencję, która pomija określoną liczbę pierwszych elementów w innej sekwencji i zwraca pozostałe elementy. [SEQ. SkipWhile —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#skipWhile) zwraca sekwencję, która pomija pierwsze elementy innej sekwencji, tak długo, jak predykat zwraca `true` , a następnie zwraca pozostałe elementy, rozpoczynając od pierwszego elementu, dla którego zwracany jest predykat `false` .

Poniższy przykład kodu ilustruje zachowanie i różnice między `Seq.takeWhile` , `Seq.skip` i `Seq.skipWhile` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet17.fs)]

Dane wyjściowe są następujące:

```console
1 4 9
36 49 64 81 100
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>Przekształcanie sekwencji

[SEQ. parowania](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#pairwise) tworzy nową sekwencję, w której kolejne elementy sekwencji wejściowej są pogrupowane w krotki.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet18.fs)]

[SEQ. Windowd](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#windowed) przypomina `Seq.pairwise` , z tą różnicą, że zamiast tworzenia sekwencji krotek tworzy sekwencję tablic zawierających kopie sąsiadujących elementów ( *okna*) z sekwencji. Należy określić liczbę sąsiadujących elementów, które mają być w każdej tablicy.

Poniższy przykład kodu demonstruje użycie `Seq.windowed` . W takim przypadku liczba elementów w oknie to 3. W przykładzie zastosowano `printSeq` , który jest zdefiniowany w poprzednim przykładzie kodu.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet180.fs)]

Dane wyjściowe są następujące:

Sekwencja początkowa:

```console
1.0 1.5 2.0 1.5 1.0 1.5

Windows of length 3:
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|]

Moving average:
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a>Operacje z wieloma sekwencjami

[Seq.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#zip) i [Seq.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#zip3) mają dwie lub trzy sekwencje i tworzą sekwencję krotek. Te funkcje są podobne do odpowiednich funkcji dostępnych dla [list](lists.md). Nie ma odpowiedniej funkcjonalności do oddzielenia jednej sekwencji na dwie lub więcej sekwencji. Jeśli potrzebujesz tej funkcji dla sekwencji, przekonwertuj sekwencję na listę i użyj funkcji [list. Rozpakuj](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip).

## <a name="sorting-comparing-and-grouping"></a>Sortowanie, porównywanie i grupowanie

Funkcje sortowania obsługiwane dla list również działają z sekwencjami. Obejmuje to [SEQ. Sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sort) i [SEQ. SortBy —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sortBy). Te funkcje iterą przez całą sekwencję.

Można porównać dwie sekwencje przy użyciu funkcji [SEQ. CompareWith —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#compareWith) . Funkcja porównuje kolejne elementy z kolei i przerywa, gdy napotka on pierwszą nierówną parę. Wszelkie dodatkowe elementy nie przyczyniają się do porównania.

Poniższy kod ilustruje użycie `Seq.compareWith` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet19.fs)]

W poprzednim kodzie tylko pierwszy element jest obliczany i sprawdzany, a wynik to-1.

[SEQ. countBy —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#countBy) pobiera funkcję, która generuje wartość o nazwie *Key* dla każdego elementu. Dla każdego elementu jest generowany klucz, wywołując tę funkcję dla każdego elementu. `Seq.countBy` następnie zwraca sekwencję zawierającą wartości klucza oraz liczbę elementów, które wygenerowały każdą wartość klucza.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet201.fs)]

Dane wyjściowe są następujące:

```console
(1, 34) (2, 33) (0, 33)
```

Poprzednie dane wyjściowe pokazują, że wystąpiły 34 elementy oryginalnej sekwencji, która wygenerowała wartości Key 1, 33, które wygenerowały klucz 2 i 33 wartości, które wygenerowały klucz 0.

Elementy sekwencji można grupować przez wywołanie [SEQ. GroupBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#groupBy). `Seq.groupBy` przyjmuje sekwencję i funkcję, która generuje klucz z elementu. Funkcja jest wykonywana na każdym elemencie sekwencji. `Seq.groupBy` zwraca sekwencję krotek, gdzie pierwszy element każdej krotki jest kluczem, a drugi to sekwencja elementów, które tworzą ten klucz.

Poniższy przykład kodu ilustruje użycie programu `Seq.groupBy` do partycjonowania sekwencji liczb z 1 do 100 w trzech grupach, które mają odrębne wartości klucza 0, 1 i 2.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet202.fs)]

Dane wyjściowe są następujące:

```console
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

Można utworzyć sekwencję, która eliminuje zduplikowane elementy przez wywołanie [SEQ. DISTINCT](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#distinct). Można też użyć [SEQ. distinctBy —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#distinctBy), który pobiera funkcję generującą klucz do wywołania dla każdego elementu. Utworzona sekwencja zawiera elementy oryginalnej sekwencji, które mają unikatowe klucze; późniejsze elementy, które generują zduplikowany klucz do wcześniejszego elementu, są odrzucane.

Poniższy przykład kodu ilustruje użycie `Seq.distinct` . `Seq.distinct` jest przedstawiany przez generowanie sekwencji, które reprezentują liczby binarne, a następnie pokazuje, że jedyne różne elementy to 0 i 1.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet22.fs)]

Poniższy kod ilustruje `Seq.distinctBy` , rozpoczynając od sekwencji zawierającej liczby ujemne i dodatnie oraz używając funkcji wartości bezwzględnej jako funkcji generującej klucz. Wynikowa sekwencja nie zawiera wszystkich liczb dodatnich, które odpowiadają liczbom ujemnym w sekwencji, ponieważ liczby ujemne występują wcześniej w sekwencji i w związku z tym są wybierane zamiast liczb dodatnich, które mają taką samą wartość bezwzględną lub klucz.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet23.fs)]

## <a name="readonly-and-cached-sequences"></a>Sekwencje ReadOnly i buforowane

[SEQ. ReadOnly](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#readonly) tworzy kopię sekwencji tylko do odczytu. `Seq.readonly` jest przydatne, gdy masz kolekcję do odczytu i zapisu, na przykład tablicę, i nie chcesz modyfikować oryginalnej kolekcji. Ta funkcja może służyć do zachowywania hermetyzacji danych. W poniższym przykładzie kodu zostanie utworzony typ zawierający tablicę. Właściwość uwidacznia tablicę, ale zamiast zwracać tablicę, zwraca sekwencję utworzoną z tablicy przy użyciu `Seq.readonly` .

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet24.fs)]

[SEQ. cache](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#cache) tworzy przechowywaną wersję sekwencji. Użyj `Seq.cache` , aby uniknąć ponownej oceny sekwencji lub jeśli masz wiele wątków, które używają sekwencji, ale musisz się upewnić, że każdy element jest poddany działaniu tylko jeden raz. Jeśli masz sekwencję, która jest używana przez wiele wątków, możesz mieć jeden wątek, który wylicza i oblicza wartości dla oryginalnej sekwencji, a pozostałe wątki mogą używać sekwencji w pamięci podręcznej.

## <a name="performing-computations-on-sequences"></a>Wykonywanie obliczeń na sekwencjach

Proste operacje arytmetyczne są podobne do tych list, takich jak [SEQ. Average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#average), [SEQ. sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sum), [SEQ. averageBy —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#averageBy), [SEQ. sumBy —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sumBy)i tak dalej.

[SEQ. złożenie](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#fold), [SEQ. Zmniejsz](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#reduce)i [SEQ. Scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#scan) przypomina odpowiednie funkcje, które są dostępne dla list. Sekwencje obsługują podzestaw pełnych wariantów tych funkcji, które obsługują listę. Aby uzyskać więcej informacji i przykładów, zobacz [listy](lists.md).

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka F #](index.md)
- [Typy F#](fsharp-types.md)
