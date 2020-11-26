---
title: Bloki konstrukcyjne programów C# "
description: Dowiedz się więcej o elementach członkowskich, wyrażeniach i instrukcjach języka C#. Typy zawierają składowe, które są zapisywane. Te elementy członkowskie są kompilowane z instrukcji i wyrażeń.
ms.date: 08/06/2020
ms.openlocfilehash: e4350f2c2b6005fb59dd868f0f7f628bd07b0053
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "93342699"
---
# <a name="program-building-blocks"></a>Bloki konstrukcyjne programu

Typy opisane w poprzednim artykule są kompilowane przy użyciu następujących bloków konstrukcyjnych: [ * **składowych** _](../programming-guide/classes-and-structs/members.md), [ _*_wyrażeń_*_ i _*_instrukcji_*_](../programming-guide/statements-expressions-operators/index.md).

## <a name="members"></a>Elementy członkowskie

Członkami elementu `class` są _*_statyczne elementy członkowskie_*_ i _*_wystąpienia_*_. Statyczne składowe należą do klas, a elementy członkowskie wystąpienia należą do obiektów (wystąpień klas).

Poniższa lista zawiera przegląd rodzajów elementów członkowskich, które może zawierać Klasa.

- _ * Stałe * *: wartości stałe skojarzone z klasą
- **Pola**: zmienne, które są skojarzone z klasą
- **Metody**: akcje, które mogą być wykonywane przez klasę
- **Właściwości**: akcje skojarzone z odczytem i pisaniem nazwanych właściwości klasy
- **Indeksatory**: akcje skojarzone z wystąpieniami indeksowania klasy, takimi jak tablica
- **Zdarzenia**: powiadomienia, które mogą być generowane przez klasę
- **Operatory**: konwersje i operatory wyrażeń obsługiwane przez klasę
- **Konstruktory**: akcje wymagane do zainicjowania wystąpień klasy lub samej klasy
- **Finalizatory**: akcje wykonywane przed wystąpieniem klasy są trwale odrzucone
- **Typy**: typy zagnieżdżone zadeklarowane przez klasę

## <a name="accessibility"></a>Ułatwienia dostępu

Każdy element członkowski klasy ma skojarzoną dostępność, która kontroluje regiony tekstu programu, które mogą uzyskać dostęp do elementu członkowskiego. Istnieje sześć możliwych form ułatwień dostępu. Modyfikatory dostępu są zestawione poniżej.

- `public`: Dostęp nie jest ograniczony.
- `private`: Dostęp jest ograniczony do tej klasy.
- `protected`: Dostęp jest ograniczony do tej klasy lub klas pochodzących od tej klasy.
- `internal`: Dostęp jest ograniczony do bieżącego zestawu ( `.exe` lub `.dll` ).
- `protected internal`: Dostęp jest ograniczony do tej klasy, klas pochodnych tej klasy lub klas w tym samym zestawie.
- `private protected`: Dostęp jest ograniczony do tej klasy lub klas pochodzących od tego typu w ramach tego samego zestawu.

## <a name="fields"></a>Pola

*Pole* jest zmienną, która jest skojarzona z klasą lub wystąpieniem klasy.

Pole zadeklarowane ze modyfikatorem static definiuje pole statyczne. Pole statyczne identyfikuje dokładnie jedną lokalizację magazynu. Niezależnie od tego, ile wystąpień klasy zostało utworzonych, istnieje tylko jedna kopia pola statycznego.

Pole zadeklarowane bez modyfikatora static definiuje pole wystąpienia. Każde wystąpienie klasy zawiera oddzielną kopię wszystkich pól wystąpienia tej klasy.

W poniższym przykładzie każde wystąpienie `Color` klasy ma oddzielną kopię `R` `G` pól,, i `B` wystąpienia, ale istnieje tylko jedna kopia `Black` pól,, `White` `Red` , `Green` i `Blue` pola statyczne:

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="ColorClassDefinition":::

