---
title: Co nowego w języku C# 9,0 — przewodnik w języku C#
description: Zapoznaj się z omówieniem nowych funkcji dostępnych w języku C# 9,0.
ms.date: 09/04/2020
ms.openlocfilehash: c165ca764d93b74aac21028ed3e55e80f2a23ee0
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654910"
---
# <a name="whats-new-in-c-90"></a>Co nowego w języku C# 9.0

W języku c# 9,0 dodano następujące funkcje i ulepszenia języka C#:

- [Rekordy](#record-types)
- [Metody ustawiające tylko do inicjowania](#init-only-setters)
- [Instrukcje najwyższego poziomu](#top-level-statements)
- [Ulepszenia dopasowania wzorców](#pattern-matching-enhancements)
- Liczby całkowite o wielkości natywnej
- Wskaźniki funkcji
- Pomiń emitowanie flagi localsinit
- Nowe wyrażenia z typem docelowym
- statyczne funkcje anonimowe
- Wyrażenia warunkowe z typem docelowym
- Kowariantne typy zwracane
- `GetEnumerator`Obsługa rozszerzeń dla `foreach` pętli
- Parametry odrzucania wyrażenia lambda
- Atrybuty funkcji lokalnych
- Inicjatory modułów
- Nowe funkcje dla metod częściowych

Język C# 9,0 jest obsługiwany w **programie .NET 5**. Aby uzyskać więcej informacji, zobacz [wersja języka C#](../language-reference/configure-language-version.md).

## <a name="record-types"></a>Typy rekordów

W języku C# 9,0 wprowadzono ***typy rekordów***, które są typem referencyjnym, które udostępniają metody z syntezą, aby zapewnić semantykę wartości dla równości. Rekordy są domyślnie niezmienne.

Typy rekordów ułatwiają tworzenie niemodyfikowalnych typów referencyjnych w programie .NET. Historycznie typy .NET są w znacznym stopniu klasyfikowane jako typy referencyjne (w tym klasy i typy anonimowe) i typy wartości (w tym struktury i krotki). Chociaż zaleca się niezmienne typy wartości, modyfikowalne typy wartości nie często wprowadzają błędy. Zmienne typu wartości przechowują wartości, więc zmiany są wprowadzane do kopii oryginalnych danych, gdy typy wartości są przekazywane do metod.

Istnieje wiele zalet, aby również niezmienne typy odwołań. Te zalety są bardziej wymawiane w współbieżnych programach z udostępnionymi danymi. Niestety, w języku C# wymuszono napisanie całkiem dowolnego dodatkowego kodu w celu utworzenia niemodyfikowalnych typów referencyjnych. Rekordy zapewniają deklarację typu dla niezmiennego typu referencyjnego, który używa semantyki wartości dla równości. W metodach syntezy dla kodów równości i wyznaczania wartości skrótu należy wziąć pod uwagę dwa rekordy równe, jeśli ich właściwości są równe. Należy wziąć pod uwagę tę definicję:

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="RecordDefinition":::

Definicja rekordu tworzy `Person` Typ, który zawiera dwie właściwości ReadOnly: `FirstName` i `LastName` . `Person`Typ jest typem referencyjnym. Jeśli szukasz języka IL, jest on klasą. Jest to niezmienne w przypadku, gdy żadna z właściwości nie może być modyfikowana po utworzeniu. W przypadku zdefiniowania typu rekordu, kompilator umożliwia wyszukanie kilku innych metod:

- Metody porównania równości opartej na wartościach
- Przesłoń dla <xref:System.Object.GetHashCode>
- Kopiowanie i klonowanie elementów członkowskich
- `PrintMembers` i <xref:System.Object.ToString>

Rekordy obsługują dziedziczenie. Można zadeklarować nowy rekord pochodzący z `Person` następujących metod:

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="InheritedRecord":::

Możesz również zapieczętować rekordy, aby zapobiec dalszemu występowaniu:

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="SealedRecord":::

Kompilator syntezuje różne wersje powyższych metod. Sygnatury metod są zależne od tego, czy typ rekordu jest zapieczętowany i czy bezpośrednia klasa bazowa to obiekt. Rekordy powinny mieć następujące możliwości:

- Równość jest oparta na wartości i zawiera sprawdzenie, czy typy pasują do siebie. Na przykład wartość `Student` nie może być równa `Person` , nawet jeśli dwa rekordy mają tę samą nazwę.
- Rekordy mają wygenerowaną spójną reprezentację ciągu.
- Rekordy obsługują konstrukcję kopiowania. Poprawna konstrukcja kopii musi zawierać hierarchie dziedziczenia i właściwości dodawane przez deweloperów.
- Rekordy można kopiować z modyfikacją. Te operacje kopiowania i modyfikowania obsługują mutację nieniszczącą.

Oprócz znanych `Equals` przeciążeń, i kompilator umożliwia wypróbowanie `operator ==` `operator !=` nowej `EqualityContract` właściwości. Właściwość zwraca `Type` obiekt, który jest zgodny z typem rekordu. Jeśli typem podstawowym jest `object` , właściwość jest `virtual` . Jeśli typ podstawowy jest innym typem rekordu, właściwość jest `override` . Jeśli typem rekordu jest `sealed` , właściwość jest `sealed` . W syntezie są `GetHashCode` stosowane `GetHashCode` wszystkie właściwości i pola zadeklarowane w typie podstawowym oraz typ rekordu. Te metody, które zostały opisane w tej metodzie, wymuszają równość opartych na wartościach w hierarchii dziedziczenia Oznacza to, że `Student` nigdy nie będzie traktowane jako równe a `Person` o tej samej nazwie. Typy dwóch rekordów muszą być zgodne oraz wszystkie właściwości, które są współużytkowane przez typy rekordów równe.

Rekordy mają również konstruktory z syntezą i metodę "Clone" służącą do tworzenia kopii. Konstruktor z syntezą ma jeden argument typu rekordu. Tworzy nowy rekord z tymi samymi wartościami dla wszystkich właściwości rekordu. Ten konstruktor jest prywatny, jeśli rekord jest zapieczętowany, w przeciwnym razie jest chroniony. Synteza "klonowanie" obsługuje konstrukcję kopiowania dla hierarchii rekordów. Termin "klon" jest w cudzysłowie, ponieważ rzeczywista nazwa jest generowana przez kompilator. Nie można utworzyć metody o nazwie `Clone` w typie rekordu. Synteza "klon" zwraca typ rekordu, który jest kopiowany przy użyciu wysyłki wirtualnej. Kompilator dodaje różne Modyfikatory dla metody "Clone" w zależności od modyfikatorów dostępu w `record` :

- Jeśli typem rekordu jest `abstract` , Metoda "klonowanie" jest również `abstract` . Jeśli typ podstawowy nie jest `object` , metoda jest również `override` .
- Dla typów rekordów, które nie są, `abstract` gdy typem podstawowym jest `object` :
  - Jeśli rekord ma wartość `sealed` , żadne dodatkowe Modyfikatory nie są dodawane do metody "klonowania" (oznacza to, że nie jest `virtual` ).
  - Jeśli rekord nie jest `sealed` , Metoda "Clone" ma wartość `virtual` .
- Dla typów rekordów, które nie są, `abstract` gdy typ podstawowy nie jest `object` :
  - Jeśli rekordem jest `sealed` , Metoda "klonowanie" jest również `sealed` .
  - Jeśli rekord nie jest `sealed` , Metoda "Clone" ma wartość `override` .

Wynik wszystkich tych reguł jest implementowany spójnie dla każdej hierarchii typów rekordów. Dwa rekordy są równe siebie, jeśli ich właściwości są równe, a ich typy są takie same, jak pokazano w następującym przykładzie:

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="RecordsEquality":::

Kompilator syntezuje dwie metody, które obsługują wydruk wyjściowy: <xref:System.Object.ToString> przesłonięcie i `PrintMembers` . `PrintMembers`Przyjmuje <xref:System.Text.StringBuilder?displayProperty=nameWithType> jako argument. Dodaje rozdzieloną przecinkami listę nazw właściwości i wartości dla wszystkich właściwości w typie rekordu. `PrintMembers` wywołuje podstawową implementację wszystkich rekordów pochodzących z innych rekordów. <xref:System.Object.ToString>Zastąpienie zwraca ciąg utworzony przez `PrintMembers` , ujęty w `{` i `}` . Na przykład <xref:System.Object.ToString> Metoda `Student` zwraca `string` podobne do poniższego kodu:

```csharp
"Student { LastName = Wagner, FirstName = Bill, Level = 11 }"
```

Przykłady pokazane do użycia tradycyjną składnią do deklarowania właściwości. Istnieje bardziej zwięzła forma o nazwie ***rekordy pozycyjne***.  Oto trzy typy rekordów zdefiniowane wcześniej jako rekordy pozycyjne:

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="PositionalRecords":::

Te deklaracje tworzą takie same funkcje jak wcześniejsza wersja (z kilkoma dodatkowymi funkcjami wymienionymi w poniższej sekcji). Te deklaracje kończą się średnikiem zamiast nawiasów, ponieważ te rekordy nie dodają dodatkowych metod. Możesz również dodać treść i dołączyć wszelkie dodatkowe metody:

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="RecordsWithMethods":::

Kompilator tworzy `Deconstruct` metodę dla rekordów pozycyjnych. `Deconstruct`Metoda ma parametry, które pasują do nazw wszystkich właściwości publicznych w typie rekordu. `Deconstruct`Metoda może służyć do dekonstruowania rekordu we właściwościach składnika:

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="DeconstructRecord":::

Na koniec rejestruje obsługę ***wyrażeń z wyrażeniami***. ***Wyrażenie with*** powoduje, że kompilator tworzy kopię rekordu, ale *o* określonych właściwościach zmodyfikowano:

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="Wither":::

Powyższy wiersz tworzy nowy `Person` rekord, w którym `LastName` Właściwość jest kopią `person` , a `FirstName` jest "Paul". W wyrażeniu można ustawić dowolną liczbę właściwości.  Każdy z tych elementów członkowskich, z wyjątkiem metody "Clone", może zostać przez Ciebie zapisany. Jeśli typ rekordu ma metodę, która pasuje do sygnatury dowolnej metody, kompilator nie wykonuje syntezy tej metody. W przykładzie wcześniejszego `Dog` rekordu znajduje się <xref:System.String.ToString> Przykładowa Metoda ze znakiem.

## <a name="init-only-setters"></a>Metody ustawiające tylko do inicjowania

***Tylko metody init*** zapewniają spójną składnię, aby inicjować elementy członkowskie obiektu. Inicjatory właściwości sprawiają, że wartość jest ustawiana dla właściwości. Minusemem jest to, że te właściwości muszą mieć wartość settable. Począwszy od języka C# 9,0, można tworzyć metody `init` dostępu zamiast `set` metod dostępu do właściwości i indeksatorów. Obiekty wywołujące mogą używać składni inicjatora właściwości do ustawiania tych wartości w wyrażeniach tworzenia, ale te właściwości są tylko do odczytu, gdy konstrukcja została ukończona. Tylko metody init umożliwiają zmianę stanu okna. To okno zostanie zamknięte po zakończeniu fazy budowania. Faza konstruowania skutecznie kończy działanie po wszystkich inicjalizacjach, w tym inicjatorach właściwości i wyrażeniach z.

W powyższym przykładzie dla rekordów pozycyjnych zademonstrowano użycie metody tylko init-Only do ustawiania właściwości przy użyciu wyrażenia with. Można zadeklarować tylko metody init w dowolnym typie, który napiszesz. Na przykład następująca struktura definiuje strukturę obserwacji pogody:

:::code language="csharp" source="snippets/whats-new-csharp9/WeatherObservation.cs" ID="DeclareWeatherObservation":::

Obiekty wywołujące mogą używać składni inicjatora właściwości do ustawiania wartości, pozostawiając zachowanie niezmienności:

:::code language="csharp" source="snippets/whats-new-csharp9/WeatherObservation.cs" ID="UseWeatherObservation":::

Jednak zmiana obserwacji po inicjacji jest błędem przez przypisanie do właściwości "init-Only" poza inicjalizacją:

```csharp
// Error! CS8852.
now.TemperatureInCelsius = 18;
```

Tylko metody init mogą być przydatne do ustawiania właściwości klasy bazowej z klas pochodnych. Mogą także ustawiać właściwości pochodne za pomocą pomocników w klasie bazowej. Rekordy pozycyjne deklarują właściwości przy użyciu tylko metod init. Te metody ustawiające są używane w wyrażeniach with. Można zadeklarować tylko metody init dla dowolnego `class` lub `struct` zdefiniowanego elementu.

## <a name="top-level-statements"></a>Instrukcje najwyższego poziomu

***Instrukcje najwyższego poziomu*** usuwają niepotrzebne procedury z wielu aplikacji. Rozważmy kanoniczną "Hello world!" Program

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

Istnieje tylko jeden wiersz kodu, który robi wszystko. Przy użyciu instrukcji najwyższego poziomu można zastąpić wszystkie te, które są standardową `using` instrukcją i pojedynczy wiersz, który wykonuje prace:

:::code language="csharp" source="snippets/whats-new-csharp9/Program.cs" ID="TopLevelStatements":::

Jeśli chciałeś zastosować program jednowierszowy, możesz usunąć `using` dyrektywę i użyć w pełni kwalifikowanej nazwy typu:

```csharp
System.Console.WriteLine("Hello World!");
```

Tylko jeden plik w aplikacji może używać instrukcji najwyższego poziomu. Jeśli kompilator odnajdzie instrukcje najwyższego poziomu w wielu plikach źródłowych, jest to błąd. Jest również błędem, jeśli łączysz instrukcje najwyższego poziomu z zadeklarowaną metodą punktu wejścia programu, zwykle `Main` metodę. W tym sensie można wziąć pod uwagę, że jeden plik zawiera instrukcje, które zwykle są w `Main` metodzie `Program` klasy.  

Jednym z najpopularniejszych zastosowania tej funkcji jest tworzenie materiałów edukacyjnych. Początkująci deweloperzy języka C# mogą pisać kanoniczny "Hello world!" w jednym lub dwóch wierszach kodu. Żadna z dodatkowych procedury nie jest wymagana. Niemniej deweloperzy mogą również znaleźć wiele użycia tej funkcji. W instrukcjach najwyższego poziomu można korzystać ze środowiska podobnego do skryptu na potrzeby eksperymentowania podobnego do tego, co zapewnia notesy Jupyter. Instrukcje najwyższego poziomu są doskonałe dla małych programów konsolowych i narzędzi. Usługa Azure Functions jest idealnym przypadkiem użycia dla instrukcji najwyższego poziomu.

Co najważniejsze, instrukcje najwyższego poziomu nie ograniczają zakresu lub złożoności aplikacji. Te instrukcje mogą uzyskać dostęp do dowolnej klasy .NET lub korzystać z niej. Nie ograniczają one również użycia argumentów wiersza polecenia ani zwracanych wartości. Instrukcje najwyższego poziomu mogą uzyskać dostęp do tablicy ciągów o nazwach argumentów. Jeśli instrukcje najwyższego poziomu zwracają wartość całkowitą, ta wartość zostanie zwróconym kodem zwrotnym z metody z syntezą `Main` . Instrukcje najwyższego poziomu mogą zawierać wyrażenia asynchroniczne. W takim przypadku syntezny punkt wejścia zwraca `Task` lub `Task<int>` .

## <a name="pattern-matching-enhancements"></a>Ulepszenia dopasowania wzorców

W języku C# 9 wprowadzono nowe ulepszenia dopasowania do wzorca:

- ***Wzorce typu*** zgodne ze zmienną jest typem
- ***Wzorce w nawiasach*** wymuszają lub podkreślają pierwszeństwo kombinacji wzorców
- *** `and` Wzorce conjunctive*** wymagają dopasowania obu wzorców
- *** `or` Wzorce disjunctive*** wymagają dopasowania do wzorca
- *** `not` Wzorce negacji*** wymagają, aby wzorzec nie był zgodny
- ***Wzorce relacyjne*** wymagają, aby dane wejściowe były mniejsze niż, większe niż lub równe lub większe niż lub równe danej stałej.

Wzorce te wzbogacają składnię wzorców. Rozważ następujące przykłady:

:::code language="csharp" source="snippets/whats-new-csharp9/PatternUtilities.cs" ID="IsLetterPattern":::

Alternatywnie, z opcjonalnymi nawiasami, aby wyczyścić ten element, który `and` ma wyższy priorytet niż `or` :

:::code language="csharp" source="snippets/whats-new-csharp9/PatternUtilities.cs" ID="IsLetterOrSeparatorPattern":::

Jednym z najpopularniejszych zastosowania jest nowa składnia dla sprawdzania wartości null:

```csharp
if (e is not null)
{
    // ...
}
```

Któregokolwiek z tych wzorców można używać w dowolnym kontekście, w którym wzorce są dozwolone: `is` wyrażenia wzorców, `switch` wyrażenia, zagnieżdżone wzorce i wzorzec `switch` `case` etykiety instrukcji.

## <a name="performance-and-interop"></a>Wydajność i międzyoperacyjność

Trzy nowe funkcje ulepszają obsługę natywnych bibliotek międzyoperacyjnych i niskiego poziomu, które wymagają wysokiej wydajności: natywnych liczb całkowitych, wskaźników funkcji i pomijania `localsinit` flagi.

Liczby całkowite o rozmiarze natywnym `nint` i `nuint` są typami całkowitymi. Są one wyrażone przez typy podstawowe <xref:System.IntPtr?displayProperty=nameWithType> i <xref:System.UIntPtr?displayProperty=nameWithType> . Kompilator wyświetla dodatkowe konwersje i operacje dla tych typów jako natywny liczby całkowite. Liczby całkowite o rozmiarze natywnym definiują właściwości dla `MaxValue` lub `MinValue` . Te wartości nie mogą być wyrażone jako stałe czasu kompilacji, ponieważ zależą od natywnego rozmiaru liczby całkowitej na maszynie docelowej. Te wartości są tylko do odczytu w czasie wykonywania. Można użyć wartości stałych dla `nint` zakresu [ `int.MinValue` .. `int.MaxValue`]. Można użyć wartości stałych dla `nuint` zakresu [ `uint.MinValue` .. `uint.MaxValue`]. Kompilator wykonuje stałe łamanie dla wszystkich operatorów jednoargumentowych i binarnych przy użyciu <xref:System.Int32?displayProperty=nameWithType> <xref:System.UInt32?displayProperty=nameWithType> typów i. Jeśli wynik nie mieści się w 32 bitów, operacja jest wykonywana w czasie wykonywania i nie jest traktowana jako stała. Natywne liczby całkowite mogą zwiększyć wydajność w scenariuszach, w których liczba obliczeń matematycznych jest szeroko stosowana i musi mieć możliwie najszybszą wydajność.

Wskaźniki funkcji umożliwiają łatwą składnię dostępu do kodów opcode IL `ldftn` i `calli` . Można zadeklarować wskaźniki funkcji przy użyciu nowej `delegate*` składni. `delegate*`Typ jest typem wskaźnika. Wywoływanie `delegate*` użycia typu `calli` , w przeciwieństwie do delegata, który używa `callvirt` `Invoke()` metody. Syntaktycznie wywołania są identyczne. Wywołanie wskaźnika funkcji używa `managed` konwencji wywoływania. Dodaj `unmanaged` słowo kluczowe po `delegate*` składni, aby zadeklarować, że chcesz `unmanaged` konwencję wywoływania. Inne konwencje wywoływania można określić przy użyciu atrybutów w `delegate*` deklaracji.

Na koniec możesz dodać polecenie, <xref:System.Runtime.CompilerServices.SkipLocalsInitAttribute?displayProperty=nameWithType> aby poinstruować kompilator, aby nie emitują `localsinit` flagi. Ta flaga instruuje CLR, aby nie zainicjowano wszystkich zmiennych lokalnych. `localsinit`Flaga była domyślnym zachowaniem języka C# od 1,0. Jednak dodatkowe zero inicjacji może mieć wymierny wpływ na wydajność w niektórych scenariuszach. W szczególności w przypadku korzystania z programu `stackalloc` . W takich przypadkach można dodać <xref:System.Runtime.CompilerServices.SkipLocalsInitAttribute> . Możesz dodać go do pojedynczej metody lub właściwości, lub do `class` modułu,, `struct` , `interface` lub nawet. Ten atrybut nie ma wpływu na `abstract` metody; wpływa na kod wygenerowany dla implementacji.

Te funkcje mogą zwiększyć wydajność w niektórych scenariuszach. Powinny być używane tylko po dokładnym przeprowadzeniu testu porównawczego zarówno przed, jak i po przyjęciu. Kod obejmujący liczby całkowite o liczbie natywnej musi być testowany na wielu platformach docelowych z różnymi rozmiarami całkowitymi. Inne funkcje wymagają niebezpiecznego kodu.

## <a name="fit-and-finish-features"></a>Funkcje dopasowywania i kończenia

Wiele innych funkcji ułatwia bardziej wydajne pisanie kodu. W języku C# 9,0 można pominąć typ w [ `new` wyrażeniu](../language-reference/operators/new-operator.md) , gdy typ tworzonego obiektu jest już znany. Najbardziej typowym zastosowaniem jest deklaracja pól:

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="WeatherStationField":::

Typ docelowy `new` może być również używany, gdy trzeba utworzyć nowy obiekt do przekazania jako argument do metody. Rozważmy `ForecastFor()` metodę o następującym podpisie:

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="ForecastSignature":::

Można wywołać go w następujący sposób:

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="TargetTypeNewArgument":::

Innym świetnym użyciem tej funkcji jest połączenie z właściwościami tylko init w celu zainicjowania nowego obiektu:

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="InitWeatherStation":::

Można zwrócić wystąpienie utworzone przez konstruktora domyślnego przy użyciu `return new();` instrukcji.

Podobna funkcja ulepsza rozpoznawanie typu docelowego [wyrażeń warunkowych](../language-reference/operators/conditional-operator.md). W przypadku tej zmiany dwa wyrażenia nie muszą mieć jawnej konwersji z jednego do drugiego, ale mogą jednocześnie mieć niejawne konwersje na typ docelowy. Ta zmiana jest niezauważalna. Informacje o tym, że niektóre wyrażenia warunkowe, które wcześniej wymagały rzutowania lub nie spowodują skompilowania, już teraz działają.

Począwszy od języka C# 9,0, można dodać `static` modyfikator do [wyrażeń lambda](../language-reference/operators/lambda-expressions.md) lub [metod anonimowych](../language-reference/operators/delegate-operator.md). Statyczne wyrażenia lambda są analogiczne do `static` funkcji lokalnych: statyczna metoda lambda lub anonimowa nie może przechwycić lokalnych zmiennych lub stanu wystąpienia. `static`Modyfikator zapobiega przypadkowemu przechwyceniu innych zmiennych.

Typy zwracane przez współwarianty zapewniają elastyczność dla zwracanych typów funkcji zastąpionych. Zastąpiona funkcja wirtualna może zwrócić typ pochodzący od typu zwracanego zadeklarowanego w metodzie klasy bazowej. Może to być przydatne w przypadku rekordów i dla innych typów, które obsługują wirtualne klony lub metody fabryki.

Ponadto [ `foreach` Pętla](../language-reference/keywords/foreach-in.md) rozpoznaje i używa metody rozszerzenia `GetEnumerator` , która w przeciwnym razie spełnia warunki `foreach` wzorca. Ta zmiana oznacza `foreach` spójność z innymi konstrukcjami opartymi na wzorcu, takimi jak wzorzec asynchroniczny i dekonstrukcja oparta na wzorcu. W tym przypadku ta zmiana oznacza, że można dodać `foreach` obsługę dowolnego typu. Należy ograniczyć jego użycie do momentu, gdy Wyliczenie obiektu ma sens w projekcie.

Następnie można użyć odrzutów jako parametrów w wyrażeniach lambda. Ta wygoda pozwala uniknąć nazywania argumentu, a kompilator może uniknąć korzystania z niego. Używasz `_` argumentu for. Aby uzyskać więcej informacji, zobacz [Parametry wejściowe sekcji wyrażenie lambda](../language-reference/operators/lambda-expressions.md#input-parameters-of-a-lambda-expression) w artykule [wyrażenia lambda](../language-reference/operators/lambda-expressions.md) .

Na koniec możesz teraz zastosować atrybuty do funkcji lokalnych. Na przykład można zastosować adnotacje atrybutu nullable do funkcji lokalnych.

## <a name="support-for-code-generators"></a>Obsługa generatorów kodu

Dwie funkcje końcowe obsługują generatory kodu w języku C#. Generatory kodu w języku C# to składnik, który można napisać, podobnie jak Analizator Roslyn lub poprawka kodu. Różnica polega na tym, że generatory kodu analizują kod i zapisują nowe pliki kodu źródłowego w ramach procesu kompilacji. Typowy generator kodu wyszukuje kod dla atrybutów lub innych konwencji.

Generator kodu odczytuje atrybuty lub inne elementy kodu przy użyciu interfejsów API analizy Roslyn. Z tych informacji dodaje nowy kod do kompilacji. Generatory źródła mogą jedynie dodawać kod; nie mogą modyfikować żadnego istniejącego kodu w kompilacji.

Dwie funkcje, które zostały dodane dla generatorów kodu są rozszerzeniami ***składni metody częściowej***i ***inicjatorami modułu***. Najpierw zmiany w metodach częściowych. Przed C# 9,0 metody częściowe są, `private` ale nie można określić modyfikatora dostępu, mają `void` Return i nie mogą mieć `out` parametrów. Te ograniczenia mające na celu, że jeśli nie zostanie podana implementacja metody, kompilator usuwa wszystkie wywołania metody częściowej. Język C# 9,0 usuwa te ograniczenia, ale wymaga, aby częściowa deklaracja metod była implementacją. Generatory kodu mogą zapewnić, że implementacja. Aby uniknąć wprowadzenia zmiany, kompilator traktuje każdą metodę częściową bez modyfikatora dostępu, aby przestrzegać starych reguł. Jeśli metoda częściowa zawiera `private` modyfikator dostępu, nowe reguły regulują tę metodę częściową.

Drugą nową funkcją dla generatorów kodu są ***inicjatory modułów***. Inicjatory modułów to metody, które mają <xref:System.Runtime.CompilerServices.ModuleInitializerAttribute> dołączony atrybut. Te metody będą wywoływane przez środowisko uruchomieniowe podczas ładowania zestawu. Metoda inicjatora modułu:

- Musi być statyczna
- Musi być bez parametrów
- Musi zwracać typ void
- Nie może być metodą generyczną
- Nie może być zawarta w klasie generycznej
- Musi być dostępny z poziomu zawierającego go modułu

Ostatni punkt Bullet efektywnie oznacza, że metoda i jej Klasa zawierająca muszą być wewnętrzne lub publiczne. Metoda nie może być funkcją lokalną.
