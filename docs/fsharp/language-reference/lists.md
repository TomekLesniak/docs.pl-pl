---
title: Listy
description: 'Zapoznaj się z listami języka F #, uporządkowaną, niemodyfikowalną serią elementów tego samego typu.'
ms.date: 08/13/2020
ms.openlocfilehash: 567731eb57b77d60d3dd847630d5676e8d047d09
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720351"
---
# <a name="lists"></a>Listy

Lista w F # to uporządkowana, niezmienna seria elementów tego samego typu. Aby wykonać podstawowe operacje na listach, użyj funkcji w [module list](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).

## <a name="creating-and-initializing-lists"></a>Tworzenie i Inicjowanie list

Możesz zdefiniować listę, jawnie wymieniając elementy, oddzielając je średnikami i ujęte w nawiasy kwadratowe, jak pokazano w poniższym wierszu kodu.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

Można również umieścić podziały wierszy między elementami, w tym przypadku średniki są opcjonalne. Druga składnia może spowodować bardziej czytelny kod, gdy wyrażenia inicjowania elementu są dłuższe lub jeśli chcesz dołączyć komentarz dla każdego elementu.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

Zwykle wszystkie elementy listy muszą być tego samego typu. Wyjątek polega na tym, że lista, w której elementy są określone jako typ podstawowy może mieć elementy, które są typami pochodnymi. W związku z tym następujące elementy są dopuszczalne, ponieważ obie `Button` i `CheckBox` pochodzą od `Control` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

Można również zdefiniować elementy listy przy użyciu zakresu wskazywanego przez liczby całkowite oddzielone operatorem zakresu ( `..` ), jak pokazano w poniższym kodzie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

Pusta lista jest określana przez parę nawiasów kwadratowych, w których nie ma niczego między nimi.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