Jak pokazano w poprzednim przykładzie *pola tylko do odczytu* mogą być zadeklarowane za pomocą `readonly` modyfikatora. Przypisanie do pola tylko do odczytu może wystąpić tylko jako część deklaracji pola lub konstruktora w tej samej klasie.

## <a name="methods"></a>Metody

*Metoda* to element członkowski implementujący obliczenia lub akcję, które mogą być wykonywane przez obiekt lub klasę. *Metody statyczne* są dostępne za pomocą klasy. *Metody wystąpienia* są dostępne za pomocą wystąpień klasy.

Metody mogą mieć listę *parametrów* reprezentujących wartości lub odwołania do zmiennych, które są przenoszone do metody. Metody mają *zwracany typ*, który określa typ wartości obliczanej i zwracanej przez metodę. Zwracany typ metody to `void` Jeśli nie zwraca wartości.

Podobnie jak typy, metody mogą także mieć zestaw parametrów typu, dla których argumenty typu muszą być określone, gdy wywoływana jest metoda. W przeciwieństwie do typów, argumenty typu często można wywnioskować na podstawie argumentów wywołania metody i nie muszą być jawnie określone.

*Sygnatura* metody musi być unikatowa w klasie, w której metoda jest zadeklarowana. Podpis metody składa się z nazwy metody, liczby parametrów typu oraz liczby, modyfikatorów i typów jego parametrów. Sygnatura metody nie zawiera typu zwracanego.

Gdy treść metody jest pojedynczym wyrażeniem, Metoda może być zdefiniowana przy użyciu formatu wyrażenia kompaktowego, jak pokazano w następującym przykładzie:

```csharp
public override string ToString() => "This is an object";
```

### <a name="parameters"></a>Parametry

Parametry służą do przekazywania wartości lub odwołań do zmiennych do metod. Parametry metody pobierają rzeczywiste wartości z *argumentów* , które są określone podczas wywoływania metody. Istnieją cztery rodzaje parametrów: parametry wartości, parametry odwołania, parametry wyjściowe i tablice parametrów.

*Parametr value* jest używany do przekazywania argumentów wejściowych. Parametr value odnosi się do zmiennej lokalnej, która pobiera jej wartość początkową z argumentu, który został przesłany dla parametru. Modyfikacje parametru value nie wpływają na argument, który został przesłany dla parametru.

Parametry wartości mogą być opcjonalne, określając wartość domyślną, aby można było pominąć odpowiednie argumenty.

*Parametr Reference* służy do przekazywania argumentów przez odwołanie. Argument przesłany dla parametru odwołania musi być zmienną z określoną wartością. Podczas wykonywania metody parametr Reference reprezentuje tę samą lokalizację magazynu co zmienna argumentu. Parametr odwołania jest zadeklarowany z `ref` modyfikatorem. W poniższym przykładzie pokazano sposób użycia `ref` parametrów.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="RefExample":::

*Parametr wyjściowy* jest używany do przekazywania argumentów przez odwołanie. Jest on podobny do parametru Reference, z tą różnicą, że nie wymaga jawnie przypisywania wartości do argumentu dostarczonego przez wywołującego. Parametr wyjściowy jest zadeklarowany z `out` modyfikatorem. W poniższym przykładzie pokazano użycie `out` parametrów przy użyciu składni wprowadzonej w języku C# 7.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="OutExample":::

*Tablica parametrów* umożliwia przekazanie zmiennej liczbie argumentów do metody. Tablica parametrów jest zadeklarowana z `params` modyfikatorem. Tylko ostatni parametr metody może być tablicą parametrów, a typ tablicy parametrów musi być typem tablicy jednowymiarowej. `Write`Metody i `WriteLine` <xref:System.Console?displayProperty=nameWithType> klasy są dobrymi przykładami użycia tablicy parametrów. Są one deklarowane w następujący sposób.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="ConsoleExtract":::

