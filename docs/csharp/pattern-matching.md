---
title: Dopasowanie wzorca — Przewodnik C#
description: 'Informacje na temat wyrażeń dopasowania wzorców w języku C #'
ms.date: 04/10/2019
ms.technology: csharp-fundamentals
ms.assetid: 1e575c32-2e2b-4425-9dca-7d118f3ed15b
ms.openlocfilehash: 2dd1401e3ef22a02f327e44ff884182ee3e22278
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414997"
---
# <a name="pattern-matching"></a>Dopasowanie wzorca

Wzorzec testuje, że wartość ma określony *kształt*i może *wyodrębnić* informacje z wartości, gdy ma pasujący kształt. Dopasowanie wzorca zawiera bardziej zwięzłą składnię dla algorytmów, które już dzisiaj używały. Można już tworzyć algorytmy dopasowywania wzorców przy użyciu istniejącej składni. Należy napisać `if` lub `switch` instrukcji, które są wartościami testowymi. Następnie, gdy te instrukcje są zgodne, wyodrębnisz i użyjesz informacji z tej wartości. Nowe elementy składni są rozszerzeniami do instrukcji, które są już znane: `is` i `switch` . Te nowe rozszerzenia łączą testowanie wartości i wyodrębniają te informacje.

W tym artykule poznasz nową składnię, aby pokazać, jak to umożliwia czytelny, zwięzły kod. Dopasowywanie wzorców umożliwia idiomy, w których dane i kod są oddzielane, w przeciwieństwie do projektów zorientowanych obiektowo, w przypadku których dane i metody manipulowania nimi są ściśle sprzężone.