Możesz również użyć wyrażenia sekwencji, aby utworzyć listę. Aby uzyskać więcej informacji, zobacz [wyrażenia sekwencji](sequences.md#sequence-expressions) . Na przykład poniższy kod tworzy listę kwadratów liczb całkowitych z zakresu od 1 do 10.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a>Operatory pracy z listami

Możesz dołączyć elementy do listy za pomocą `::` operatora (wady). Jeśli `list1` jest `[2; 3; 4]` , poniższy kod tworzy `list2` jako `[100; 2; 3; 4]` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

Można łączyć listy z zgodnymi typami przy użyciu `@` operatora, jak w poniższym kodzie. Jeśli `list1` jest `[2; 3; 4]` i `list2` ma `[100; 2; 3; 4]` , ten kod tworzy `list3` jako `[2; 3; 4; 100; 2; 3; 4]` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

Funkcje do wykonywania operacji na listach są dostępne w [module list](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).

Ponieważ listy w języku F # są niezmienne, wszelkie operacje modyfikacji generują nowe listy zamiast modyfikować istniejące.

Listy w języku F # są implementowane jako pojedynczo połączone listy, co oznacza, że operacje, które uzyskują dostęp tylko do nagłówka listy, mają wartość O (1), a dostęp do elementów to O (*n*).

## <a name="properties"></a>Właściwości

Typ listy obsługuje następujące właściwości:

|Właściwość|Typ|Opis|
|--------|----|-----------|
|[Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head)|`'T`|Pierwszy element.|
|[Ciągiem](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Empty)|`'T list`|Właściwość statyczna zwracająca pustą listę odpowiedniego typu.|
|[IsEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#IsEmpty)|`bool`|`true` Jeśli lista nie zawiera żadnych elementów.|
|[Element](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Item)|`'T`|Element o określonym indeksie (liczony od zera).|
|[Długość](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Length)|`int`|Liczba elementów.|
|[Tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail)|`'T list`|Lista bez pierwszego elementu.|

Poniżej przedstawiono kilka przykładów użycia tych właściwości.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]

## <a name="using-lists"></a>Korzystanie z list

Programowanie za pomocą list umożliwia wykonywanie złożonych operacji przy użyciu niewielkiej ilości kodu. W tej sekcji opisano typowe operacje na listach, które są ważne dla programowania funkcjonalnego.

### <a name="recursion-with-lists"></a>Rekursja z listami

Listy są jednoznacznie dostosowane do technik programowania cyklicznego. Należy wziąć pod uwagę operację, która musi zostać wykonana dla każdego elementu listy. Można to zrobić cyklicznie, działając na początku listy, a następnie przekazując ogon listy, czyli mniejszą listę, która składa się z oryginalnej listy bez pierwszego elementu, z powrotem do następnego poziomu rekursji.

Aby napisać taką funkcję cykliczną, należy użyć operatora wad ( `::` ) we wzorcu dopasowywania, który umożliwia rozdzielenie nagłówka listy od ogona.

Poniższy przykład kodu pokazuje, jak używać dopasowywania wzorców do implementowania funkcji cyklicznej, która wykonuje operacje na liście.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

Poprzedni kod działa dobrze w przypadku małych list, ale dla większych list może przekroczyć stos. Poniższy kod Ulepsza ten kod przy użyciu argumentu akumulowana, standardowej techniki pracy z funkcjami cyklicznymi. Użycie argumentu akumulowana powoduje cykliczne zakończenie funkcji, która zapisuje przestrzeń stosu.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

Funkcja `RemoveAllMultiples` jest funkcją cykliczną, która przyjmuje dwie listy. Pierwsza lista zawiera numery, których wielokrotność zostanie usunięta, a druga lista to lista, z której mają zostać usunięte liczby. W poniższym przykładzie kod używa tej funkcji cyklicznej, aby wyeliminować wszystkie niepodstawowe numery z listy, pozostawiając w wyniku listę numerów pierwszych.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

Wynik jest następujący:

```console
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a>Funkcje modułu

[Moduł list](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html) zawiera funkcje, które uzyskują dostęp do elementów listy. Element główny jest najszybszy i najłatwiejszy do uzyskania dostępu. Użyj właściwości [głównego](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) lub listy funkcji modułu [.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head) Można uzyskać dostęp do ogona listy za pomocą właściwości [tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail) lub funkcji [list. tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail) . Aby znaleźć element według indeksu, użyj funkcji [list. n](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) . `List.nth` przechodzi listę. W związku z tym to O (*n*). Jeśli kod `List.nth` jest często używany, warto rozważyć użycie tablicy zamiast listy. Dostęp do elementów w tablicach ma (1).

### <a name="boolean-operations-on-lists"></a>Operacje logiczne na listach

Funkcja [list. IsEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty) określa, czy lista zawiera dowolne elementy.

Funkcja [list. Exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists) stosuje test logiczny do elementów listy i zwraca, `true` Jeśli którykolwiek element spełnia testy. [List. exists2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) jest podobny, ale działa na kolejnych parach elementów na dwóch listach.

Poniższy kod ilustruje użycie `List.exists` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet1.fs)]

Wynik jest następujący:

```console
For list [0; 1; 2; 3], contains zero is true
```

Poniższy przykład ilustruje użycie `List.exists2` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet2.fs)]

Wynik jest następujący:

```console
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

Możesz użyć [list. ForAll](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall) , jeśli chcesz sprawdzić, czy wszystkie elementy listy spełniają warunek.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet3.fs)]

Wynik jest następujący:

```console
true
false
```

Podobnie, [list. forall2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) określa, czy wszystkie elementy w odpowiednich pozycjach na dwóch listach spełniają wyrażenie logiczne, które obejmuje każdą parę elementów.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet4.fs)]

Wynik jest następujący:

```console
true
false
```

### <a name="sort-operations-on-lists"></a>Operacje sortowania na listach

Listy sortowania list [. Sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort), [list. SortBy —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy)oraz [list. sortWith —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith) . Funkcja sortowania określa, które z tych trzech funkcji mają być używane. `List.sort` używa domyślnego porównania ogólnego. Porównanie ogólne używa operatorów globalnych opartych na funkcji porównania generycznej do porównywania wartości. Wydajnie współpracuje z szeroką gamą typów elementów, takimi jak proste typy liczbowe, krotki, rekordy, związki rozłączne, listy, tablice i dowolny typ, który implementuje `System.IComparable` . Dla typów, które implementują `System.IComparable` , porównanie ogólne używa `System.IComparable.CompareTo()` funkcji. Porównanie ogólne działa również z ciągami, ale używa niezależnej od kultury kolejności sortowania. Porównania generycznego nie należy używać w przypadku nieobsługiwanych typów, takich jak typy funkcji. Ponadto wydajność domyślnego porównania ogólnego jest Najlepsza dla małych typów strukturalnych; w przypadku większych typów strukturalnych, które muszą być porównywane i sortowane często, należy rozważyć zaimplementowanie `System.IComparable` i zapewnienie wydajnej implementacji `System.IComparable.CompareTo()` metody.