W metodzie, która używa tablicy parametrów, tablica parametrów zachowuje się dokładnie tak jak zwykły parametr typu tablicy. Jednak w wywołaniu metody z tablicą parametrów, możliwe jest przekazanie jednego argumentu typu tablicy parametrów lub dowolnej liczby argumentów typu elementu tablicy parametrów w postaci. W tym drugim przypadku wystąpienie tablicy jest automatycznie tworzone i inicjowane z podanym argumentami. Ten przykład

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="UseParamsArgs":::

jest równoznaczny z zapisem poniżej.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="CompilerParams":::

### <a name="method-body-and-local-variables"></a>Treść metody i zmienne lokalne

Treść metody Określa instrukcje do wykonania, gdy metoda jest wywoływana.

Treść metody może deklarować zmienne, które są specyficzne dla wywołania metody. Takie zmienne są nazywane *zmiennymi lokalnymi*. Deklaracja zmiennej lokalnej określa nazwę typu, nazwę zmiennej i prawdopodobnie wartość początkową. Poniższy przykład deklaruje zmienną lokalną `i` z początkową wartością zero i zmienną lokalną `j` bez wartości początkowej.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="SquaresClass":::

Język C# wymaga, aby zmienna lokalna była *przypisana ostatecznie* przed uzyskaniem jej wartości. Na przykład jeśli deklaracja poprzedniej `i` nie zawierała wartości początkowej, kompilator zgłosi błąd dla późniejszych użycia, `i` ponieważ nie `i` będzie on ostatecznie przypisany w tych punktach w programie.

Metoda może użyć `return` instrukcji do zwrócenia kontroli do obiektu wywołującego. W wyniku zwrócenia metody `void` `return` instrukcje nie mogą określać wyrażenia. W metodzie zwracającej wartości inne niż void `return` instrukcje muszą zawierać wyrażenie, które oblicza wartość zwracaną.

### <a name="static-and-instance-methods"></a>Metody static i instance

Metoda zadeklarowana za pomocą `static` modyfikatora jest *metodą statyczną*. Metoda statyczna nie działa w konkretnym wystąpieniu i może bezpośrednio uzyskiwać dostęp do statycznych elementów członkowskich.

Metoda zadeklarowana bez `static` modyfikatora jest *metodą wystąpienia*. Metoda wystąpienia działa w konkretnym wystąpieniu i może uzyskiwać dostęp do elementów członkowskich static i instance. Wystąpienie, na którym wywołano metodę wystąpienia, można jawnie uzyskać do niego dostęp `this` . Jest to błąd, aby odwołać się do `this` w metodzie statycznej.

Następująca `Entity` Klasa zawiera elementy członkowskie statyczne i wystąpienia.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="EntityClass":::

Każde `Entity` wystąpienie zawiera numer seryjny (i najprawdopodobniej inne informacje, które nie są wyświetlane w tym miejscu). `Entity`Konstruktor (który przypomina metodę wystąpienia) Inicjuje nowe wystąpienie przy użyciu następnego dostępnego numeru seryjnego. Ponieważ Konstruktor jest członkiem wystąpienia, dozwolone jest uzyskanie dostępu zarówno do `_serialNo` pola wystąpienia, jak i `s_nextSerialNo` pola statycznego.

`GetNextSerialNo`Metody i `SetNextSerialNo` static mogą uzyskać dostęp do `s_nextSerialNo` pola statycznego, ale może to być błąd, aby uzyskać bezpośredni dostęp do `_serialNo` pola wystąpienia.

Poniższy przykład pokazuje użycie `Entity` klasy.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="UsingEntity":::

`SetNextSerialNo`Metody i `GetNextSerialNo` Static są wywoływane w klasie, podczas gdy `GetSerialNo` metoda wystąpienia jest wywoływana w wystąpieniach klasy.

### <a name="virtual-override-and-abstract-methods"></a>Metody wirtualne, przesłonięcia i abstrakcyjne

