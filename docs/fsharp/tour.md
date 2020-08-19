---
title: Przewodnik po środowisku F#
description: 'Zapoznaj się z najważniejszymi funkcjami języka programowania F # w tym przewodniku z przykładami kodu.'
ms.date: 08/14/2020
ms.openlocfilehash: b115317e1f47ef7e18333cae4145b99e11645579
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558598"
---
# <a name="tour-of-f"></a>Przewodnik po języku F\#

Najlepszym sposobem na poznanie języka F # jest odczytywanie i pisanie kodu języka F #. Ten artykuł działa jak przewodnik po niektórych najważniejszych funkcjach języka F # i zawiera fragmenty kodu, które można wykonać na komputerze. Aby dowiedzieć się więcej o konfigurowaniu środowiska programistycznego, zapoznaj się z [wprowadzenie](get-started/index.md).

Istnieją dwa podstawowe koncepcje w języku F #: funkcje i typy.  W tym samouczku zostaną wyróżnione funkcje języka, które dzielą się na te dwa pojęcia.

## <a name="executing-the-code-online"></a>Wykonywanie kodu online

Jeśli na maszynie nie zainstalowano języka F #, można wykonać wszystkie przykłady w przeglądarce przy użyciu [języka f # w zestawie webassembly](https://tryfsharp.fsbolero.io/). Fable to dialekt języka F #, który jest wykonywany bezpośrednio w przeglądarce. Aby wyświetlić przykłady, które są zgodne z REPL, zapoznaj się z przykładami, **> poznaj > Przewodnik po języku F #** na pasku menu po lewej stronie Fable REPL.

## <a name="functions-and-modules"></a>Funkcje i moduły

Najbardziej podstawowe fragmenty dowolnego programu F # to ***funkcje*** zorganizowane w ***moduły***.  [Funkcje](./language-reference/functions/index.md) wykonują prace nad danymi wejściowymi w celu tworzenia wyjść i są zorganizowane w [modułach](./language-reference/modules.md), które są głównym sposobem grupowania elementów w języku F #.  Są one definiowane przy użyciu [ `let` powiązania](./language-reference/functions/let-bindings.md), które nadaj funkcji nazwę i definiują jej argumenty.