`List.sortBy` przyjmuje funkcję zwracającą wartość, która jest używana jako kryterium sortowania i `List.sortWith` Pobiera funkcję porównania jako argument. Te ostatnie dwie funkcje są przydatne podczas pracy z typami, które nie obsługują porównania, lub gdy porównanie wymaga bardziej złożonej semantyki porównania, tak jak w przypadku ciągów z obsługą kultury.

Poniższy przykład ilustruje użycie `List.sort` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet5.fs)]

Wynik jest następujący:

```console
[-2; 1; 4; 5; 8]
```

Poniższy przykład ilustruje użycie `List.sortBy` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet6.fs)]

Wynik jest następujący:

```console
[1; -2; 4; 5; 8]
```

W następnym przykładzie pokazano użycie `List.sortWith` . W tym przykładzie funkcja porównywania niestandardowego `compareWidgets` służy do pierwszego porównania jednego pola typu niestandardowego, a następnie drugiego, gdy wartości pierwszego pola są równe.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet7.fs)]

Wynik jest następujący:

```console
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a>Operacje wyszukiwania na listach

Dla list są obsługiwane liczne operacje wyszukiwania. Najprostszy, [list. Find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find), umożliwia znalezienie pierwszego elementu, który jest zgodny z danym warunkiem.

Poniższy przykład kodu demonstruje użycie programu `List.find` w celu znalezienia pierwszego numeru, który jest podzielny przez 5 na liście.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet8.fs)]

Wynik to 5.

Jeśli elementy muszą zostać przekształcone w pierwszej kolejności, wywołaj [listę. pobranie](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick), która pobiera funkcję, która zwraca opcję, i szuka pierwszej wartości opcji, która jest `Some(x)` . Zamiast zwracać element, `List.pick` zwraca wynik `x` . Jeśli nie zostanie znaleziony pasujący element, `List.pick` zgłosi `System.Collections.Generic.KeyNotFoundException` . Poniższy kod ilustruje użycie `List.pick` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet9.fs)]

Wynik jest następujący:

```console
"b"
```

Inna grupa operacji wyszukiwania, [list. tryFind —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) i powiązanych funkcji, zwracają wartość opcji. `List.tryFind`Funkcja zwraca pierwszy element listy, który spełnia warunek, jeśli taki element istnieje, ale wartość opcji, `None` Jeśli nie. Lista wariacji [. tryFindIndex —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) zwraca indeks elementu, jeśli został znaleziony, a nie sam element. Te funkcje są zilustrowane w poniższym kodzie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet10.fs)]

Wynik jest następujący:

```console
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a>Operacje arytmetyczne na listach

Typowe operacje arytmetyczne, takie jak sum i Average, są wbudowane w [moduł listy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html). Aby można było korzystać z [list. sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum), typ elementu listy musi obsługiwać `+` operatora i mieć wartość zerową. Wszystkie wbudowane typy arytmetyczne spełniają te warunki. Aby można było korzystać z [listy. Average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average), typ elementu musi obsługiwać dzielenie bez reszty, która wyklucza typy całkowite, ale pozwala na używanie zmiennoprzecinkowych typów. Funkcje [list. sumBy —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy) i [list. averageBy —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy) przyjmują funkcję jako parametr, a wyniki tej funkcji są używane do obliczania wartości sum lub średniej.

Poniższy kod ilustruje użycie `List.sum` , `List.sumBy` , i `List.average` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet11.fs)]

Wynik to `1.000000`.

Poniższy kod ilustruje użycie `List.averageBy` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet12.fs)]

Wynik to `5.5`.

### <a name="lists-and-tuples"></a>Listy i krotki

Listy zawierające krotki mogą być przetwarzane przy użyciu funkcji zip i rozpakowania. Te funkcje łączą dwie listy pojedynczych wartości w jedną listę spójnych kolekcji lub dzielą jedną listę krotek na dwie listy pojedynczych wartości. Najprostsza funkcja [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) pobiera dwie listy pojedynczych elementów i tworzy pojedynczą listę par krotek. Inna wersja, [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3), pobiera trzy listy pojedynczych elementów i tworzy pojedynczą listę krotek, które mają trzy elementy. Poniższy przykład kodu demonstruje użycie `List.zip` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet13.fs)]

Wynik jest następujący:

