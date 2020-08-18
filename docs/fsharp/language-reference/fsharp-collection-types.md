---
title: Typy kolekcji
description: 'Dowiedz się więcej o typach kolekcji F # i sposobach ich różnicowania od typów kolekcji .NET.'
ms.date: 08/14/2020
ms.openlocfilehash: 197ba754d632051b5a0bf9c8364d45a1fb932f48
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267285"
---
# <a name="f-collection-types"></a>Typy kolekcji F#

Przeglądając ten temat, można określić, który typ kolekcji języka F # najlepiej odpowiada konkretnym potrzebom. Te typy kolekcji różnią się od typów kolekcji w programie .NET, takich jak te w `System.Collections.Generic` przestrzeni nazw, w których typy kolekcji F # są zaprojektowane z perspektywy programowania funkcjonalnego, a nie z perspektywy zorientowanej obiektowo. Dokładniej tylko kolekcja tablic ma modyfikowalne elementy. W związku z tym podczas modyfikowania kolekcji utworzysz wystąpienie zmodyfikowanej kolekcji zamiast zmieniać oryginalną kolekcję.

Typy kolekcji różnią się również w zależności od typu struktury danych, w której są przechowywane obiekty. Struktury danych, takie jak tabele skrótów, połączone listy i tablice, mają różne charakterystyki wydajności i inny zestaw dostępnych operacji.

## <a name="f-collection-types"></a>Typy kolekcji F#

W poniższej tabeli przedstawiono typy kolekcji języka F #.

