---
title: Dokumentacja języka
description: 'Znajdź informacje o funkcjach języka F # z tego odwołania do tokenów języka, pojęć, typów, wyrażeń i tematów konstrukcyjnych obsługiwanych przez kompilator.'
ms.date: 05/16/2016
ms.openlocfilehash: e8a6c7ef83c4e2d292cc6a12a59e420708240a39
ms.sourcegitcommit: 09bad6ec0cbf18be7cd7f62e77286d305a18b607
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2020
ms.locfileid: "87795479"
---
# <a name="f-language-reference"></a>Materiały referencyjne dotyczące języka F#

Ta sekcja jest odwołaniem do języka F #, w języku programowania wieloznacznym przeznaczonym dla platformy .NET. Język F # obsługuje funkcjonalne modele programowania, zorientowane obiektowo i bezwzględnie.

## <a name="f-tokens"></a>Tokeny języka F #

W poniższej tabeli przedstawiono tematy referencyjne, które zawierają tabele słów kluczowych, symboli i literałów używanych jako tokeny w języku F #.

|Tytuł|Opis|
|-----|-----------|
|[Odwołanie do słowa kluczowego](keyword-reference.md)|Zawiera linki do informacji o wszystkich słowach kluczowych języka F #.|
|[Odwołanie do symboli i operatorów](./symbol-and-operator-reference/index.md)|Zawiera tabelę symboli i operatorów, które są używane w języku F #.|
|[Literały](literals.md)|Opisuje składnię dla wartości literału w języku F # oraz sposób określania informacji o typie dla literałów języka F #.|

## <a name="f-language-concepts"></a>Pojęcia dotyczące języka F #

W poniższej tabeli przedstawiono dostępne tematy dotyczące języka.

