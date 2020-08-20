---
title: Przewodnik programowania w języku C# — C#
description: Jesteś nowym w języku C#? Poznaj podstawy języka.
ms.date: 08/06/2020
ms.openlocfilehash: 9fa292e8e85832d831f36cf0f21512aa0cf32580
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656231"
---
# <a name="a-tour-of-the-c-language"></a>Przewodnik po języku C#

C# ("Zobacz Sharp") to nowoczesny, zorientowany obiektowo i bezpieczny dla typu język programowania. Język C# ma swoje elementy główne w rodzinie C i będzie od razu zaznajomiony z programistami C, C++, Java i JavaScript. Ten przewodnik zawiera omówienie głównych składników języka w języku C# 8 i jego wcześniejszych wersjach. Jeśli chcesz poznać język za pomocą przykładów interaktywnych, wypróbuj samouczki [dotyczące języka C#](../tutorials/intro-to-csharp/index.md) .

C# to zorientowany obiektowo język programowania ***zorientowany na składniki*** . Język c# udostępnia konstrukcje języka, aby bezpośrednio obsługiwać te koncepcje, co pozwala na tworzenie i używanie składników oprogramowania w języku C#. Ze względu na to, że język C# dodał funkcje do obsługi nowych obciążeń i rozwijających się praktyk projektowania oprogramowania.

Kilka funkcji języka C# pomaga w konstruowaniu niezawodnych i trwałych aplikacji. [***Wyrzucanie elementów bezużytecznych***](../../standard/garbage-collection/index.md) automatycznie odzyskuje ilość pamięci zajętą nieosiągalnymi obiektami. [***Obsługa wyjątków***](../programming-guide/exceptions/index.md) zapewnia strukturalne i rozszerzalne podejście do wykrywania błędów i odzyskiwania. [***Wyrażenia lambda***](../language-reference/operators/lambda-expressions.md) obsługują techniki programowania funkcjonalnego. [***Składnia zapytania***](../linq/index.md) tworzy wspólny wzorzec do pracy z danymi z dowolnego źródła. Obsługa języka dla [***operacji asynchronicznych***](../programming-guide/concepts/async/index.md) zapewnia składnię tworzenia systemów rozproszonych. [***Dopasowywanie wzorców***](..//pattern-matching.md) zawiera składnię umożliwiającą łatwe oddzielenie danych z algorytmów w nowoczesnych systemach rozproszonych. Język C# ma [***ujednolicony system typów***](../programming-guide/types/index.md). Wszystkie typy C#, w tym typy pierwotne, takie jak `int` i `double` , dziedziczą z jednego `object` typu głównego. Wszystkie typy korzystają z zestawu typowych operacji. Wartości dowolnego typu mogą być przechowywane, transportowane i obsługiwane w spójny sposób. Ponadto w języku C# obsługiwane są zarówno typy odwołań zdefiniowane przez użytkownika, jak i typy wartości. Język C# umożliwia dynamiczne przydzielanie obiektów i przechowywanie w wierszu lekkich struktur.

Język C# wyróżnia ***wersje*** , aby zapewnić zgodność programów i bibliotek z upływem czasu. Aspekty projektu języka C#, które miały bezpośrednio wpływ na kwestie związane z obsługą wersji, obejmują oddzielność `virtual` i `override` modyfikatory, reguły rozpoznawania przeciążania metod oraz obsługę jawnych deklaracji elementów członkowskich interfejsu.

## <a name="hello-world"></a>Hello world

Program "Hello, World" jest tradycyjnie używany do wprowadzania języka programowania. W tym miejscu jest w języku C#:

:::code language="csharp" interactive="try-dotnet" source="./snippets/shared/HelloWorld.cs":::