Gdy deklaracja metody wystąpienia zawiera `virtual` modyfikator, metoda jest uznawana za *metodę wirtualną*. Gdy nie jest dostępny żaden modyfikator wirtualny, metoda jest uznawana za *metodę niewirtualną*.

Gdy wywoływana jest metoda wirtualna, *typem czasu wykonywania* wystąpienia, dla którego odbywa się wywołanie określa rzeczywistą implementację metody do wywołania. W wywołaniu metody niewirtualnej *Typ czasu kompilacji* wystąpienia jest czynnikiem decydującym.

Metoda wirtualna może zostać *przesłonięta* w klasie pochodnej. Gdy deklaracja metody wystąpienia zawiera modyfikator przesłonięcia, metoda zastępuje dziedziczonej metody wirtualnej tą samą sygnaturą. Deklaracja metody wirtualnej wprowadza nową metodę. Deklaracja metody przesłonięcia specjalizacji istniejącej dziedziczonej metody wirtualnej przez podanie nowej implementacji tej metody.

*Metoda abstrakcyjna* jest metodą wirtualną bez implementacji. Metoda abstrakcyjna jest zadeklarowana z `abstract` modyfikatorem i jest dozwolona tylko w klasie abstrakcyjnej. Metoda abstrakcyjna musi zostać przesłonięta w każdej nieabstrakcyjnej klasie pochodnej.

Poniższy przykład deklaruje klasę abstrakcyjną, `Expression` która reprezentuje węzeł drzewa wyrażeń i trzy klasy pochodne, `Constant` , `VariableReference` i `Operation` , które implementują węzły drzewa wyrażeń dla stałych, odwołań do zmiennych i operacji arytmetycznych. (Ten przykład jest podobny do, ale nie jest powiązany z typami drzewa wyrażeń).

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="WorkingWithExpressions":::

Poprzednie cztery klasy mogą służyć do modelowania wyrażeń arytmetycznych. Na przykład przy użyciu wystąpień tych klas wyrażenie `x + 3` może być reprezentowane w następujący sposób.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="UseExpressions":::

`Evaluate`Metoda `Expression` wystąpienia jest wywoływana w celu obliczenia danego wyrażenia i utworzenia `double` wartości. Metoda przyjmuje `Dictionary` argument, który zawiera nazwy zmiennych (jako klucze wpisów) i wartości (jako wartości wpisów). Ponieważ `Evaluate` jest to metoda abstrakcyjna, klasy nieabstrakcyjne pochodne `Expression` muszą zostać przesłonięte `Evaluate` .

`Constant`Implementacja `Evaluate` po prostu zwraca przechowywaną stałą. `VariableReference`Implementacja programu wyszukuje nazwę zmiennej w słowniku i zwraca wartość wynikową. `Operation`Implementacja najpierw szacuje lewy i prawy operand (cyklicznie wywołując ich `Evaluate` metody), a następnie wykonuje daną operację arytmetyczną.

Poniższy program używa `Expression` klas do obliczenia wyrażenia `x * (y + 2)` pod kątem różnych wartości `x` i `y` .

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="UsingExpressions":::

### <a name="method-overloading"></a>Przeciążanie metody

*Przeciążanie* metod pozwala wielu metodom w tej samej klasie mieć taką samą nazwę, o ile mają unikatowe podpisy. Podczas kompilowania wywołania przeciążonej metody kompilator używa *rozdzielczości przeciążenia* do określenia konkretnej metody do wywołania. Rozpoznanie przeciążenia umożliwia znalezienie jednej metody, która najlepiej pasuje do argumentów. Jeśli nie można znaleźć pojedynczego najlepszego dopasowania, zostanie zgłoszony błąd. W poniższym przykładzie przedstawiono sposób rozwiązywania przeciążenia. Komentarz dla każdego wywołania `UsageExample` metody pokazuje, która metoda jest wywoływana.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="Overloading":::

Jak pokazano w przykładzie, dana metoda może być zawsze wybierana przez jawne rzutowanie argumentów do dokładnych typów parametrów i argumentów typu.