Aby zilustrować te nowe idiomy, przyjrzyjmy się strukturom, które reprezentują kształty geometryczne przy użyciu instrukcji dopasowania do wzorca. Prawdopodobnie wiesz już, jak tworzyć hierarchie klas i tworzyć [metody wirtualne i zastąpione metody,](methods.md#inherited) aby dostosować zachowanie obiektów na podstawie typu środowiska uruchomieniowego obiektu.

Te techniki nie są możliwe w przypadku danych, które nie są strukturalne w hierarchii klas. Gdy dane i metody są oddzielone, potrzebne są inne narzędzia. Nowe konstrukcje *dopasowania wzorców* umożliwiają oczyszczarkę składnię do badania danych i manipulowania przepływem sterowania na podstawie dowolnego warunku tych danych. Należy już napisać `if` instrukcje i `switch` przetestować wartość zmiennej. Należy napisać `is` instrukcje, które testują typ zmiennej. *Dopasowanie wzorca* dodaje nowe możliwości do tych instrukcji.

W tym artykule utworzysz metodę, która oblicza obszar różnych kształtów geometrycznych. Jednak należy to zrobić bez konieczności wykonywania technik zorientowanych obiektowo i tworzenia hierarchii klas dla różnych kształtów.
Zamiast tego użyjesz *dopasowania do wzorca* .
Korzystając z tego przykładu, należy pokontraście ten kod, tak aby był on strukturalny jako hierarchia obiektów. Gdy dane, które należy wykonać podczas wykonywania zapytania i manipulowania, nie są hierarchią klas, dopasowanie wzorców umożliwia tworzenie eleganckich projektów.

Zamiast rozpoczynać się od definicji kształtu abstrakcyjnego i dodawać różne klasy kształtów, zacznijmy zamiast od prostych definicji zawierających tylko dane dla każdego z kształtów geometrycznych:

[!code-csharp[ShapeDefinitions](../../samples/snippets/csharp/PatternMatching/Shapes.cs#01_ShapeDefinitions "Shape definitions")]

Z tych struktur Napiszmy metodę, która oblicza obszar pewnego kształtu.

## <a name="the-is-type-pattern-expression"></a>`is`Wyrażenie wzorca typu

Przed C# 7,0 należy przetestować każdy typ w szeregu `if` i `is` instrukcjach:

[!code-csharp[ClassicIsExpression](../../samples/snippets/csharp/PatternMatching/GeometricUtilities.cs#02_ClassicIsExpression "Classic type pattern using is")]

Ten kod powyżej jest wyrażeniem klasycznym *wzorca typu*: testujesz zmienną, aby określić jej typ i wykonując inną akcję na podstawie tego typu.

Ten kod będzie prostszy przy użyciu rozszerzeń do `is` wyrażenia, aby przypisać zmienną, jeśli test zakończy się pomyślnie:

[!code-csharp[IsPatternExpression](../../samples/snippets/csharp/PatternMatching/GeometricUtilities.cs#03_IsPatternExpression "is pattern expression")]

W tej zaktualizowanej wersji `is` wyrażenie testuje zmienną i przypisze ją do nowej zmiennej odpowiedniego typu. Należy również zauważyć, że ta wersja zawiera `Rectangle` Typ, który jest `struct` . Nowe `is` wyrażenie działa z typami wartości, a także typami referencyjnymi.

Reguły języka dla wyrażeń dopasowania wzorców pomagają uniknąć nieprawidłowych wyników wyrażenia dopasowania. W powyższym przykładzie zmienne `s` , `c` , i `r` są tylko w zakresie i ostatecznie przypisane, gdy odpowiednie wyrażenia dopasowania wzorców mają `true` wyniki. Jeśli spróbujesz użyć dowolnej zmiennej w innej lokalizacji, kod generuje błędy kompilatora.

Sprawdźmy szczegóły obu tych reguł, rozpoczynając od zakresu. Zmienna `c` znajduje się w zakresie tylko w `else` gałęzi pierwszej `if` instrukcji. Zmienna `s` jest w zakresie w metodzie `ComputeAreaModernIs` . Jest tak dlatego, że każda gałąź `if` instrukcji tworzy oddzielny zakres dla zmiennych. Jednak `if` sama instrukcja nie jest. Oznacza to, że zmienne zadeklarowane w `if` instrukcji znajdują się w tym samym zakresie co `if` instrukcja (metoda w tym przypadku). To zachowanie nie jest specyficzne dla dopasowania do wzorca, ale jest zachowaniem zdefiniowanym dla zakresów zmiennych i `if` `else` instrukcji.

Zmienne `c` i `s` są przypisywane, gdy odpowiednie `if` instrukcje są prawdziwe ze względu na to, że jest on w nieskończony sposób przypisany do rzeczywistego mechanizmu.

> [!TIP]
> Przykłady w tym temacie wykorzystują zalecaną konstrukcję, w której wyrażenie dopasowania do wzorca `is` ostatecznie przypisuje zmienną Match w `true` gałęzi `if` instrukcji.
> Można wycofać logikę, wypowiadając `if (!(shape is Square s))` , a zmienna `s` może być ostatecznie przypisana tylko w `false` gałęzi. Chociaż jest to prawidłowy język C#, nie jest to zalecane, ponieważ jest bardziej trudne do przestrzegania logiki.

Te reguły oznaczają, że nie jest możliwe przypadkowe uzyskanie dostępu do wyniku wyrażenia dopasowania do wzorca, gdy ten wzorzec nie został spełniony.

## <a name="using-pattern-matching-switch-statements"></a>Używanie instrukcji dopasowania wzorca `switch`

Gdy przejdzie czas, może być konieczne obsługę innych typów kształtów. W miarę zwiększania się liczby testowanych warunków można się dowiedzieć, że użycie `is` wyrażeń dopasowania wzorców może stać się nieskomplikowany. Oprócz wymagania `if` instrukcji dla każdego typu, który chcesz sprawdzić, `is` wyrażenia są ograniczone do testowania, jeśli dane wejściowe są zgodne z pojedynczym typem. W tym przypadku zobaczysz, że `switch` wyrażenia dopasowania wzorców staną się lepszym wyborem.

Tradycyjna `switch` instrukcja była wyrażeniem wzorca: obsługuje stałe wzorce.
Można porównać zmienną z dowolną stałą używaną w `case` instrukcji:

[!code-csharp[ClassicSwitch](../../samples/snippets/csharp/PatternMatching/GeometricUtilities.cs#04_ClassicSwitch "Classic switch statement")]

Jedyny wzorzec obsługiwany przez `switch` instrukcję był wzorcem stałym. Jest ona bardziej ograniczona do typów liczbowych i `string` typu.
Te ograniczenia zostały usunięte i można teraz napisać `switch` instrukcję przy użyciu wzorca typu:

[!code-csharp[Switch Type Pattern](../../samples/snippets/csharp/PatternMatching/GeometricUtilities.cs#05_SwitchTypePattern "Compute with `switch` expression")]

W instrukcji dopasowania wzorca `switch` używana jest znana składnia dla deweloperów, którzy używali tradycyjnej `switch` instrukcji języka C. Każdy `case` z nich jest obliczany, a kod pod warunkiem, który jest zgodny z zmienną wejściową jest wykonywany. Wykonanie kodu nie może "przechodzenie" z jednego wyrażenia case do następnego; Składnia `case` instrukcji wymaga, aby każde `case` zakończenie z `break` , `return` lub `goto` .

> [!NOTE]
> `goto`Instrukcje do przeskoczenia do innej etykiety są prawidłowe tylko dla wzorca stałej (instrukcji switch klasycznego).

Istnieją ważne nowe zasady dotyczące zasad `switch` . Ograniczenia dotyczące typu zmiennej w `switch` wyrażeniu zostały usunięte.
Można użyć dowolnego typu, takiego jak `object` w tym przykładzie. Wyrażenia case nie są już ograniczone do wartości stałych. Usunięcie tego ograniczenia oznacza, że zmiany kolejności `switch` w sekcjach mogą zmienić zachowanie programu.

Gdy są ograniczone do wartości stałych, nie więcej niż jedna `case` etykieta może pasować do wartości `switch` wyrażenia. Połącz ten element z regułą, która `switch` nie może przechodzić do kolejnej sekcji, a następnie `switch` Przemieść sekcje w dowolnej kolejności bez wpływu na zachowanie.
Teraz, w przypadku bardziej uogólnionych `switch` wyrażeń, kolejność każdej sekcji jest ważna. `switch`Wyrażenia są oceniane w kolejności tekstowej. Wykonanie przenosi do pierwszej `switch` etykiety, która pasuje do `switch` wyrażenia.  
`default`Przypadek zostanie wykonany tylko wtedy, gdy żadne inne etykiety case nie pasują do siebie. `default`Wielkość liter jest szacowana jako Ostatnia, niezależnie od ich kolejności tekstu. Jeśli nie ma żadnego `default` przypadku, a żadna z innych instrukcji nie jest `case` zgodna, wykonanie kontynuuje się w instrukcji następującej po `switch` instrukcji. Żaden z `case` kodów etykiet nie jest wykonywany.

## <a name="when-clauses-in-case-expressions"></a>`when` klauzule w `case` wyrażeniach

Można tworzyć specjalne przypadki dla tych kształtów, które mają 0 obszarów, używając `when` klauzuli na `case` etykiecie. Kwadrat o długości bocznej 0 lub Okręg o promieniu 0 ma powierzchnię 0. Należy określić warunek przy użyciu `when` klauzuli na `case` etykiecie:  

[!code-csharp[ComputeDegenerateShapes](../../samples/snippets/csharp/PatternMatching/GeometricUtilities.cs#07_ComputeDegenerateShapes "Compute shapes with 0 area")]

Ta zmiana pokazuje kilka ważnych punktów dotyczących nowej składni. Najpierw `case` można zastosować wiele etykiet do jednej `switch` sekcji. Blok instrukcji jest wykonywany, gdy dowolna z tych etykiet jest `true` . W tym przypadku, jeśli `switch` wyrażenie jest okrąg lub kwadrat z 0 obszaru, metoda zwraca stałą 0.

W tym przykładzie wprowadzono dwie różne zmienne w dwóch `case` etykietach dla pierwszego `switch` bloku. Zauważ, że instrukcje w tym `switch` bloku nie używają zmiennych `c` (dla okręgu) lub `s` (dla kwadratu).
Żadna z tych zmiennych nie jest ostatecznie przypisana w tym `switch` bloku.
Jeśli jeden z tych przypadków jest zgodny, wyraźnie jedna ze zmiennych została przypisana.
Nie jest jednak możliwe informowanie, *które* zostało przypisane w czasie kompilacji, ponieważ każdy przypadek może być zgodny w czasie wykonywania. Z tego powodu najczęściej w przypadku używania wielu `case` etykiet dla tego samego bloku nie zostanie wprowadzona nowa zmienna w `case` instrukcji lub w klauzuli zostanie użyta tylko zmienna `when` .

Po dodaniu tych kształtów w obszarze 0 Dodajmy kilka typów kształtów: prostokąt i Trójkąt:

[!code-csharp[AddRectangleAndTriangle](../../samples/snippets/csharp/PatternMatching/GeometricUtilities.cs#09_AddRectangleAndTriangle "Add rectangle and triangle")]

 Ten zestaw zmian dodaje `case` etykiety dla przypadku wygenerowania i etykiety i bloki dla każdego nowego kształtu.

Na koniec możesz dodać przypadek, `null` Aby upewnić się, że argument nie jest `null` :

[!code-csharp[NullCase](../../samples/snippets/csharp/PatternMatching/GeometricUtilities.cs#10_NullCase "Add null case")]

Specjalne zachowanie `null` wzorca jest interesujące, ponieważ stała `null` w wzorcu nie ma typu, ale można ją przekonwertować na dowolny typ referencyjny lub typ wartości null. Zamiast konwersji `null` do dowolnego typu, język definiuje, że `null` wartość nie będzie zgodna ze wzorcem typu, niezależnie od typu czasu kompilacji zmiennej. To zachowanie powoduje, że nowy `switch` wzorzec typu opartego na typie jest spójny z `is` instrukcją: `is` instrukcje zawsze zwracają, `false` gdy sprawdzana wartość jest `null` . Jest również prostsze: po sprawdzeniu typu nie jest wymagane dodatkowe sprawdzenie wartości null. Można sprawdzić, czy nie ma żadnych testów null w żadnym z bloków Case powyższych przykładów: nie jest to konieczne, ponieważ dopasowanie wzorca typu gwarantuje wartość różną od null.

## <a name="var-declarations-in-case-expressions"></a>`var` deklaracje w `case` wyrażeniach

Wprowadzenie `var` jako jednego z wyrażeń dopasowania wprowadza nowe reguły do dopasowania do wzorca.

Pierwsza reguła polega na tym, że `var` Deklaracja jest zgodna z regułami wnioskowania o typie normalnym: typ jest wywnioskowany jako typ statyczny wyrażenia Switch. W tej regule typ zawsze jest zgodny.

Druga reguła polega na tym, że `var` Deklaracja nie ma sprawdzenia wartości null, która zawiera inne wyrażenia wzorca typu. Oznacza to, że zmienna może mieć wartość null, a w takim przypadku konieczne jest sprawdzenie wartości null.

Te dwie reguły oznaczają, że w wielu przypadkach `var` Deklaracja w `case` wyrażeniu dopasowuje te same warunki co `default` wyrażenie.
Ponieważ każdy przypadek inny niż domyślny jest preferowany w `default` przypadku, `default` przypadek nigdy nie zostanie wykonany.

> [!NOTE]
> Kompilator nie emituje ostrzeżenia w przypadkach, gdy `default` sprawa została zapisywana, ale nigdy nie zostanie wykonana. Jest to zgodne z obecnym `switch` zachowaniem instrukcji w przypadku, gdy wszystkie możliwe przypadki zostały wymienione.

Trzecia reguła wprowadza użycie w przypadku, gdy `var` może być przydatne w przypadku. Załóżmy, że wykonujesz dopasowanie do wzorca, gdzie dane wejściowe są ciągiem i wyszukujesz znane wartości poleceń. Można napisać coś takiego jak:

[!code-csharp[VarCaseExpression](../../samples/snippets/csharp/PatternMatching/Program.cs#VarCaseExpression "use a var case expression to filter white space")]

`var`Wielkość liter jest zgodna z `null` ciągiem pustym lub dowolnym ciągiem zawierającym tylko biały znak. Zwróć uwagę, że poprzedni kod używa `?.` operatora, aby upewnić się, że nie zgłosi przypadkowo <xref:System.NullReferenceException> . `default`Przypadek obsługuje wszelkie inne wartości ciągów, które nie są zrozumiałe dla tego analizatora poleceń.

Jest to jeden przykład, w którym warto rozważyć `var` wyrażenie CASE, które różni się od `default` wyrażenia.

## <a name="conclusions"></a>Wnioski

*Konstrukcje dopasowania wzorców* umożliwiają łatwe zarządzanie przepływem sterowania między różnymi zmiennymi i typami, które nie są powiązane z hierarchią dziedziczenia. Możesz również sterować logiką, aby używać dowolnego warunku, który można testować na zmiennej. Umożliwia ona wzorce i idiomy, które będą potrzebne częściej, podczas tworzenia bardziej rozproszonych aplikacji, w przypadku których dane i metody manipulowania nimi są osobne. Zauważ, że struktury kształtu używane w tym przykładzie nie zawierają żadnych metod, tylko właściwości tylko do odczytu.
Dopasowanie wzorca współdziała z dowolnym typem danych. Można pisać wyrażenia, które badają obiekt, i podejmować decyzje dotyczące przepływu sterowania na podstawie tych warunków.

Porównaj kod z tego przykładu z projektem, który byłby następujący po utworzeniu hierarchii klas dla abstrakcyjnych `Shape` i specyficznych kształtów pochodnych z własnym implementacją metody wirtualnej w celu obliczenia obszaru. Często należy zauważyć, że wyrażenia dopasowania wzorców mogą być bardzo użytecznym narzędziem podczas pracy z danymi i chcą oddzielić problemy związane z przechowywaniem danych od problemów z zachowaniem.

## <a name="see-also"></a>Zobacz też

- [Samouczek: Używanie funkcji dopasowania wzorców do zwiększania typów danych](tutorials/pattern-matching.md)