Program "Hello, World" rozpoczyna się od `using` dyrektywy, która odwołuje się do `System` przestrzeni nazw. Przestrzenie nazw zapewniają hierarchiczny sposób organizowania programów i bibliotek w języku C#. Przestrzenie nazw zawierają typy i inne przestrzenie nazw — na przykład `System` przestrzeń nazw zawiera wiele typów, takich jak `Console` Klasa, do której odwołuje się program, oraz liczba innych przestrzeni nazw, takich jak `IO` i `Collections` . `using`Dyrektywa odwołująca się do danej przestrzeni nazw umożliwia niekwalifikowane użycie typów, które są elementami członkowskimi tej przestrzeni nazw. Ze względu na `using` dyrektywę program może użyć `Console.WriteLine` jako skrótu dla elementu `System.Console.WriteLine` .

`Hello`Klasa zadeklarowana przez program "Hello, World" ma jeden element członkowski, Metoda o nazwie `Main` . `Main`Metoda jest zadeklarowana z `static` modyfikatorem. Chociaż metody wystąpień mogą odwoływać się do określonego wystąpienia obiektu otaczającego za pomocą słowa kluczowego `this` , metody statyczne działają bez odwołania do określonego obiektu. Zgodnie z Konwencją metoda statyczna o nazwie `Main` służy jako punkt wejścia programu C#.

Dane wyjściowe programu są tworzone przez `WriteLine` metodę `Console` klasy w `System` przestrzeni nazw. Ta klasa jest udostępniana przez standardowe biblioteki klas, które domyślnie są przywoływane przez kompilator.

## <a name="types-and-variables"></a>Typy i zmienne

Istnieją dwa rodzaje typów w języku C#: *typy wartości* i *typy referencyjne*. Zmienne typów wartości bezpośrednio zawierają swoje dane, a zmienne typów referencyjnych przechowują odwołania do danych, które są znane jako obiekty. W przypadku typów referencyjnych istnieje możliwość, że dwie zmienne odwołują się do tego samego obiektu i możliwe dla operacji na jednej zmiennej mają wpływ na obiekt, do którego odwołuje się inna zmienna. W przypadku typów wartości zmiennych każda z nich ma własną kopię danych i nie jest możliwe wykonywanie operacji na nich, aby wpływać na drugą (z wyjątkiem `ref` `out` zmiennych i parametrów).

***Identyfikator*** jest nazwą zmiennej. Identyfikator jest sekwencją znaków Unicode bez odstępów. Identyfikator może być słowem zastrzeżonym języka C#, jeśli jest poprzedzony przez `@` . Może to być przydatne w przypadku współpracy z innymi językami.

Typy wartości języka C# są dalej podzielone na *typy proste*, *typy wyliczeniowe*, *typy struktur*i *typy wartości null*. Typy odwołań języka C# są dalej podzielone na *typy klas*, *typy interfejsów*, *Typy tablic*i *typy delegatów*.

Poniższy konspekt zawiera omówienie systemu typów języka C#.