|Tytuł|Opis|
|-----|-----------|
|[Funkcje](./functions/index.md)|Funkcje są podstawową jednostką wykonywania programu w dowolnym języku programowania. Podobnie jak w innych językach, funkcja języka F # ma nazwę, może mieć parametry i przyjmować argumenty i ma treść. Język F # obsługuje również konstrukcje programowania funkcjonalnego, takie jak traktowanie funkcji jako wartości, za pomocą funkcji nienazwanych w wyrażeniach, skład funkcji do tworzenia nowych funkcji, funkcji rozwinięte i niejawnej definicji funkcji w ramach częściowego zastosowania argumentów funkcji.|
|[Typy F#](fsharp-types.md)|Opisuje typy, które są używane w języku F # i jak typy języka F # mają nazwy i zostały opisane.|
|[Wnioskowanie o typie](type-inference.md)|Opisuje, w jaki sposób kompilator F # wnioskuje typy wartości, zmiennych, parametrów i zwracanych wartości.|
|[Automatyczna generalizacja](./generics/automatic-generalization.md)|Opisuje konstrukcje ogólne w języku F #.|
|[Dziedziczenie](inheritance.md)|Opisuje dziedziczenie, które jest używane do modelowania relacji "is-a" lub podpisywania w programowaniu zorientowanym obiektowo.|
|[Elementy członkowskie](./members/index.md)|Opisuje elementy członkowskie typów obiektów języka F #.|
|[Parametry i argumenty](Parameters-and-Arguments.md)|Opisuje obsługę języka w celu definiowania parametrów i przekazywania argumentów do funkcji, metod i właściwości. Zawiera informacje o sposobach przekazywania przez odwołanie.|
|[Przeciążanie operatora](operator-overloading.md)|Opisuje sposób przeciążenia operatorów arytmetycznych w typie klasy lub rekordu oraz na poziomie globalnym.|
|[Rzutowanie i konwersje](casting-and-conversions.md)|Opisuje obsługę konwersji typów w języku F #.|
|[Access Control](access-control.md)|Opisuje kontrolę dostępu w języku F #. Kontrola dostępu oznacza, że klienci mogą korzystać z niektórych elementów programu, takich jak typy, metody, funkcje i tak dalej.|
|[Dopasowanie wzorca](pattern-matching.md)|Opisuje wzorce, które są regułami dotyczącymi przekształcania danych wejściowych, które są używane w całym języku F # w celu wyodrębnienia danych z wzorca, rozkładania danych do części składowych lub wyodrębniania informacji z danych na różne sposoby.|
|[Wzorce aktywne](active-patterns.md)|Opisuje aktywne wzorce. Aktywne wzorce umożliwiają zdefiniowanie nazwanych partycji, które dzielą dane wejściowe. Przy użyciu aktywnych wzorców można rozkładać dane w dostosowany sposób dla każdej partycji.|
|[Asercje](assertions.md)|Opisuje `assert` wyrażenie, które jest funkcją debugowania, której można użyć do przetestowania wyrażenia. W przypadku niepowodzenia w trybie debugowania potwierdzenie generuje okno dialogowe błędu systemu.|
|[Obsługa wyjątków](./exception-handling/index.md)|Zawiera informacje dotyczące obsługi wyjątków w języku F #.|
|[Attributes](attributes.md)|Opisuje atrybuty, które umożliwiają stosowanie metadanych do konstrukcji programistycznej.|
|[Zarządzanie zasobami: `use` słowo kluczowe](resource-management-the-use-keyword.md)|Opisuje słowa kluczowe `use` i `using` , które mogą kontrolować inicjalizację i wydawanie zasobów|
|[przestrzeni](namespaces.md)|Opisuje obsługę przestrzeni nazw w języku F #. Przestrzeń nazw umożliwia organizowanie kodu w obszary powiązanej funkcjonalności przez umożliwienie dołączenia nazwy do grupy elementów programu.|
|[Moduły](modules.md)|Opisuje moduły. Moduł języka F # to grupa kodu F #, taka jak wartości, typy i wartości funkcji, w programie F #. Grupowanie kodu w modułach ułatwia zachowanie powiązanego kodu i pozwala uniknąć konfliktów nazw w programie.|
|[Deklaracje importu: `open` słowo kluczowe](import-declarations-the-open-keyword.md)|Opisuje sposób `open` działania programu. Deklaracja importu określa moduł lub przestrzeń nazw, których elementy można odwoływać bez używania w pełni kwalifikowanej nazwy.|
|[Podpisy](signature-files.md)|Opisuje sygnatury i pliki sygnatur. Plik podpisu zawiera informacje o podpisach publicznych zestawu elementów programu F #, takich jak typy, przestrzenie nazw i moduły. Może służyć do określania dostępności tych elementów programu.|
|[Dokumentacja XML](xml-documentation.md)|Opisuje obsługę generowania plików dokumentacji dla komentarzy do dokumentów XML, znanych także jako komentarze z potrójnym ukośnikiem. Można utworzyć dokumentację z komentarzy do kodu w języku F #, tak jak w innych językach .NET.|
|[Pełna składnia](verbose-syntax.md)|Opisuje składnię dla konstrukcji języka F #, gdy nie jest włączona składnia uproszczona. Składnia verbose jest wskazywana przez `#light "off"` dyrektywę w górnej części pliku kodu.|
|[Formatowanie zwykłego tekstu](plaintext-formatting.md)|Dowiedz się, jak używać sprintf — i innego formatowania zwykłego tekstu w aplikacjach i skryptach w języku F #.|

## <a name="f-types"></a>Typy F#

W poniższej tabeli przedstawiono dostępne tematy referencyjne opisujące Typy obsługiwane przez język F #.

|Tytuł|Opis|
|-----|-----------|
|[wartością](./values/index.md)|Opisuje wartości, które są niezmienne ilości, które mają określony typ; wartości mogą być liczbami całkowitymi lub zmiennoprzecinkowymi, znakami lub tekstem, listami, sekwencjami, tablicami, krotkami, związkami rozłącznych, rekordami, typami klas lub wartościami funkcji.|
|[Typy podstawowe](basic-types.md)|Zawiera opis podstawowych typów podstawowych, które są używane w języku F #. Zapewnia także odpowiednie typy .NET i minimalne i maksymalne wartości dla każdego typu.|
|[Typ jednostki](unit-type.md)|Opisuje `unit` Typ, który jest typem, który wskazuje brak określonej wartości; `unit` Typ ma tylko jedną wartość, która działa jako symbol zastępczy, gdy inna wartość nie istnieje lub nie jest wymagana.|
|[Ciągi](strings.md)|Opisuje ciągi w języku F #. `string`Typ reprezentuje niezmienny tekst, jako sekwencję znaków Unicode. `string`jest aliasem dla `System.String` .NET Framework.|
|[Krotki](tuples.md)|Opisuje krotki, które są grupowaniem nienazwanych, ale uporządkowane wartości prawdopodobnie różnych typów.|
|[Typy kolekcji F#](fsharp-collection-types.md)|Przegląd typów kolekcji funkcjonalnej F #, w tym typów tablic, list, sekwencji (SEQ), map i zestawów.|
|[Listy](lists.md)|Zawiera opis list. Lista w F # jest uporządkowaną, niemodyfikowalną serią wszystkich elementów tego samego typu.|
|[Opcje](options.md)|Opisuje typ opcji. Opcja w języku F # jest używana, gdy wartość może lub nie istnieje. Opcja ma typ podstawowy i może zawierać wartość tego typu lub może nie mieć wartości.|
|[Sekwencje](sequences.md)|Opisuje sekwencje. Sekwencja jest logiczną serią wszystkich elementów jednego typu. Poszczególne elementy sekwencji są obliczane tylko w razie potrzeby, więc reprezentacja może być mniejsza niż liczba elementów literału.|
|[Tablice](arrays.md)|Opisuje tablice. Tablice są stałym rozmiarem (liczonym od zera sekwencją) kolejnych elementów danych, tego samego typu.|
|[Rekordy](records.md)|Opisuje rekordy. Rekordy reprezentują proste Agregowanie wartości nazwanych, opcjonalnie z elementami członkowskimi.|
|[Sumy rozłączne](discriminated-unions.md)|Opisuje związki rozłączne, które zapewniają obsługę wartości, które mogą być jednym z różnych nazwanych przypadków, z których każdy ma inne wartości i typy.|
|[Wyliczenia](enumerations.md)|Opisuje typy wyliczeniowe, które mają zdefiniowany zestaw nazwanych wartości. Można ich użyć zamiast literałów, aby kod był bardziej czytelny i możliwy do utrzymania.|
|[Komórki odwołań](reference-cells.md)|Opisuje komórki odwołań, które są lokalizacjami przechowywania, które umożliwiają tworzenie zmiennych modyfikowalnych z semantyką odwołania.|
|[Skróty typów](type-abbreviations.md)|Opisuje skróty typów, które są alternatywnymi nazwami typów.|
|[Klasy](classes.md)|Opisuje klasy, które reprezentują obiekty, które mogą mieć właściwości, metody i zdarzenia.|
|[Struktury](structures.md)|Opisuje struktury, które są kompaktowymi typami obiektów, które mogą być bardziej wydajne niż Klasa dla typów, które mają niewielką ilość danych i proste zachowanie.|
|[Interfejsy](interfaces.md)|Opisuje interfejsy, które określają zestawy powiązanych elementów członkowskich, które są implementowane przez inne klasy.|
|[Klasy abstrakcyjne](abstract-classes.md)|Opisuje klasy abstrakcyjne, które są klasami, które opuszczają niektóre lub wszystkie składowe niezaimplementowane, dzięki czemu implementacje mogą być dostarczane przez klasy pochodne.|
|[Rozszerzenia typu](type-extensions.md)|Opisuje rozszerzenia typów, które umożliwiają dodawanie nowych elementów członkowskich do wcześniej zdefiniowanego typu obiektu.|
|[Typy elastyczne](flexible-types.md)|Opisuje elastyczne typy. Typ elastycznyj adnotacji jest wskaźnikiem, że parametr, zmienna lub wartość ma typ zgodny z określonym typem, w którym zgodność jest określana na podstawie położenia w hierarchii obiektów klasy lub interfejsów zorientowanych obiektowo.|
|[Delegaty](delegates.md)|Opisuje delegatów, które reprezentują wywołanie funkcji jako obiekt.|
|[Jednostki miary](units-of-measure.md)|Opisuje jednostki miary. Wartości zmiennoprzecinkowe w F # mogą mieć skojarzone jednostki miary, które zwykle są używane do wskazywania długości, objętości, masy itd.|
|[Dostawcy typów](../tutorials/type-providers/index.md)|Opis typu udostępnia i zawiera linki do przewodników dotyczących korzystania z wbudowanych dostawców typów w celu uzyskania dostępu do baz danych i usług sieci Web.|

## <a name="f-expressions"></a>Wyrażenia języka F #

W poniższej tabeli przedstawiono tematy opisujące wyrażenia języka F #.

|Tytuł|Opis|
|-----|-----------|
|[Wyrażenia warunkowe:`if...then...else`](conditional-expressions-if-then-else.md)|Opisuje `if...then...else` wyrażenie, które uruchamia różne gałęzie kodu, a także oblicza inną wartość w zależności od danego wyrażenia logicznego.|
|[Wyrażenia dopasowania](match-expressions.md)|Opisuje `match` wyrażenie, które zapewnia sterowanie rozgałęzieniem oparte na porównaniu z zestawem wzorców.|
|[Pętle: `for...to` wyrażenie](loops-for-to-expression.md)|Opisuje `for...to` wyrażenie, które jest używane do iteracji w pętli względem zakresu wartości zmiennej pętli.|
|[Pętle: `for...in` wyrażenie](loops-for-in-expression.md)|Opisuje `for...in` wyrażenie, konstrukcja pętli, która jest używana do iteracji na dopasowaniach wzorca w wyliczalnej kolekcji, takiej jak wyrażenie zakresu, sekwencja, lista, tablica lub inna konstrukcja, która obsługuje Wyliczenie.|
|[Pętle: `while...do` wyrażenie](loops-while-do-expression.md)|Opisuje `while...do` wyrażenie, które jest używane do wykonywania iteracji (zapętlenie), podczas gdy określony warunek testu ma wartość true.|
|[Wyrażenia obiektów](object-expressions.md)|Opisuje wyrażenia obiektów, które są wyrażeniami, które tworzą nowe wystąpienia dynamicznie utworzonego, anonimowego typu obiektu, który jest oparty na istniejącym typie podstawowym, interfejsie lub zestawie interfejsów.|
|[Wyrażenia z opóźnionym obliczaniem](lazy-expressions.md)|Opisuje wyrażenia z opóźnieniem, które są obliczeniami, które nie są natychmiast oceniane, ale zamiast tego są oceniane, gdy wynik jest rzeczywiście wymagany.|
|[Wyrażenia obliczeń](computation-expressions.md)|Opisuje wyrażenia obliczeń w języku F #, które zapewniają wygodną składnię do pisania obliczeń, które mogą być sekwencjonowane i łączone przy użyciu konstrukcji przepływu sterowania i powiązań. Mogą one służyć do zapewnienia wygodnej składni dla *monads*, funkcji programowania funkcjonalnego, która może służyć do zarządzania danymi, kontrolkami i efektami ubocznymi w programach funkcjonalnych. Jeden typ wyrażenia obliczeń, asynchroniczny przepływ pracy, zapewnia obsługę obliczeń asynchronicznych i równoległych. Aby uzyskać więcej informacji, zobacz [asynchroniczne przepływy pracy](asynchronous-workflows.md).|
|[Asynchroniczne przepływy pracy](asynchronous-workflows.md)|Opisuje asynchroniczne przepływy pracy, funkcję języka, która pozwala pisać kod asynchroniczny w sposób zbliżony do sposobu, w jaki można naturalnie pisać kod synchroniczny.|
|[Cytaty kodu](code-quotations.md)|Opisuje cytaty kodu, funkcję języka, która umożliwia programowe generowanie i Używanie wyrażeń kodu języka F #.|
|[Wyrażenia zapytania](query-expressions.md)|Opisuje wyrażenia zapytania, funkcję języka, która implementuje LINQ for F # i umożliwia pisanie zapytań względem źródła danych lub wyliczalnej kolekcji.|

## <a name="compiler-supported-constructs"></a>Konstrukcje obsługiwane przez kompilator

W poniższej tabeli przedstawiono tematy opisujące specjalne konstrukcje obsługiwane przez kompilator.

|Temat|Opis|
|-----|-----------|
|[Opcje kompilatora](compiler-options.md)|Opisuje opcje wiersza polecenia kompilatora języka F #.|
|[Dyrektywy kompilatora](compiler-directives.md)|Opisuje dyrektywy procesora i dyrektywy kompilatora.|
|[Identyfikatory wiersza źródłowego, pliku i ścieżki](source-line-file-path-identifiers.md)|Opisuje identyfikatory `__LINE__` `__SOURCE_DIRECTORY__` i `__SOURCE_FILE__` , które są wbudowanymi wartościami, które umożliwiają dostęp do numeru wiersza źródłowego, katalogu i nazwy pliku w kodzie.|