## <a name="other-function-members"></a>Inne elementy członkowskie funkcji

Elementy członkowskie, które zawierają kod wykonywalny, są określane zbiorczo jako *elementy członkowskie* klasy. W poprzedniej sekcji opisano metody, które stanowią podstawowe typy elementów członkowskich funkcji. W tej sekcji opisano inne rodzaje składowych funkcji obsługiwane przez język C#: konstruktory, właściwości, indeksatory, zdarzenia, operatory i finalizatory.

Poniższy przykład pokazuje klasę generyczną o nazwie `MyList<T>` , która implementuje rozwijaną listę obiektów. Klasa zawiera kilka przykładów typowych rodzajów elementów członkowskich funkcji.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="ListExample":::

### <a name="constructors"></a>Konstruktory

C# obsługuje zarówno wystąpienie, jak i konstruktory statyczne. *Konstruktor wystąpienia* jest członkiem, który implementuje akcje wymagane do zainicjowania wystąpienia klasy. *Statyczny Konstruktor* jest członkiem, który implementuje akcje wymagane do zainicjowania samej klasy podczas pierwszego ładowania.

Konstruktor jest zadeklarowany jak metoda bez zwracanego typu i o takiej samej nazwie jak zawierająca klasy. Jeśli deklaracja konstruktora zawiera `static` modyfikator, deklaruje Konstruktor statyczny. W przeciwnym razie deklaruje Konstruktor wystąpienia.

Konstruktory wystąpień mogą być przeciążone i mogą mieć parametry opcjonalne. Na przykład `MyList<T>` Klasa deklaruje jeden Konstruktor wystąpienia z jednym opcjonalnym `int` parametrem. Konstruktory wystąpień są wywoływane przy użyciu `new` operatora. Poniższe instrukcje przydzielą dwa `MyList<string>` wystąpienia przy użyciu konstruktora `MyList` klasy z argumentem opcjonalnym i bez niego.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="CreateLists":::

W przeciwieństwie do innych elementów członkowskich, konstruktory wystąpień nie są dziedziczone. Klasa nie ma konstruktorów wystąpień innych niż te konstruktory faktycznie zadeklarowane w klasie. Jeśli nie podano konstruktora wystąpienia dla klasy, zostanie automatycznie podana pusta wartość bez parametrów.

### <a name="properties"></a>Właściwości

*Właściwości* są naturalnym rozszerzeniem pól. Oba są nazwanymi członkami ze skojarzonymi typami, a składnia dostępu do pól i właściwości jest taka sama. Jednak w przeciwieństwie do pól właściwości nie oznacza lokalizacji magazynu. Zamiast tego właściwości mają metody *dostępu* określające instrukcje wykonywane, gdy ich wartości są odczytywane lub zapisywane.

Właściwość jest zadeklarowana jako pole, z tą różnicą, że deklaracja kończy się metodą dostępu get lub zestawem akcesora zapisanym między ogranicznikami `{` i `}` zamiast kończyć się średnikiem. Właściwość, która ma zarówno metodę dostępu get, jak i zestaw akcesora zestawu jest *właściwością do odczytu i zapisu*, właściwość, która ma tylko metodę dostępu get, jest *właściwością tylko do odczytu*, a właściwość, która ma tylko metodę dostępu zestawu, jest *właściwością tylko do zapisu*.

Metoda dostępu get odpowiada metodzie bez parametrów z wartością zwracaną typu właściwości. Metoda dostępu zestawu odpowiada metodzie z pojedynczym parametrem o nazwie Value i bez zwracanego typu. Metoda dostępu get oblicza wartość właściwości. Metoda dostępu set udostępnia nową wartość właściwości. Gdy właściwość jest obiektem docelowym przypisania lub operandem `++` lub `--` , metoda dostępu set jest wywoływana. W innych przypadkach, w których właściwość jest przywoływana, metoda dostępu get jest wywoływana.