|Typ|Opis|Linki powiązane|
|----|-----------|-------------|
|[Lista](https://msdn.microsoft.com/library/c627b668-477b-4409-91ed-06d7f1b3e4a7)|Uporządkowana, niezmienna seria elementów tego samego typu. Zaimplementowane jako lista połączona.|[Listy](lists.md)<br /><br />[List — moduł](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)|
|[Macierzy](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)|Zbiór o stałym rozmiarze, od zera, modyfikowalny dla kolejnych elementów danych, które są tego samego typu.|[Tablice](arrays.md)<br /><br />[Moduł Array](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)<br /><br />[Moduł Array2D](https://msdn.microsoft.com/library/ae1a9746-7817-4430-bcdb-a79c2411bbd3)<br /><br />[Moduł Array3D](https://msdn.microsoft.com/library/c8355e2d-add8-48a4-8aa6-1c57ae74c560)|
|[Sekwencja](https://msdn.microsoft.com/library/2f0c87c6-8a0d-4d33-92a6-10d1d037ce75)|Logiczna seria elementów należących do jednego typu. Sekwencje są szczególnie przydatne w przypadku dużej, uporządkowanej kolekcji danych, ale niekoniecznie używać wszystkich elementów. Poszczególne elementy sekwencji są obliczane tylko w razie potrzeby, dlatego sekwencja może być większa niż lista, jeśli nie wszystkie elementy są używane. Sekwencje są reprezentowane przez `seq<'T>` Typ, który jest aliasem dla `IEnumerable<T>` . W związku z tym każdy typ .NET Framework, który implementuje, `System.Collections.Generic.IEnumerable<'T>` może być używany jako sekwencja.|[Sekwencje](sequences.md)<br /><br />[SEQ — moduł](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684)|
|[Mapa](https://msdn.microsoft.com/library/975316ea-55e3-4987-9994-90897ad45664)|Niezmienny słownik elementów. Dostęp do elementów jest uzyskiwany przez klucz.|[Mapuj moduł](https://msdn.microsoft.com/library/bfe61ead-f16c-416f-af98-56dbcbe23e4f)|
|[Set](https://msdn.microsoft.com/library/50cebdce-0cd7-4c5c-8ebc-f3a9e90b38d8)|Niezmienny zestaw oparty na drzewach binarnych, gdzie porównanie jest funkcją porównywania strukturalnego F #, która potencjalnie używa implementacji `System.IComparable` interfejsu dla wartości kluczy.|[Ustaw moduł](https://msdn.microsoft.com/library/61efa732-d55d-4c32-993f-628e2f98e6a0)|

### <a name="table-of-functions"></a>Tabela funkcji

W tej sekcji porównano funkcje, które są dostępne w typach kolekcji języka F #. Określona jest złożoność obliczeniowa funkcji, gdzie N jest rozmiarem pierwszej kolekcji, a M to rozmiar drugiej kolekcji, jeśli istnieje. Łącznik (-) wskazuje, że ta funkcja jest niedostępna w kolekcji. Ponieważ sekwencje są oceniane opóźnieniem, funkcja taka jak Seq. DISTINCT może mieć wartość O (1), ponieważ zwraca natychmiast, mimo że ma wpływ na wydajność sekwencji podczas wyliczania.

|Funkcja|Tablica|Lista|Sequence|Mapa|Set|Opis|
|--------|-----|----|--------|---|---|-----------|
|łączono|O (N)|O (N)|O (N)|-|-|Zwraca nową kolekcję zawierającą elementy pierwszej kolekcji, a następnie elementy drugiej kolekcji.|
|add|-|-|-|O (Dziennik (N))|O (Dziennik (N))|Zwraca nową kolekcję z dodanym elementem.|
|średnia|O (N)|O (N)|O (N)|-|-|Zwraca średnią elementów w kolekcji.|
|averageBy —|O (N)|O (N)|O (N)|-|-|Zwraca średnią z wyników podanej funkcji zastosowanej do każdego elementu.|
|blit —|O (N)|-|-|-|-|Kopiuje sekcję tablicy.|
|cache|-|-|O (N)|-|-|Oblicza i zapisuje elementy sekwencji.|
|rzutowanie|-|-|O (N)|-|-|Konwertuje elementy na określony typ.|
|następnie|O (N)|O (N)|O (N)|-|-|Stosuje daną funkcję `f` do każdego elementu `x` listy. Zwraca listę zawierającą wyniki dla każdego elementu, gdzie funkcja zwraca `Some(f(x))` .|
|zbieranie|O (N)|O (N)|O (N)|-|-|Stosuje daną funkcję do każdego elementu kolekcji, łączy wszystkie wyniki i zwraca listę połączoną.|
|CompareWith —|-|-|O (N)|-|-|Porównuje dwie sekwencje przy użyciu danej funkcji porównania, elementu według elementu.|
|concat|O (N)|O (N)|O (N)|-|-|Łączy określone Wyliczenie wyliczenia jako jedno połączone Wyliczenie.|
|zawiera|-|-|-|-|O (Dziennik (N))|Zwraca wartość true, jeśli zestaw zawiera określony element.|
|ContainsKey —|-|-|-|O (Dziennik (N))|-|Testuje, czy element znajduje się w domenie mapy.|
|count|-|-|-|-|O (N)|Zwraca liczbę elementów w zestawie.|
|countBy —|-|-|O (N)|-|-|Stosuje funkcję generującą klucz do każdego elementu sekwencji i zwraca sekwencję, która daje unikatowe klucze i ich liczbę wystąpień w oryginalnej sekwencji.|
|kopiowanie|O (N)|-|O (N)|-|-|Kopiuje kolekcję.|
|create|O (N)|-|-|-|-|Tworzy tablicę całych elementów, która początkowo jest podaną wartością.|
|opóźnienie|-|-|O (1)|-|-|Zwraca sekwencję, która jest tworzona na podstawie podanych specyfikacji opóźnionej sekwencji.|
|różnica|-|-|-|-|O (g \* log (N))|Zwraca nowy zestaw z elementami drugiego zestawu usuniętymi z pierwszego zestawu.|
|distinct|||O (1)\*|||Zwraca sekwencję, która nie zawiera zduplikowanych wpisów zgodnie z ogólnym mieszaniem i porównaniem równości dla wpisów. Jeśli element występuje wiele razy w sekwencji, późniejsze wystąpienia są odrzucane.|
|distinctBy —|||O (1)\*|||Zwraca sekwencję, która nie zawiera zduplikowanych wpisów zgodnie z ogólnymi wynikami mieszania i równości w kluczach zwracanych przez daną funkcję generującą klucz. Jeśli element występuje wiele razy w sekwencji, późniejsze wystąpienia są odrzucane.|
|puste|O (1)|O (1)|O (1)|O (1)|O (1)|Tworzy pustą kolekcję.|
|istniejący|O (N)|O (N)|O (N)|O (Dziennik (N))|O (Dziennik (N))|Testuje, czy dowolny element sekwencji spełnia określony predykat.|
|exists2 —|O (min (N, M))|-|O (min (N, M))|||Testuje, czy jakakolwiek para odpowiadających elementów sekwencji wejściowych spełnia dany predykat.|
|fill|O (N)|||||Ustawia zakres elementów tablicy na daną wartość.|
|filtr|O (N)|O (N)|O (N)|O (N)|O (N)|Zwraca nową kolekcję, która zawiera tylko elementy kolekcji, dla których podano określony predykat `true` .|
|find|O (N)|O (N)|O (N)|O (Dziennik (N))|-|Zwraca pierwszy element, dla którego dana funkcja zwraca `true` . Zwraca wartość, `System.Collections.Generic.KeyNotFoundException` Jeśli taki element nie istnieje.|
|FindIndex —|O (N)|O (N)|O (N)|-|-|Zwraca indeks pierwszego elementu tablicy, który spełnia określony predykat. Podnosi `System.Collections.Generic.KeyNotFoundException` , czy żaden element nie spełnia predykatu.|
|FindKey —|-|-|-|O (Dziennik (N))|-|Oblicza funkcję dla każdego mapowania w kolekcji i zwraca klucz pierwszego mapowania, gdzie funkcja zwraca `true` . Jeśli taki element nie istnieje, ta funkcja podnosi `System.Collections.Generic.KeyNotFoundException` .|
|składanie|O (N)|O (N)|O (N)|O (N)|O (N)|Stosuje funkcję do każdego elementu kolekcji, wątkowość argumentu akumulowana przy użyciu obliczenia. Jeśli funkcja wejściowa to f, a elementy to I0... w programie ta funkcja oblicza f (... (f s I0)...) podczas.|
|fold2 —|O (N)|O (N)|-|-|-|Stosuje funkcję do odpowiednich elementów dwóch kolekcji, wątkowość argumentu akumulowana przy użyciu obliczeń. Kolekcje muszą mieć identyczne rozmiary. Jeśli funkcja wejściowa to f, a elementy to I0... w i J0... jN, ta funkcja oblicza f (... (f s I0 J0)...) w jN.|
|foldBack —|O (N)|O (N)|-|O (N)|O (N)|Stosuje funkcję do każdego elementu kolekcji, wątkowość argumentu akumulowana przy użyciu obliczenia. Jeśli funkcja wejściowa to f, a elementy to I0... w programie ta funkcja oblicza I0 f (... (f w s)).|
|Foldback2 —|O (N)|O (N)|-|-|-|Stosuje funkcję do odpowiednich elementów dwóch kolekcji, wątkowość argumentu akumulowana przy użyciu obliczeń. Kolekcje muszą mieć identyczne rozmiary. Jeśli funkcja wejściowa to f, a elementy to I0... w i J0... jN, ta funkcja oblicza J0 f I0 (... (f w jN s)).|
|ForAll|O (N)|O (N)|O (N)|O (N)|O (N)|Testuje, czy wszystkie elementy kolekcji spełniają dany predykat.|
|forall2 —|O (N)|O (N)|O (N)|-|-|Testuje, czy wszystkie odpowiednie elementy kolekcji spełniają daną przebuforowanie predykatu.|
|Pobierz/n|O (1)|O (N)|O (N)|-|-|Zwraca element z kolekcji o podanym indeksie.|
|MTP|-|O (1)|O (1)|-|-|Zwraca pierwszy element kolekcji.|
|init|O (N)|O (N)|O (1)|-|-|Tworzy kolekcję uwzględniającą wymiar i funkcję generatora do obliczenia elementów.|
|initInfinite —|-|-|O (1)|-|-|Generuje sekwencję, która po iteracji zwraca kolejne elementy, wywołując daną funkcję.|
|intersect|-|-|-|-|O (Dziennik dziennika (N) \* (M))|Oblicza część wspólną dwóch zestawów.|
|IntersectMany —|-|-|-|-|O (N1 \* N2...)|Oblicza przecięcie sekwencji zestawów. Sekwencja nie może być pusta.|
|isEmpty|O (1)|O (1)|O (1)|O (1)|-|Zwraca `true` czy kolekcja jest pusta.|
|IsProperSubset —|-|-|-|-|O (g \* log (N))|Zwraca `true` czy wszystkie elementy pierwszego zestawu są w drugim zestawie, i co najmniej jeden element drugiego zestawu nie znajduje się w pierwszym zestawie.|
|isProperSuperset —|-|-|-|-|O (g \* log (N))|Zwraca `true` czy wszystkie elementy drugiego zestawu są w pierwszym zestawie, a co najmniej jeden element pierwszego zestawu nie jest w drugim zestawie.|
|IsSubset —|-|-|-|-|O (g \* log (N))|Zwraca `true` czy wszystkie elementy pierwszego zestawu są w drugim zestawie.|
|isSuperset —|-|-|-|-|O (g \* log (N))|Zwraca `true` czy wszystkie elementy drugiego zestawu są w pierwszym zestawie.|
|Radę|O (N)|O (N)|O (N)|O (N)|O (N)|Stosuje daną funkcję do każdego elementu kolekcji.|
|iteri —|O (N)|O (N)|O (N)|-|-|Stosuje daną funkcję do każdego elementu kolekcji. Liczba całkowita, która jest przenoszona do funkcji wskazuje indeks elementu.|
|iteri2 —|O (N)|O (N)|-|-|-|Stosuje daną funkcję do pary elementów, które są rysowane z dopasowywania indeksów w dwóch tablicach. Liczba całkowita, która jest przenoszona do funkcji wskazuje indeks elementów. Dwie tablice muszą mieć tę samą długość.|
|iter2 —|O (N)|O (N)|O (N)|-|-|Stosuje daną funkcję do pary elementów, które są rysowane z dopasowywania indeksów w dwóch tablicach. Dwie tablice muszą mieć tę samą długość.|
|ostatni|O (1)|O (N)|O (N)|-|-|Zwraca ostatni element w odpowiedniej kolekcji.|
|length|O (1)|O (N)|O (N)|-|-|Zwraca liczbę elementów w kolekcji.|
|map (mapa)|O (N)|O (N)|O (1)|-|-|Kompiluje kolekcję, której elementy są wynikami zastosowania danej funkcji do każdego elementu tablicy.|
|MAP2 —|O (N)|O (N)|O (1)|-|-|Kompiluje kolekcję, której elementy są wynikami zastosowania danej funkcji do odpowiednich elementów dwóch kolekcji parowania. Dwie tablice wejściowe muszą mieć tę samą długość.|
|map3 —|-|O (N)|-|-|-|Kompiluje kolekcję, której elementy są wynikami zastosowania danej funkcji do odpowiednich elementów trzech kolekcji jednocześnie.|
|obsługując|O (N)|O (N)|O (N)|-|-|Kompiluje tablicę, której elementy są wynikami zastosowania danej funkcji do każdego elementu tablicy. Indeks liczby całkowitej, który jest przesyłany do funkcji wskazuje indeks elementu, który jest przekształcany.|
|mapi2 —|O (N)|O (N)|-|-|-|Kompiluje kolekcję, której elementy są wynikami zastosowania danej funkcji do odpowiednich elementów dwóch kolekcji parowania, również przekazywać indeks elementów. Dwie tablice wejściowe muszą mieć tę samą długość.|
|max|O (N)|O (N)|O (N)|-|-|Zwraca największy element w kolekcji, porównując przy użyciu operatora [Max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) .|
|maxBy —|O (N)|O (N)|O (N)|-|-|Zwraca największy element w kolekcji, porównując przy użyciu wartości [Max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) w wyniku funkcji.|
|MaxElement —|-|-|-|-|O (Dziennik (N))|Zwraca największy element w zestawie zgodnie z kolejnością używaną dla zestawu.|
|min|O (N)|O (N)|O (N)|-|-|Zwraca najmniejszy element w kolekcji, porównując przy użyciu operatora [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) .|
|minBy —|O (N)|O (N)|O (N)|-|-|Zwraca najmniejszy element w kolekcji, porównując przy użyciu operatora [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) w wyniku funkcji.|
|MinElement —|-|-|-|-|O (Dziennik (N))|Zwraca najniższy element w zestawie zgodnie z kolejnością używaną dla zestawu.|
|ofArray —|-|O (N)|O (1)|O (N)|O (N)|Tworzy kolekcję zawierającą te same elementy co dana tablica.|
|ofList —|O (N)|-|O (1)|O (N)|O (N)|Tworzy kolekcję zawierającą te same elementy co podaną listę.|
|ofSeq —|O (N)|O (N)|-|O (N)|O (N)|Tworzy kolekcję zawierającą te same elementy co dana sekwencja.|
|Pairwise|-|-|O (N)|-|-|Zwraca sekwencję każdego elementu w sekwencji wejściowej i jej poprzedniku, z wyjątkiem pierwszego elementu, który jest zwracany tylko jako poprzednik drugiego elementu.|
|partition|O (N)|O (N)|-|O (N)|O (N)|Dzieli kolekcję na dwie kolekcje. Pierwsza kolekcja zawiera elementy, dla których dany predykat zwraca `true` , a druga kolekcja zawiera elementy, dla których dany predykat zwraca `false` .|
|permute|O (N)|O (N)|-|-|-|Zwraca tablicę zawierającą wszystkie elementy permuted zgodnie z określoną Permutacją.|
|ukończeniu|O (N)|O (N)|O (N)|O (Dziennik (N))|-|Stosuje daną funkcję do kolejnych elementów, zwracając pierwszy wynik, gdzie funkcja zwraca część. Jeśli funkcja nigdy nie zwraca niektórych, `System.Collections.Generic.KeyNotFoundException` jest wywoływany.|
|readonly|-|-|O (N)|-|-|Tworzy obiekt sekwencji, który jest delegatem do danego obiektu sekwencji. Ta operacja gwarantuje, że rzutowanie typu nie może ponownie odnaleźć i zmodyfikować oryginalnej sekwencji. Na przykład jeśli dana tablica zawiera tablicę, zwracana sekwencja zwróci elementy tablicy, ale nie można rzutować zwracanego obiektu sekwencji do tablicy.|
|zmniejszenie|O (N)|O (N)|O (N)|-|-|Stosuje funkcję do każdego elementu kolekcji, wątkowość argumentu akumulowana przy użyciu obliczenia. Ta funkcja zaczyna się od zastosowania funkcji do pierwszych dwóch elementów, przekazuje ten wynik do funkcji wraz z trzecim elementem i tak dalej. Funkcja zwraca wynik końcowy.|
|reduceBack —|O (N)|O (N)|-|-|-|Stosuje funkcję do każdego elementu kolekcji, wątkowość argumentu akumulowana przy użyciu obliczenia. Jeśli funkcja wejściowa to f, a elementy to I0... w programie ta funkcja oblicza I0 f (... (f iN-1)).|
|remove|-|-|-|O (Dziennik (N))|O (Dziennik (N))|Usuwa element z domeny mapy. Wyjątek nie jest zgłaszany, jeśli element nie jest obecny.|
|Informacja|-|O (N)|-|-|-|Tworzy listę o określonej długości, z każdym elementem ustawionym na daną wartość.|
|Rev|O (N)|O (N)|-|-|-|Zwraca nową listę z elementami w odwrotnej kolejności.|
|skanowanie|O (N)|O (N)|O (N)|-|-|Stosuje funkcję do każdego elementu kolekcji, wątkowość argumentu akumulowana przy użyciu obliczenia. Ta operacja stosuje funkcję do drugiego argumentu i pierwszego elementu listy. Następnie operacja przekazuje ten wynik do funkcji wraz z drugim elementem i tak dalej. Na koniec operacja zwraca listę wyników pośrednich i końcowy wynik.|
|ScanBack —|O (N)|O (N)|-|-|-|Przypomina operację foldBack —, ale zwraca zarówno wynik pośredni, jak i końcowe.|
|pojedynczego|-|-|O (1)|-|O (1)|Zwraca sekwencję, która daje tylko jeden element.|
|set|O (1)|-|-|-|-|Ustawia element tablicy do określonej wartości.|
|Pomiń|-|-|O (N)|-|-|Zwraca sekwencję, która pomija N elementów sekwencji źródłowej, a następnie daje pozostałe elementy sekwencji.|
|SkipWhile —|-|-|O (N)|-|-|Zwraca sekwencję, która podczas iteracji pomija elementy z sekwencji bazowej, gdy dany predykat zwraca, `true` a następnie daje pozostałe elementy sekwencji.|
|sort|O (N \* log (n)) średnia<br /><br />O (N ^ 2) najgorszy przypadek|O (N \* log (n))|O (N \* log (n))|-|-|Sortuje kolekcje według wartości elementu. Elementy są porównywane za pomocą [porównania](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|SortBy —|O (N \* log (n)) średnia<br /><br />O (N ^ 2) najgorszy przypadek|O (N \* log (n))|O (N \* log (n))|-|-|Sortuje daną listę przy użyciu kluczy, które udostępnia dana projekcja. Klucze są porównywane za pomocą [porównania](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlace —|O (N \* log (n)) średnia<br /><br />O (N ^ 2) najgorszy przypadek|-|-|-|-|Sortuje elementy tablicy przez przemieszczenie ich w miejscu i przy użyciu danej funkcji porównywania. Elementy są porównywane za pomocą [porównania](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|SortInPlaceBy —|O (N \* log (n)) średnia<br /><br />O (N ^ 2) najgorszy przypadek|-|-|-|-|Sortuje elementy tablicy przez przemieszczenie ich w miejscu i użycie danego rzutowania dla kluczy. Elementy są porównywane za pomocą [porównania](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|SortInPlaceWith —|O (N \* log (n)) średnia<br /><br />O (N ^ 2) najgorszy przypadek|-|-|-|-|Sortuje elementy tablicy przez zamierzenie jej w miejscu i użycie danej funkcji porównania jako kolejności.|
|sortWith —|O (N \* log (n)) średnia<br /><br />O (N ^ 2) najgorszy przypadek|O (N \* log (n))|-|-|-|Sortuje elementy kolekcji, używając podanej funkcji porównania jako kolejności i zwracając nową kolekcję.|
|Sub|O (N)|-|-|-|-|Kompiluje tablicę zawierającą dany Podzakres, który jest określony przez początkowy indeks i długość.|
|Suma|O (N)|O (N)|O (N)|-|-|Zwraca sumę elementów w kolekcji.|
|sumBy —|O (N)|O (N)|O (N)|-|-|Zwraca sumę wyników, które są generowane przez zastosowanie funkcji do każdego elementu kolekcji.|
|drugorzędn|-|O (1)|-|-|-|Zwraca listę bez jej pierwszego elementu.|
|take (pobierz)|-|-|O (N)|-|-|Zwraca elementy sekwencji do określonej liczby.|
|TakeWhile —|-|-|O (1)|-|-|Zwraca sekwencję, która po iteracji zwraca elementy z sekwencji bazowej, gdy dany predykat zwróci wartość, `true` a następnie zwraca nie więcej elementów.|
|ToArray —|-|O (N)|O (N)|O (N)|O (N)|Tworzy tablicę z danej kolekcji.|
|ToList —|O (N)|-|O (N)|O (N)|O (N)|Tworzy listę z danej kolekcji.|
|toSeq —|O (1)|O (1)|-|O (1)|O (1)|Tworzy sekwencję z danej kolekcji.|
|obciąć|-|-|O (1)|-|-|Zwraca sekwencję, która po wyliczeniu zwraca wartość nie więcej niż N elementów.|
|TryFind —|O (N)|O (N)|O (N)|O (Dziennik (N))|-|Wyszukuje element, który spełnia określony predykat.|
|tryFindIndex —|O (N)|O (N)|O (N)|-|-|Wyszukuje pierwszy element, który spełnia określony predykat i zwraca indeks pasującego elementu, lub `None` Jeśli taki element nie istnieje.|
|TryFindKey —|-|-|-|O (Dziennik (N))|-|Zwraca klucz pierwszego mapowania w kolekcji, który spełnia określony predykat, lub zwraca, `None` Jeśli taki element nie istnieje.|
|tryPick —|O (N)|O (N)|O (N)|O (Dziennik (N))|-|Stosuje daną funkcję do kolejnych elementów, zwracając pierwszy wynik, gdzie funkcja zwraca `Some` dla pewnej wartości. Jeśli taki element nie istnieje, operacja zwraca wartość `None` .|
|unfold|-|-|O (N)|-|-|Zwraca sekwencję zawierającą elementy generowane przez daną obliczenie.|
|unia|-|-|-|-|O (g \* log (N))|Oblicza Unię dwóch zestawów.|
|unionMany —|-|-|-|-|O (N1 \* N2...)|Oblicza Unię sekwencji zestawów.|
|pakowane|O (N)|O (N)|O (N)|-|-|Dzieli listę par na dwie listy.|
|unzip3 —|O (N)|O (N)|O (N)|-|-|Dzieli listę trzykrotnie na trzy listy.|
|okienkowe|-|-|O (N)|-|-|Zwraca sekwencję, która daje ruchome okna zawierające elementy, które są rysowane z sekwencji wejściowej. Każde okno jest zwracane jako nowa tablica.|
|kodu|O (N)|O (N)|O (N)|-|-|Łączy dwie kolekcje w listę par. Dwie listy muszą mieć równe długości.|
|zip3 —|O (N)|O (N)|O (N)|-|-|Łączy trzy kolekcje z listą trzykrotnie. Listy muszą mieć równe długości.|

## <a name="see-also"></a>Zobacz także

- [Typy F#](fsharp-types.md)
- [Dokumentacja języka F #](index.md)