- [Typy wartości](../language-reference/builtin-types/value-types.md)
  - [Typy proste](../language-reference/builtin-types/value-types.md#built-in-value-types)
    - [Całkowita część ze znakiem](../language-reference/builtin-types/integral-numeric-types.md): `sbyte` ,, `short` `int` , `long`
    - [Całka bez znaku](../language-reference/builtin-types/integral-numeric-types.md): `byte` ,, `ushort` `uint` , `ulong`
    - [Znaki Unicode](../../standard/base-types/character-encoding-introduction.md): `char` , które reprezentuje jednostkę kodu UTF-16
    - [Binarny zmiennoprzecinkowy IEEE](../language-reference/builtin-types/floating-point-numeric-types.md): `float` , `double`
    - [Zmiennoprzecinkowa liczba dziesiętna o dużej precyzji](../language-reference/builtin-types/floating-point-numeric-types.md): `decimal`
    - Wartość logiczna: `bool` , która reprezentuje wartości logiczne — wartości, które są `true` albo `false`
  - [Typy wyliczeniowe](../language-reference/builtin-types/enum.md)
    - Typy formularza zdefiniowane przez użytkownika `enum E {...}` . `enum`Typ jest typem odrębnym o nazwanych stałych. Każdy `enum` Typ ma typ podstawowy, który musi być jednym z ośmiu typów całkowitych. Zestaw wartości `enum` typu jest taki sam jak zestaw wartości typu podstawowego.
  - [Typy struktur](../language-reference/builtin-types/struct.md)
    - Typy formularza zdefiniowane przez użytkownika `struct S {...}`
  - [Typy wartości dopuszczające wartość null](../language-reference/builtin-types/nullable-value-types.md)
    - Rozszerzenia wszystkich innych typów wartości z `null` wartością
  - [Typy wartości krotki](../language-reference/builtin-types/value-tuples.md)
    - Typy formularza zdefiniowane przez użytkownika `(T1, T2, ...)`
- [Typy odwołań](../language-reference/keywords/reference-types.md)
  - [Typy klas](../language-reference/keywords/class.md)
    - Ostateczna Klasa bazowa dla wszystkich innych typów: `object`
    - [Ciągi Unicode](../../standard/base-types/character-encoding-introduction.md): `string` , które reprezentuje sekwencję jednostek kodu UTF-16
    - Typy formularza zdefiniowane przez użytkownika `class C {...}`
  - [Typy interfejsów](../language-reference/keywords/interface.md)
    - Typy formularza zdefiniowane przez użytkownika `interface I {...}`
  - [Typy tablic](../programming-guide/arrays/index.md)
    - Pojedyncze i wielowymiarowe i postrzępione, na przykład,, `int[]` `int[,]` i `int[][]`
  - [Typy delegatów](../language-reference/builtin-types/reference-types.md#the-delegate-type)
    - Typy formularza zdefiniowane przez użytkownika `delegate int D(...)`

Programy w języku C# używają *deklaracji typów* do tworzenia nowych typów. Deklaracja typu określa nazwę i składowe nowego typu. Pięć kategorii typów języka C# jest definiowanych przez użytkownika: typy klas, typy struktur, typy interfejsów, typy wyliczeniowe i typy delegatów.

- `class`Typ definiuje strukturę danych, która zawiera składowe danych (pola) i składowe funkcji (metody, właściwości i inne). Typy klas obsługują pojedyncze dziedziczenie i polimorfizm, czyli mechanizmy, w których klasy pochodne mogą poszerzać i specjalizację klas bazowych.
- `struct`Typ jest podobny do typu klasy w tym, że reprezentuje strukturę z składowymi danych i składowymi funkcji. Jednak w przeciwieństwie do klas, struktury są typami wartości i nie wymagają zazwyczaj alokacji sterty. Typy struktur nie obsługują dziedziczenia określonego przez użytkownika, a wszystkie typy struktur niejawnie dziedziczą po typie `object` .
- `interface`Typ definiuje kontrakt jako nazwany zestaw publicznych członków. A `class` lub `struct` implementujący `interface` musi zapewniać implementacje elementów członkowskich interfejsu. `interface`Może dziedziczyć z wielu interfejsów podstawowych, a `class` lub `struct` może zaimplementować wiele interfejsów.
- `delegate`Typ reprezentuje odwołania do metod z określoną listą parametrów i zwracanym typem. Delegaty umożliwiają traktowanie metod jako jednostek, które mogą być przypisane do zmiennych i przekazane jako parametry. Delegaty są analogiczne do typów funkcji zapewnianych przez Języki funkcjonalne. Są one również podobne do koncepcji wskaźników funkcji, które znajdują się w innych językach. W przeciwieństwie do wskaźników funkcji Delegaty są zorientowane obiektowo i są bezpieczne dla typów.

`class` `struct` `interface` Wszystkie typy,,, i są `delegate` obsługiwane przez wszystkie typy ogólne, dzięki czemu można je sparametryzowane z innymi typami.

Język C# obsługuje tablice o pojedynczym i wielowymiarowym dowolnego typu. W przeciwieństwie do typów wymienionych powyżej, typy tablicy nie muszą być zadeklarowane przed użyciem. Zamiast tego typy tablic są konstruowane przez następujące nazwy typu z nawiasami kwadratowymi. Na przykład, `int[]` jest tablicą jednowymiarową `int` , `int[,]` jest tablicą dwuwymiarową `int` , i `int[][]` jest jednowymiarową tablicą jednowymiarowej tablicy lub "nieregularna" tablicą `int` .

Typy dopuszczające wartości null nie wymagają oddzielnej definicji. Dla każdego typu, który nie dopuszcza wartości null `T` , istnieje odpowiedni typ dopuszczający wartość null, `T?` który może zawierać dodatkowe wartości `null` . Na przykład `int?` jest typem, który może zawierać dowolną 32-bitową liczbę całkowitą lub wartość `null` , i `string?` jest typem, który może zawierać dowolną `string` lub wartość `null` .

System typów języka C# jest jednorodny tak, że wartość dowolnego typu może być traktowana jako `object` . Każdy typ w języku C# bezpośrednio lub pośrednio pochodzi od `object` typu klasy i `object` jest ostateczną klasą bazową wszystkich typów. Wartości typów referencyjnych są traktowane jako obiekty, po prostu wyświetlając wartości jako typ `object` . Wartości typów wartości są traktowane jako obiekty *przez wykonywanie* *operacji pakowania*i rozpakowywania. W poniższym przykładzie `int` wartość jest konwertowana na `object` i z powrotem do `int` .

:::code language="csharp" source="./snippets/shared/Program.cs" ID="boxing" :::

Gdy wartość typu wartości jest przypisana do `object` odwołania, pole "Box" jest przydzielane do przechowywania wartości. To pole jest wystąpieniem typu odwołania, a wartość jest kopiowana do tego pola. Z drugiej strony, gdy `object` odwołanie jest rzutowane na typ wartości, jest wykonywane sprawdzenie, że odwołanie `object` jest polem o poprawnym typie wartości. Jeśli sprawdzenie zakończy się powodzeniem, wartość w polu jest kopiowana do typu wartości.

Ujednolicony system typów języka C# efektywnie oznacza, że typy wartości są traktowane jako `object` odwołania "na żądanie". Ze względu na nieujednolicenie biblioteki ogólnego przeznaczenia używające typu `object` można używać ze wszystkimi typami, które pochodzą od `object` , w tym typy odwołań i typy wartości.

W języku C# istnieje kilka rodzajów *zmiennych* , w tym pola, elementy tablicy, zmienne lokalne i parametry. Zmienne reprezentują lokalizacje magazynu. Każda zmienna ma typ, który określa, jakie wartości mogą być przechowywane w zmiennej, jak pokazano poniżej.

- Typ wartości niedopuszczający wartości null
  - Wartość tego dokładnego typu
- Typ wartości null
  - `null`Wartość lub wartość tego dokładnego typu
- object
  - `null`Odwołanie, odwołanie do obiektu dowolnego typu odwołania lub odwołanie do wartości opakowanej dowolnego typu wartości
- Typ klasy
  - `null`Odwołanie, odwołanie do wystąpienia tego typu klasy lub odwołanie do wystąpienia klasy pochodzącej od tego typu klasy
- Typ interfejsu
  - `null`Odwołanie, odwołanie do wystąpienia typu klasy implementującego ten typ interfejsu lub odwołanie do wartości opakowanej typu wartości implementującej ten typ interfejsu
- Typ tablicy
  - `null`Odwołanie, odwołanie do wystąpienia tego typu tablicy lub odwołanie do wystąpienia zgodnego typu tablicy
- Typ delegata
  - `null`Odwołanie lub odwołanie do wystąpienia zgodnego typu delegata

## <a name="program-structure"></a>Struktura programu

Kluczowe koncepcje organizacyjne w języku C# to [***programy***](../programming-guide/inside-a-program/index.md), [***przestrzenie nazw***](../programming-guide/namespaces/index.md), [***typy***](../programming-guide/types/index.md), [***elementy członkowskie***](../programming-guide/classes-and-structs/members.md)i [***zestawy***](../../standard/assembly/index.md). Programy deklarują typy, które zawierają składowe i mogą być zorganizowane w przestrzenie nazw. Klasy, struktury i interfejsy są przykładami typów. Pola, metody, właściwości i zdarzenia są przykładami elementów członkowskich. Po skompilowaniu programów C# są one fizycznie spakowane w zestawy. Zestawy zazwyczaj mają rozszerzenie pliku `.exe` lub `.dll` , w zależności od tego, czy implementują odpowiednio ***aplikacje*** lub ***biblioteki***.

Jako mały przykład rozważmy zestaw, który zawiera następujący kod:

:::code language="csharp" source="./snippets/shared/AcmeStack.cs":::

W pełni kwalifikowana nazwa tej klasy to `Acme.Collections.Stack` . Klasa zawiera kilka elementów członkowskich: pole o nazwie `top` , dwie metody o nazwie `Push` i `Pop` i zagnieżdżoną klasę o nazwie `Entry` . `Entry`Klasa dodatkowo zawiera trzy elementy członkowskie: pole o nazwie `next` , pole o nazwie `data` i Konstruktor. `Stack`Jest klasą *rodzajową* . Ma jeden parametr typu, `T` który jest zastępowany konkretnym typem, gdy jest używany.

> [!NOTE]
> *Stos* to kolekcja "First In-Last Out" (filo). Nowe elementy są dodawane na górze stosu. Po usunięciu elementu jest on usuwany z góry stosu.

Zestawy zawierają kod wykonywalny w postaci instrukcji języka pośredniego (IL) i informacji symbolicznych w formie metadanych. Przed wykonaniem, kompilator just-in-Time (JIT) środowiska uruchomieniowego języka wspólnego .NET konwertuje kod IL w zestawie na kod specyficzny dla procesora.

Ponieważ zestaw jest samoopisującą się jednostką funkcji obejmujących zarówno kod, jak i metadane, nie ma potrzeby stosowania `#include` dyrektyw i plików nagłówkowych w języku C#. Typy publiczne i składowe zawarte w określonym zestawie są udostępniane w programie C# po prostu przez odwołanie się do tego zestawu podczas kompilowania programu. Na przykład ten program używa `Acme.Collections.Stack` klasy z `acme.dll` zestawu:

:::code language="csharp" source="./snippets/shared/StackUsage.cs":::

Aby skompilować ten program, należy *odwołać* się do zestawu zawierającego klasę stosu zdefiniowaną w poprzednim przykładzie.

Programy w języku C# mogą być przechowywane w kilku plikach źródłowych. Po skompilowaniu programu w języku C# wszystkie pliki źródłowe są przetwarzane razem, a pliki źródłowe mogą swobodnie odwoływać się do siebie. Koncepcyjnie, jeśli wszystkie pliki źródłowe zostały połączone w jeden duży plik przed przetworzeniem. Deklaracje przesyłania dalej nie są nigdy konieczne w języku C#, ponieważ z kilkoma wyjątkami porządek deklaracji jest nieważny. Język C# nie ogranicza pliku źródłowego do deklarowania tylko jednego typu publicznego ani nie wymaga, aby nazwa pliku źródłowego była zgodna z typem zadeklarowanym w pliku źródłowym.

Dalsze artykuły w tym samouczku wyjaśniają te bloki organizacyjne.

>[!div class="step-by-step"]
>[Dalej](types.md)