`MyList<T>`Klasa deklaruje dwie właściwości `Count` i `Capacity` , które są tylko do odczytu i odczytu i zapisu. Poniższy kod stanowi przykład użycia tych właściwości:

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="AccessProperties":::

Podobnie jak pola i metody, C# obsługuje zarówno właściwości wystąpienia, jak i właściwości statyczne. Właściwości statyczne są zadeklarowane za pomocą modyfikatora static, a właściwości wystąpienia są deklarowane bez użycia.

Metody dostępu właściwości mogą być wirtualne. Gdy Deklaracja właściwości zawiera `virtual` `abstract` modyfikator, lub `override` , ma zastosowanie do akcesorów właściwości.

### <a name="indexers"></a>Indeksatory

*Indeksator* jest członkiem, który umożliwia indeksowanie obiektów w taki sam sposób jak w przypadku tablicy. Indeksator jest zadeklarowany jak właściwość, z tą różnicą, że po nazwie składowej `this` następuje lista parametrów zapisywana między ogranicznikami `[` i `]` . Parametry są dostępne w metodach dostępu indeksatora. Podobnie jak w przypadku właściwości, indeksatory mogą być tylko do odczytu i zapisu, tylko do odczytu i do zapisu, a Akcesory dla indeksatora mogą być wirtualne.

`MyList<T>`Klasa deklaruje pojedynczy indeksator do odczytu i zapisu, który pobiera `int` parametr. Indeksator umożliwia indeksowanie `MyList<T>` wystąpień z `int` wartościami. Przykład:

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="ListAccess":::

Indeksatory mogą być przeciążone. Klasa może deklarować wiele indeksatorów, o ile liczba lub typy ich parametrów różnią się.

### <a name="events"></a>Zdarzenia

*Zdarzenie* jest członkiem, który umożliwia klasy lub obiektowi dostarczanie powiadomień. Zdarzenie jest zadeklarowane jak pole, z tą różnicą, że deklaracja zawiera `event` słowo kluczowe i typ musi być typem delegata.

W obrębie klasy, która deklaruje element członkowski zdarzenia, zdarzenie zachowuje się podobnie jak pole typu delegata (pod warunkiem, że zdarzenie nie jest abstrakcyjne i nie deklaruje metod dostępu). W polu jest przechowywane odwołanie do delegata, który reprezentuje programy obsługi zdarzeń, które zostały dodane do zdarzenia. Jeśli nie ma żadnych programów obsługi zdarzeń, pole jest `null` .

`MyList<T>`Klasa deklaruje pojedynczy element członkowski zdarzenia o nazwie `Changed` , który wskazuje, że dodano nowy element do listy. Zmienione zdarzenie jest wywoływane przez `OnChanged` metodę wirtualną, która najpierw sprawdza, czy zdarzenie jest `null` (oznacza, że nie ma żadnych programów obsługi). Pojęcie podniesienia poziomu zdarzenia jest dokładnie równoważne do wywołania delegata reprezentowanego przez zdarzenie. Nie istnieją żadne specjalne konstrukcje języka do wywoływania zdarzeń.

Klienci reagują na zdarzenia za poorednictwem *programów obsługi zdarzeń*. Procedury obsługi zdarzeń są dołączane przy użyciu `+=` operatora i usuwane przy użyciu `-=` operatora. Poniższy przykład dołącza procedurę obsługi zdarzeń do `Changed` zdarzenia `MyList<string>` .

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="RespondToEvents":::

W przypadku zaawansowanych scenariuszy, w których wymagana jest kontrola bazowego magazynu zdarzenia, deklaracja zdarzenia może jawnie dostarczyć i akcesorów `add` `remove` , które są podobne do `set` metody dostępu do właściwości.

### <a name="operators"></a>Operatory

*Operator* jest członkiem, który definiuje znaczenie zastosowania określonego operatora wyrażenia do wystąpienia klasy. Można zdefiniować trzy rodzaje operatorów: operatory jednoargumentowe, operatory binarne i operatory konwersji. Wszystkie operatory muszą być zadeklarowane jako `public` i `static` .