```console
[(1, -1); (2, -2); (3; -3)]
```

Poniższy przykład kodu demonstruje użycie `List.zip3` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet14.fs)]

Wynik jest następujący:

```console
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

Odpowiednie wersje rozpakować, [list. rozpakować](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip) i [list. unzip3 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3), przyjmują listy krotek i listy zwracane w spójnej kolekcji, gdzie pierwsza lista zawiera wszystkie elementy, które wcześniej znajdowały się w każdej kolekcji, a druga lista zawiera drugi element każdej krotki itd.

Poniższy przykład kodu demonstruje użycie [list.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip)rozpakowywanie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet15.fs)]

Wynik jest następujący:

```console
([1; 3], [2; 4])
[1; 3] [2; 4]
```

Poniższy przykład kodu demonstruje użycie [list. unzip3 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet16.fs)]

Wynik jest następujący:

```console
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a>Działa na elementach listy

Język F # obsługuje wiele operacji na elementach listy. Najprostszą jest [Lista. ITER](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter), która umożliwia wywoływanie funkcji dla każdego elementu listy. Wariacje obejmują [list. iter2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2), które umożliwiają wykonywanie operacji na elementach dwóch list, [list. iteri —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri), które przypominają, `List.iter` że indeks każdego elementu jest przenoszona jako argument do funkcji, która jest wywoływana dla każdego elementu, i [list. iteri2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2), który jest kombinacją funkcji `List.iter2` i `List.iteri` . Poniższy przykład kodu ilustruje te funkcje.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet17.fs)]

Wynik jest następujący:

```console
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

Inna często używana funkcja, która przekształca elementy listy to [list. map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map), która umożliwia zastosowanie funkcji do każdego elementu listy i umieszczenie wszystkich wyników w nowej liście. [List. MAP2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) i [list. map3 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) są odmianami, które pobierają wiele list. Można również użyć [list. MAPI](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi) i [list. mapi2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2), jeśli oprócz elementu, funkcja musi zostać przeniesiona indeks każdego elementu. Jedyną różnicą między `List.mapi2` i `List.mapi` jest to, że `List.mapi2` Program współpracuje z dwiema listami. Poniższy przykład ilustruje [list. map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet18.fs)]

Wynik jest następujący:

```console
[2; 3; 4]
```

W poniższym przykładzie pokazano użycie `List.map2` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet19.fs)]

Wynik jest następujący:

```console
[5; 7; 9]
```

W poniższym przykładzie pokazano użycie `List.map3` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet20.fs)]

Wynik jest następujący:

```console
[7; 10; 13]
```

W poniższym przykładzie pokazano użycie `List.mapi` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet21.fs)]

Wynik jest następujący:

```console
[1; 3; 5]
```

W poniższym przykładzie pokazano użycie `List.mapi2` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet22.fs)]

Wynik jest następujący:

```console
[0; 7; 18]
```

[List. Collect](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) przypomina `List.map` , z tą różnicą, że każdy element tworzy listę i wszystkie te listy są łączone w ostateczną listę. W poniższym kodzie każdy element listy generuje trzy liczby. Wszystkie te dane są zbierane w jednej liście.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet23.fs)]

Wynik jest następujący:

```console
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

Można również użyć [list. Filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter), który przyjmuje warunek logiczny i tworzy nową listę, która składa się tylko z elementów, które spełniają określony warunek.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet24.fs)]

Lista wyników `[2; 4; 6]` .

Kombinacja map i filtru, [list. Choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) umożliwia przekształcanie i zaznaczanie elementów w tym samym czasie. `List.choose` stosuje funkcję, która zwraca opcję do każdego elementu listy i zwraca nową listę wyników dla elementów, gdy funkcja zwraca wartość opcji `Some` .

Poniższy kod ilustruje użycie `List.choose` do zaznaczania wersalików wyrazów z listy wyrazów.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet25.fs)]

Wynik jest następujący:

```console
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a>Działa na wielu listach

Listy można łączyć ze sobą. Aby dołączyć dwie listy do jednej, użyj [list. Append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append). Aby dołączyć więcej niż dwie listy, użyj [list. Concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet26.fs)]

### <a name="fold-and-scan-operations"></a>Operacje składania i skanowania

Niektóre operacje na listach obejmują wzajemne zależności między wszystkimi elementami listy. Operacje składania i skanowania są podobne `List.iter` i `List.map` w przypadku wywołania funkcji dla każdego elementu, ale te operacje zapewniają dodatkowy parametr o nazwie *akumulowana* , który przenosi informacje za pomocą obliczeń.

Służy `List.fold` do wykonywania obliczeń na liście.

Poniższy przykład kodu demonstruje użycie [list. zgięcie](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) do wykonywania różnych operacji.

Lista jest przesunięta; akumulacja `acc` jest wartością, która jest przenoszona wraz z przeprowadzeniem obliczeń. Pierwszy argument przyjmuje wartość akumulowana i element list i zwraca pośredni wynik obliczeń dla tego elementu listy. Drugi argument jest początkową wartością akumulowana.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet27.fs)]

Wersje tych funkcji, które mają cyfrę w nazwie funkcji, działają na więcej niż jednej liście. Na przykład, [list. fold2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) wykonuje obliczenia na dwóch listach.

Poniższy przykład ilustruje użycie `List.fold2` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet28.fs)]

`List.fold` and [list. Scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) różni się, która `List.fold` zwraca końcową wartość dodatkowego parametru, ale `List.scan` zwraca listę wartości pośrednich (wraz z wartością końcową) dodatkowego parametru.

Każda z tych funkcji zawiera odwrotną odmianę, na przykład [list. foldBack —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack), która różni się w kolejności, w jakiej jest przesunięty listy, i kolejności argumentów. Ponadto `List.fold` i `List.foldBack` mają różne odmiany, [list. fold2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) i [list. foldBack2 —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2), które pobierają dwie listy o równej długości. Funkcja, która jest wykonywana dla każdego elementu, może użyć odpowiednich elementów obu list do wykonania pewnej akcji. Typy elementów dwóch list mogą być różne, jak w poniższym przykładzie, w którym jedna lista zawiera kwoty transakcji dla konta bankowego, a druga lista zawiera typ transakcji: kaucja lub wycofanie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet29.fs)]

W przypadku obliczeń, takich jak suma `List.fold` i `List.foldBack` ma ten sam skutek, ponieważ wynik nie zależy od kolejności przechodzenia. W poniższym przykładzie `List.foldBack` jest używany do dodawania elementów na liście.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet30.fs)]

Poniższy przykład zwraca dane do przykładu konta bankowego. Tym razem zostanie dodany nowy typ transakcji: Obliczanie odsetek. Saldo końcowe jest teraz zależne od kolejności transakcji.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet34.fs)]

Lista funkcji [. Redukcja](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) jest nieco taka sama jak `List.fold` i `List.scan` , z tą różnicą, że zamiast przechodzenia do innego akumulowana, `List.reduce` przyjmuje funkcję, która przyjmuje dwa argumenty typu elementu zamiast tylko jednego, a jeden z tych argumentów pełni rolę akumulowana, co oznacza, że przechowuje wynik pośredni obliczenia. `List.reduce` zaczyna się od działania pierwszego z dwóch elementów listy, a następnie używa wyniku operacji wraz z następnym elementem. Ponieważ nie istnieje oddzielny obiekt, który ma własny typ, może być używany zamiast tylko wtedy, gdy obiekt, który ma ten `List.reduce` `List.fold` sam typ i typ elementu. Poniższy kod ilustruje użycie `List.reduce` . `List.reduce` zgłasza wyjątek, jeśli podana lista nie zawiera żadnych elementów.

W poniższym kodzie, pierwsze wywołanie do wyrażenia lambda otrzymuje argumenty 2 i 4 i zwraca 6, a następne wywołanie otrzymuje argumenty 6 i 10, więc wynik wynosi 16.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet33.fs)]

### <a name="converting-between-lists-and-other-collection-types"></a>Konwertowanie między listami i innymi typami kolekcji

`List`Moduł zawiera funkcje do konwersji do i z obu sekwencji i tablic. Aby przekonwertować sekwencję na lub z sekwencji, użyj [list. toSeq —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) lub [list. ofSeq —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq). Aby przekonwertować na tablicę lub z niej, użyj [list. ToArray —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) lub [list. ofArray —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray).

### <a name="additional-operations"></a>Dodatkowe operacje

Aby uzyskać informacje na temat dodatkowych operacji na listach, zobacz temat informacje o [bibliotece.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka F #](index.md)
- [Typy F#](fsharp-types.md)
- [Sekwencje](sequences.md)
- [Tablice](arrays.md)
- [Opcje](options.md)