[!code-fsharp[BasicFunctions](~/samples/snippets/fsharp/tour.fs#L101-L133)]

`let` powiązania to również sposób powiązania wartości z nazwą, podobnie jak zmienna w innych językach.  `let` powiązania są domyślnie ***niezmienne*** , co oznacza, że gdy wartość lub funkcja jest powiązana z nazwą, nie można jej zmienić w miejscu.  Jest to w przeciwieństwie do zmiennych w innych językach, które są ***modyfikowalne***, co oznacza, że ich wartości można zmienić w dowolnym momencie.  Jeśli jest wymagane powiązanie modyfikowalne, można użyć `let mutable ...` składni.

[!code-fsharp[Immutability](~/samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a>Liczby, wartości logiczne i ciągi

Jako język .NET program F # obsługuje te same podstawowe [typy pierwotne](language-reference/basic-types.md) , które istnieją w programie .NET.

Oto, jak różne typy liczbowe są reprezentowane w F #:

[!code-fsharp[Numbers](~/samples/snippets/fsharp/tour.fs#L49-L68)]

Oto, jakie wartości logiczne i wykonywanie podstawowej logiki warunkowej wygląda następująco:

[!code-fsharp[Bools](~/samples/snippets/fsharp/tour.fs#L142-L152)]

A Oto podstawowe manipulowanie [ciągami](./language-reference/strings.md) :

[!code-fsharp[Strings](~/samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a>Krotki

[Krotki](./language-reference/tuples.md) to Wielka okazja w języku F #.  Są to grupy nienazwanych, ale uporządkowane wartości, które mogą być traktowane jako same wartości.  Należy traktować je jako wartości agregowane z innych wartości.  Mają one wiele celów, takich jak wygodne zwracanie wielu wartości z funkcji lub grupowanie wartości dla niektórych wygodów ad hoc.

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L186-L203)]

Można również tworzyć `struct` krotki.  Są one również w pełni współdziałające z krotkami w języku C# 7/Visual Basic 15, które są również `struct` krotkami:

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L205-L218)]

Należy pamiętać, że ponieważ `struct` krotki są typami wartości, nie mogą być niejawnie konwertowane na kolekcje referencyjne lub odwrotnie.  Należy jawnie skonwertować między krotką i strukturą struktury.

## <a name="pipelines-and-composition"></a>Potoki i kompozycje

Operatory potokowe, takie jak `|>` są używane w szerokim czasie podczas przetwarzania danych w języku F #. Te operatory są funkcjami, które umożliwiają w elastyczny sposób ustanawianie "potoków" funkcji. W poniższym przykładzie pokazano, jak można wykorzystać te operatory w celu utworzenia prostego potoku funkcjonalnego:

[!code-fsharp[Pipelines](~/samples/snippets/fsharp/tour.fs#L227-L282)]

W poprzednim przykładzie użyto wielu funkcji języka F #, w tym funkcji przetwarzania list, funkcji pierwszej klasy i [częściowej aplikacji](./language-reference/functions/index.md#partial-application-of-arguments). Chociaż dokładne zrozumienie każdego z tych koncepcji może stać się nieco zaawansowane, powinno być jasne, jak łatwo funkcje mogą być używane do przetwarzania danych podczas kompilowania potoków.

## <a name="lists-arrays-and-sequences"></a>Listy, tablice i sekwencje

Listy, tablice i sekwencje to trzy podstawowe typy kolekcji w podstawowej bibliotece języka F #.

[Listy](./language-reference/lists.md) są uporządkowane, niezmienne kolekcje elementów tego samego typu.  Są one pojedynczo połączonymi listami, co oznacza, że są przeznaczone do wyliczenia, ale niewłaściwy wybór dostępu losowego i łączenia, jeśli są duże.  W przeciwieństwie do list w innych popularnych językach, które zazwyczaj nie używają pojedynczej listy połączonej do reprezentowania list.

[!code-fsharp[Lists](~/samples/snippets/fsharp/tour.fs#L309-L359)]

[Tablice](./language-reference/arrays.md) są stałymi *kolekcjami* elementów tego samego typu.  Obsługują one szybki dostęp do elementów i są szybsze niż listy języka F #, ponieważ są tylko ciągłymi blokami pamięci.

[!code-fsharp[Arrays](~/samples/snippets/fsharp/tour.fs#L368-L407)]

[Sekwencje](./language-reference/sequences.md) to logiczna seria elementów tego samego typu.  Jest to bardziej ogólny typ niż list i tablic, który może być "widokiem" w dowolnej logicznej serii elementów.  Są one również niezależne, ponieważ mogą być ***opóźnione***, co oznacza, że elementy można obliczyć tylko wtedy, gdy są one zbędne.

[!code-fsharp[Sequences](~/samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a>Funkcje rekursywne

Przetwarzanie kolekcji lub sekwencji elementów jest zwykle wykonywane z [rekursją](./language-reference/functions/index.md#recursive-functions) w języku F #.  Chociaż język F # obsługuje pętle i bezwzględne programowanie, rekursja jest preferowana, ponieważ jest łatwiejsza do zagwarantowania poprawności.

> [!NOTE]
> W poniższym przykładzie użyto dopasowania wzorca za pośrednictwem `match` wyrażenia.  Ta podstawowa konstrukcja została omówiona w dalszej części tego artykułu.

[!code-fsharp[RecursiveFunctions](~/samples/snippets/fsharp/tour.fs#L461-L500)]

Język F # ma także pełną obsługę optymalizacji wywołań końcowych, która jest sposobem na optymalizację wywołań cyklicznych, dzięki czemu są one równie szybkie jako konstrukcja pętli.

## <a name="record-and-discriminated-union-types"></a>Rekordy i typy Unii rozłącznych

Typy rekordów i Unii to dwa podstawowe typy danych używane w kodzie języka F # i ogólnie najlepszym sposobem reprezentowania danych w programie F #.  Chociaż sprawia to, że są one podobne do klas w innych językach, jedną z podstawowych różnic jest to, że mają semantykę równości strukturalnej.  Oznacza to, że są one "natywnie" porównywalne i równość są bezpośrednie — po prostu sprawdzaj, czy jeden z nich jest równy drugiemu.

[Rekordy](./language-reference/records.md) są agregacją nazwanych wartości z opcjonalnymi elementami członkowskimi (takimi jak metody).  W przypadku znajomości języka C# lub Java, powinny one być podobne do POCOs lub Pojo — tylko z równości strukturalne i mniej procedury.

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L507-L559)]

Można również reprezentować rekordy jako struktury. Jest to realizowane z `[<Struct>]` atrybutem:

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L561-L568)]

Związki rozłączne [(DUs)](./language-reference/discriminated-unions.md) to wartości, które mogą być liczbami nazwanymi formularzami lub przypadkami.  Dane przechowywane w typie mogą być jedną z kilku odrębnych wartości.

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L575-L631)]

Można również użyć DUs jako *Unii rozłącznych z pojedynczym przypadkiem*, aby ułatwić modelowanie domen dla typów pierwotnych.  Często zdarza się, że ciągi i inne typy pierwotne są używane do reprezentowania elementu i w ten sposób mają określone znaczenie.  Jednak użycie tylko pierwotnej reprezentacji danych może spowodować błędne przypisanie nieprawidłowej wartości.  Reprezentuje każdy typ informacji jako odrębna Unia z pojedynczym przypadkiem, że w tym scenariuszu można wymusić poprawność.

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L633-L654)]

Jak pokazano na powyższym przykładzie, aby uzyskać podstawową wartość w Unii rozłącznej, należy jawnie odwrócić ją.

Ponadto DUs obsługuje również definicje cykliczne, co pozwala na łatwe przedstawianie drzew i danych rekursywnie.  Na przykład poniżej przedstawiono sposób reprezentowania binarnego drzewa wyszukiwania z `exists` `insert` funkcjami i.

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L656-L683)]

Ponieważ DUs pozwala reprezentować strukturę cykliczną drzewa w typie danych, działanie na tej strukturze cyklicznej jest proste i gwarantuje poprawność.  Jest ona również obsługiwana w dopasowaniu wzorców, jak pokazano poniżej.

Ponadto można reprezentować DUs jako `struct` s z `[<Struct>]` atrybutem:

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L685-L696)]

Istnieją jednak dwie kluczowe kwestie, które należy wziąć pod uwagę podczas wykonywania następujących czynności:

1. Struktura DU nie może być zdefiniowana cyklicznie.
2. Struktura DU musi mieć unikatowe nazwy dla każdego ze swoich przypadków.

Niewykonanie powyższych czynności spowoduje wystąpienie błędu kompilacji.

## <a name="pattern-matching"></a>Dopasowanie wzorca

[Dopasowanie do wzorca](./language-reference/pattern-matching.md) to funkcja języka f #, która umożliwia poprawność działania w przypadku typów języka f #.  W powyższych przykładach prawdopodobnie zauważono nieprawidłową `match x with ...` składnię.  Ta konstrukcja umożliwia kompilatorowi, który może zrozumieć "kształt" typów danych, aby wymusić obsługę wszystkich możliwych przypadków przy użyciu typu danych, który jest znany jako wyczerpujące dopasowanie do wzorca.  Jest to niezwykle zaawansowane w celu poprawienia poprawności i może być Cleverly używany do "dźwigów", co zazwyczaj jest problemem w czasie wykonywania.

[!code-fsharp[PatternMatching](~/samples/snippets/fsharp/tour.fs#L705-L742)]

Coś, co może być zauważone, jest użycie `_` wzorca.  Jest to tzw. [symbol wieloznaczny](./language-reference/pattern-matching.md#wildcard-pattern), który jest sposobem wymawiania "nie wiemy, co coś jest".  Chociaż jest to wygodne, można przypadkowo ominąć dokładne dopasowanie do wzorca i nie korzystać z wymuszania w czasie kompilacji, jeśli nie jest to ważne w przypadku korzystania z programu `_` .  Najlepiej jest używać, gdy nie masz opieki nad niektórymi fragmentami typu rozłożonego w przypadku dopasowania do wzorca lub klauzuli końcowej, gdy wyliczane są wszystkie znaczące przypadki w wyrażeniu dopasowania do wzorca.

W poniższym przykładzie `_` przypadek jest używany w przypadku niepowodzenia operacji analizy.

[!code-fsharp[PatternMatching](~/samples/snippets/fsharp/tour.fs#L744-L762)]

[Aktywne wzorce](./language-reference/active-patterns.md) to kolejna Zaawansowana konstrukcja do użycia z dopasowaniem do wzorca.  Umożliwiają one Partycjonowanie danych wejściowych w formularzach niestandardowych, a następnie ich tworzenie w lokacji wywołania dopasowania wzorca.  Mogą być również sparametryzowane, umożliwiając zdefiniowanie partycji jako funkcji.  Powiększanie poprzedniego przykładu w celu obsługi aktywnych wzorców wygląda następująco:

[!code-fsharp[ActivePatterns](~/samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a>Typy opcjonalne

Pojedynczym szczególnym przypadkiem typów Unii rozłącznych jest typ opcji, co jest przydatne, gdy jest to część biblioteki podstawowej F #.

[Typ opcji](./language-reference/options.md) jest typem, który reprezentuje jeden z dwóch przypadków: wartość lub nic wcale.  Jest on używany w każdym scenariuszu, w którym wartość może lub nie może wynikać z określonej operacji.  Oznacza to, że jest to konieczne dla obu tych przypadków, co sprawia, że nie jest to problem w czasie wykonywania.  Są one często używane w interfejsach API `null` , gdzie są używane do reprezentowania wartości "Nothing", co eliminuje konieczność przejmowania się `NullReferenceException` w wielu sytuacjach.

[!code-fsharp[Options](~/samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a>Jednostki miary

Jedną z unikatowych funkcji systemu typu F # jest możliwość zapewnienia kontekstu dla literałów numerycznych za pomocą jednostek miary.

[Jednostki miary](./language-reference/units-of-measure.md) umożliwiają kojarzenie typu liczbowego z jednostką, taką jak liczniki, i mają funkcje, które wykonują prace w jednostkach, a nie literały numeryczne.  Dzięki temu kompilator może sprawdzić, czy typy literałów liczbowych, które przechodzą, mają sens w określonym kontekście, eliminując w ten sposób błędy środowiska uruchomieniowego związane z tym rodzajem pracy.

[!code-fsharp[UnitsOfMeasure](~/samples/snippets/fsharp/tour.fs#L817-L842)]

Biblioteka podstawowa F # definiuje wiele typów jednostek SI i konwersje jednostek.  Aby dowiedzieć się więcej, zapoznaj się z [przestrzenią nazw FSharp. Data. UnitSystems. si. UnitSymbols](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-data-unitsystems-si-unitsymbols.html).

## <a name="classes-and-interfaces"></a>Klasy i interfejsy

Język F # ma także pełną obsługę klas .NET, [interfejsów](./language-reference/interfaces.md), [klas abstrakcyjnych](./language-reference/abstract-classes.md), [dziedziczenia](./language-reference/inheritance.md)i tak dalej.

[Klasy](./language-reference/classes.md) są typami reprezentującymi obiekty .NET, które mogą mieć właściwości, metody i zdarzenia jako [elementy członkowskie](./language-reference/members/index.md).

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L845-L880)]

Definiowanie klas ogólnych jest również bardzo proste.

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L883-L908)]

Aby zaimplementować interfejs, można użyć `interface ... with` składni lub [wyrażenia obiektu](./language-reference/object-expressions.md).

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a>Jakiego typu używać

Obecność klas, rekordów, Unii rozłącznych i krotek prowadzi do ważnych pytań: których należy użyć?  Podobnie jak większość wszystkiego w życiu, odpowiedź zależy od Twoich okoliczności.

Krotki są doskonałe do zwracania wielu wartości z funkcji i używania zagregowanych wartości ad-hoc jako samej wartości.

Rekordy są "krokami" z spójnych kolekcji o nazwanych etykietach i pomocy technicznej dla opcjonalnych elementów członkowskich.  Są one doskonałe do proceduryej reprezentacji danych przesyłanych przez program.  Ze względu na to, że mają one równość strukturalnych, są łatwe do użycia z porównaniem.

Związki rozłączne mają wiele celów, ale korzyścią podstawową jest możliwość ich użycia w połączeniu ze wzorcem dopasowania do konta dla wszystkich możliwych "kształtów", które mogą mieć dane.  

Klasy są doskonałe dla dużej liczby powodów, takich jak w przypadku konieczności reprezentowania informacji, a także powiązania tych informacji z funkcjonalnością.  Jako zasada elementu kciuka, gdy masz funkcje, które są koncepcyjnie powiązane z danymi, korzystanie z klas i zasad programowania zorientowanego obiektowo jest wielką zaletą.  Klasy są również preferowanym typem danych podczas współdziałania z C# i Visual Basic, ponieważ te języki używają klas dla niemal wszystkiego.

## <a name="next-steps"></a>Następne kroki

Teraz, gdy zobaczysz niektóre z podstawowych funkcji języka, warto przystąpić do pisania pierwszych programów w języku F #.  Zapoznaj się z [wprowadzenie](get-started/index.md) , aby dowiedzieć się, jak skonfigurować środowisko deweloperskie i napisać kod.

Kolejne kroki dotyczące uczenia się nie mogą być takie same, ale zalecamy [wprowadzenie do programowania funkcjonalnego w języku F #](./introduction-to-functional-programming/index.md) w celu uzyskania komfortu podstawowych koncepcji programowania funkcjonalnego.  Są one niezbędne do tworzenia niezawodnych programów w języku F #.

Zapoznaj się również z dokumentacją [języka f #](./language-reference/index.md) , aby zobaczyć kompleksową kolekcję zawartości koncepcyjnej w języku f #.