`MyList<T>`Klasa deklaruje dwa operatory `operator ==` i `operator !=` . Te zastąpione operatory dają nowe znaczenie dla wyrażeń, które stosują te operatory do `MyList` wystąpień. W tym celu operatory definiują równość dwóch `MyList<T>` wystąpień w porównaniu z poszczególnymi obiektami zawartymi przy użyciu `Equals` metod. Poniższy przykład używa `==` operatora do porównywania dwóch `MyList<int>` wystąpień.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="ListAddition":::

Pierwsze dane `Console.WriteLine` wyjściowe, `True` ponieważ dwie listy zawierają tę samą liczbę obiektów z tymi samymi wartościami w tej samej kolejności. `MyList<T>`Nie zdefiniowano `operator ==` , pierwsze `Console.WriteLine` miałoby wynik, `False` ponieważ `a` i odwołuje się do `b` różnych `MyList<int>` wystąpień.

### <a name="finalizers"></a>Finalizatory

*Finalizator* jest członkiem, który implementuje akcje wymagane do sfinalizowania wystąpienia klasy. Zazwyczaj finalizator jest wymagany do zwolnienia niezarządzanych zasobów. Finalizatory nie mogą mieć parametrów, nie mogą mieć modyfikatorów dostępności i nie mogą być wywoływane jawnie. Finalizator dla wystąpienia jest wywoływany automatycznie podczas wyrzucania elementów bezużytecznych. Aby uzyskać więcej informacji, zobacz artykuł dotyczący [finalizatorów](../programming-guide/classes-and-structs/destructors.md).

Moduł wyrzucania elementów bezużytecznych jest dozwolony w przypadku podejmowania decyzji podczas zbierania obiektów i uruchamiania finalizatorów. W odniesieniu do chronometrażu wywołań finalizatora nie jest deterministyczna, a finalizatory mogą być wykonywane na dowolnym wątku. Z tych i innych powodów klasy powinny implementować finalizatory tylko wtedy, gdy żadne inne rozwiązania nie są możliwe.

`using`Instrukcja zawiera lepsze podejście do niszczenia obiektów.

## <a name="expressions"></a>Wyrażenia

*Wyrażenia* są zbudowane z *argumentów operacji* i *operatorów*. Operatory wyrażenia wskazują, które operacje mają być stosowane do operandów. Przykłady operatorów obejmują `+` , `-` , `*` , `/` , i `new` . Przykłady operandów obejmują literały, pola, zmienne lokalne i wyrażenia.

Gdy wyrażenie zawiera wiele operatorów, *pierwszeństwo* operatorów kontroluje kolejność, w jakiej są oceniane poszczególne operatory. Na przykład wyrażenie `x + y * z` jest oceniane tak, jakby `x + (y * z)` `*` operator miał wyższy priorytet niż `+` operator.

Gdy operand występuje między dwoma operatorami o takim samym priorytecie, *łączność* operatorów kontroluje kolejność wykonywania operacji:

* Z wyjątkiem operatorów przypisania i łączenia wartości null wszystkie operatory binarne są z *lewej strony skojarzenia*, co oznacza, że operacje są wykonywane od lewej do prawej. Na przykład, `x + y + z` jest oceniane jako `(x + y) + z` .
* Operatory przypisania, przeciąganie wartości null `??` i `??=` operatory, a operator warunkowy `?:` są z *prawej strony skojarzenia*, co oznacza, że operacje są wykonywane od prawej do lewej. Na przykład, `x = y = z` jest oceniane jako `x = (y = z)` .

Pierwszeństwo i łączność można kontrolować za pomocą nawiasów. Na przykład program `x + y * z` najpierw mnoży `y` przez, `z` a następnie dodaje wynik do `x` , ale `(x + y) * z` najpierw dodaje `x` i `y` i następnie mnoży wynik przez `z` .

Większość operatorów może być [*przeciążona*](../language-reference/operators/operator-overloading.md). Przeciążanie operatora umożliwia określenie implementacji operatora zdefiniowanego przez użytkownika dla operacji, w których jeden lub oba operandy są klasy lub typu struktury zdefiniowanej przez użytkownika.

Język C# zawiera wiele operatorów umożliwiających operacje [arytmetyczne](../language-reference/operators/arithmetic-operators.md), [logiczne](../language-reference/operators/boolean-logical-operators.md), [bitowe i przesunięcia](../language-reference/operators/bitwise-and-shift-operators.md) oraz porównania [równości](../language-reference/operators/equality-operators.md) i [kolejności](../language-reference/operators/comparison-operators.md) .

Aby uzyskać pełną listę operatorów języka C# uporządkowanych według poziomu pierwszeństwa, zobacz [operatory języka c#](../language-reference/operators/index.md).

## <a name="statements"></a>Instrukcje

Akcje programu są wyrażane przy użyciu *instrukcji*. Język C# obsługuje kilka różnych rodzajów instrukcji, które są zdefiniowane w postaci instrukcji osadzonych.

- *Blok* umożliwia zapisanie wielu instrukcji w kontekstach, w których Pojedyncza instrukcja jest dozwolona. Blok składa się z listy instrukcji pisanych między ogranicznikami `{` i `}` .
- *Instrukcje deklaracji* są używane do deklarowania zmiennych lokalnych i stałych.
- *Instrukcje wyrażeń* są używane do obliczania wyrażeń. Wyrażenia, które mogą być używane jako instrukcje, obejmują wywołania metod, alokacje obiektów przy użyciu `new` operatora, przypisań przy użyciu `=` i operatorów przypisania złożonego, operacji zwiększania i zmniejszania przy użyciu `++` `--` operatorów i i `await` wyrażeń.
- *Instrukcje wyboru* są używane do wybierania jednej z wielu możliwych instrukcji do wykonania na podstawie wartości niektórych wyrażeń. Ta grupa zawiera `if` instrukcje i `switch` .
- *Instrukcje iteracji* są używane do wielokrotnego wykonywania osadzonej instrukcji. Ta grupa zawiera `while` instrukcje, `do` , `for` , i `foreach` .
- *Instrukcje skoku* są używane do transferowania kontroli. Ta grupa zawiera `break` instrukcje, `continue` ,,, `goto` `throw` `return` i `yield` .
- `try`Instrukcja... służy `catch` do przechwytywania wyjątków, które występują podczas wykonywania bloku, a `try` instrukcja... `finally` jest używana do określania kodu finalizacji, który jest zawsze wykonywany, niezależnie od tego, czy wystąpił wyjątek, czy nie.
- `checked`Instrukcje and `unchecked` są używane do kontrolowania kontekstu sprawdzania przepełnienia dla operacji arytmetycznych i konwersji typu całkowitego.
- `lock`Instrukcja służy do uzyskiwania blokady wzajemnego wykluczania dla danego obiektu, wykonywania instrukcji i zwalniania blokady.
- `using`Instrukcja służy do uzyskiwania zasobu, wykonywania instrukcji, a następnie usuwania tego zasobu.

Poniżej wymieniono rodzaje instrukcji, które mogą być używane:

* Deklaracja zmiennej lokalnej.
* Lokalna deklaracja stała.
* Instrukcja wyrażenia.
* `if` Merge.
* `switch` Merge.
* `while` Merge.
* `do` Merge.
* `for` Merge.
* `foreach` Merge.
* `break` Merge.
* `continue` Merge.
* `goto` Merge.
* `return` Merge.
* `yield` Merge.
* `throw` instrukcje i `try` instrukcje.
* `checked` i `unchecked` instrukcji.
* `lock` Merge.
* `using` Merge.

>[!div class="step-by-step"]
>[Poprzedni](types.md) 
> [Dalej](features.md)
