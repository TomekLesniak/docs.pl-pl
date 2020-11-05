---
title: Samouczek dotyczący głównych obszarów języka C#
description: Jesteś nowym w języku C#? Poznaj podstawy języka.
ms.date: 08/06/2020
ms.openlocfilehash: a73399643ada05a4bfb17fadd17bf3267514e99d
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400751"
---
# <a name="major-language-areas"></a>Główne obszary języka

## <a name="arrays-collections-and-linq"></a>Tablice, kolekcje i LINQ

Języki C# i .NET udostępniają wiele różnych typów kolekcji. Tablice mają składnię zdefiniowaną przez język. Typy kolekcji ogólnych są wymienione w <xref:System.Collections.Generic?displayProperty=fullName> przestrzeni nazw. Wyspecjalizowane kolekcje obejmują <xref:System.Span%601?displayProperty=nameWithType> dostęp do ciągłej pamięci w ramce stosu oraz do <xref:System.Memory%601?displayProperty=nameWithType> uzyskiwania dostępu do ciągłej pamięci na zarządzanym stosie. Wszystkie kolekcje, w tym tablice, <xref:System.Span%601> i <xref:System.Memory%601> współdzielą zasadę ujednolicania dla iteracji. Używasz <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interfejsu. Ta zasada ujednolicenia oznacza, że wszystkie typy kolekcji mogą być używane z kwerendami LINQ lub innymi algorytmami. Metody pisania przy użyciu <xref:System.Collections.Generic.IEnumerable%601> i te algorytmy współpracują z dowolną kolekcją.

### <a name="arrays"></a>Tablice

[ * **Tablica** _](../programming-guide/arrays/index.md) to struktura danych zawierająca wiele zmiennych, do których uzyskuje się dostęp za pomocą indeksów obliczanych. Zmienne zawarte w tablicy, nazywane również _*_elementami_*_ tablicy, są tego samego typu. Ten typ jest nazywany _*_typem elementu_*_ tablicy.

Typy tablic są typami odwołań, a deklaracja zmiennej tablicowej po prostu ustawia miejsce na odwołanie do wystąpienia tablicy. Rzeczywiste wystąpienia tablicy są tworzone dynamicznie w czasie wykonywania przy użyciu `new` operatora. `new`Operacja określa _*_Długość_*_ nowego wystąpienia tablicy, które jest następnie naprawione dla okresu istnienia wystąpienia. Indeksy elementów z zakresu tablicy od `0` do `Length - 1` . `new`Operator automatycznie inicjuje elementy tablicy do ich wartości domyślnych, które na przykład są równe zero dla wszystkich typów liczbowych i `null` dla wszystkich typów odwołań.

Poniższy przykład tworzy tablicę `int` elementów, Inicjuje tablicę i drukuje zawartość tablicy.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="ArraysSample":::

Ten przykład tworzy i działa na _*_tablicy jednowymiarowej_*_. Język C# obsługuje również _*_tablice_*_ wielowymiarowe. Liczba wymiarów typu tablicy, znana również jako _*_ranga_*_ typu tablicy, jest taka, a liczba przecinkiów zapisywana między nawiasami kwadratowymi typu tablicy. Poniższy przykład przydziela odpowiednio jednowymiarowe, dwuwymiarowe i trójwymiarowe tablice.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="DeclareArrays":::

`a1`Tablica zawiera 10 elementów, `a2` tablica zawiera 50 (10 × 5) elementów, a `a3` Tablica zawiera 100 (10 × 5 x 2) elementów.
Typ elementu tablicy może być dowolnego typu, łącznie z typem tablicy. Tablica z elementami typu tablicy jest czasami nazywana _*_tablicą nieregularną_*_ , ponieważ długości tablic elementów nie wszystkie muszą być takie same. Poniższy przykład alokuje tablicę tablic `int` :

:::code language="csharp" source="./snippets/shared/Features.cs" ID="ArrayOfArrays":::

Pierwszy wiersz tworzy tablicę z trzema elementami, każdy typ `int[]` i każdy z początkową wartością `null` . Kolejne wiersze inicjują następnie trzy elementy z odwołaniami do poszczególnych wystąpień tablicy o różnej długości.

`new`Operator zezwala na określenie wartości początkowych elementów tablicy przy użyciu _*_inicjatora tablicy_*_ , który jest listą wyrażeń pisanych ogranicznikami `{` i `}` . Poniższy przykład przydziela i inicjuje `int[]` z trzema elementami.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="InitializeArray":::

Długość tablicy jest wywnioskowana na podstawie liczby wyrażeń między `{` i `}` . Inicjalizacja tablicy może być skrócona w taki sposób, aby nie trzeba było przetworzyć typu tablicy.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="InitializeShortened":::

Oba poprzednie przykłady są równoważne następującym kodzie:

:::code language="csharp" source="./snippets/shared/Features.cs" ID="InitializeGenerated":::

`foreach`Instrukcja może służyć do wyliczania elementów dowolnej kolekcji. Poniższy kod wylicza tablicę z poprzedniego przykładu:

:::code language="csharp" source="./snippets/shared/Features.cs" ID="EnumerateArray":::

`foreach`Instrukcja używa <xref:System.Collections.Generic.IEnumerable%601> interfejsu, więc może współdziałać z dowolną kolekcją.

## <a name="string-interpolation"></a>Interpolacja ciągów

[_*_Interpolacja ciągów_*_](../language-reference/tokens/interpolated.md) w języku C# umożliwia formatowanie ciągów przez definiowanie wyrażeń, których wyniki są umieszczane w ciągu formatu. Na przykład poniższy przykład drukuje temperaturę w danym dniu z zestawu danych pogody:

:::code language="csharp" source="./snippets/shared/Features.cs" ID="StringInterpolation":::

Ciąg interpolowany jest zadeklarowany przy użyciu `$` tokenu. Interpolacja ciągów oblicza wyrażenia między `{` i `}` , następnie konwertuje wynik na i `string` zastępuje tekst między nawiasami z wynikiem wyrażenia w postaci ciągu. `:`W pierwszym wyrażeniu `{weatherData.Date:MM-DD-YYYY}` określa ciąg _format *. W poprzednim przykładzie określa, że data powinna być drukowana w formacie "MM-DD-RRRR".

## <a name="pattern-matching"></a>Dopasowanie do wzorca

Język C# zawiera wyrażenia [ * **pasujące do wzorca**](../pattern-matching.md) , aby zbadać stan obiektu i wykonać kod na podstawie tego stanu. Możesz sprawdzić typy i wartości właściwości i pól, aby określić, która akcja ma zostać podjęta. `switch`Wyrażenie jest wyrażeniem podstawowym dla dopasowania wzorca.

## <a name="delegates-and-lambda-expressions"></a>Delegaty i wyrażenia lambda

[_*_Typ delegata_*_](../delegates-overview.md) reprezentuje odwołania do metod z określoną listą parametrów i zwracanym typem. Delegaty umożliwiają traktowanie metod jako jednostek, które mogą być przypisane do zmiennych i przekazane jako parametry. Delegaty są podobne do koncepcji wskaźników funkcji, które znajdują się w innych językach. W przeciwieństwie do wskaźników funkcji Delegaty są zorientowane obiektowo i są bezpieczne dla typów.

Poniższy przykład deklaruje i używa typu delegata o nazwie `Function` .

:::code language="csharp" source="./snippets/shared/Features.cs" ID="DelegateExample":::

Wystąpienie `Function` typu delegata może odwoływać się do dowolnej metody, która przyjmuje `double` argument i zwraca `double` wartość. `Apply`Metoda odnosi się `Function` do elementów a `double[]` , zwracając `double[]` wynik. `Main`Metoda `Apply` jest używana do zastosowania trzech różnych funkcji do `double[]` .

Delegat może odwoływać się do metody statycznej (takiej jak `Square` lub `Math.Sin` w poprzednim przykładzie) lub metody wystąpienia (na przykład `m.Multiply` w poprzednim przykładzie). Delegat, który odwołuje się do metody wystąpienia, odwołuje się również do określonego obiektu i gdy metoda wystąpienia jest wywoływana za pomocą delegata, ten obiekt zostaje `this` w wywołaniu.

Delegatów można także tworzyć za pomocą funkcji anonimowych, które są "metodami wbudowanymi", które są tworzone podczas deklarowania. Funkcje anonimowe mogą zobaczyć zmienne lokalne otaczających metod. Poniższy przykład nie tworzy klasy:

:::code language="csharp" source="./snippets/shared/Features.cs" ID="UseDelegate":::

Delegat nie wie ani nie dba o klasę metody, do której się odwołuje. Wszystkie te kwestie polegają na tym, że metoda przywoływana ma te same parametry i zwracany typ jako delegat.

## <a name="async--await"></a>asynchroniczne/await

Język C# obsługuje programy asynchroniczne z dwoma słowami kluczowymi: `async` i `await` . Dodaj `async` modyfikator do deklaracji metody, aby zadeklarować metodę jako asynchroniczną. `await`Operator nakazuje kompilatorowi asynchroniczne oczekiwanie na zakończenie. Formant jest zwracany do obiektu wywołującego, a metoda zwraca strukturę, która zarządza stanem pracy asynchronicznej. Struktura jest zazwyczaj <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> , ale może być dowolnego typu, który obsługuje wzorzec await. Te funkcje umożliwiają pisanie kodu, który odczytuje jako jego odpowiednik synchroniczny, ale wykonuje się asynchronicznie. Na przykład poniższy kod pobiera stronę główną witryny [Microsoft docs](/):

:::code language="csharp" source="./snippets/shared/Features.cs" ID="AsyncExample":::

Ten mały przykład pokazuje główne funkcje programowania asynchronicznego:

- Deklaracja metody zawiera `async` modyfikator.
- Treść metody `await` s zwraca `GetByteArrayAsync` metodę.
- Typ określony w instrukcji jest `return` zgodny z argumentem typu w `Task<T>` deklaracji metody. (Metoda zwracająca `Task` instrukcję USE instrukcji, która `return` nie ma żadnego argumentu).

## <a name="attributes"></a>Atrybuty

Typy, elementy członkowskie i inne jednostki w programie C# obsługują Modyfikatory kontrolujące pewne aspekty ich zachowania. Na przykład dostępność metody jest kontrolowana za pomocą `public` `protected` `internal` modyfikatorów,, i `private` . Język C# służy do uogólniania tej funkcji w taki sposób, że typy informacji deklaratywnych zdefiniowanych przez użytkownika mogą być dołączane do jednostek programu i pobierane w czasie wykonywania. Programy określają te dodatkowe informacje deklaracyjne przez definiowanie i używanie [*_atrybutów_* * _](../programming-guide/concepts/attributes/index.md).

Poniższy przykład deklaruje `HelpAttribute` atrybut, który może być umieszczony w jednostkach programu, aby udostępnić linki do powiązanej dokumentacji.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="DefineAttribute":::

Wszystkie klasy atrybutów pochodzą z <xref:System.Attribute> klasy podstawowej dostarczonej przez bibliotekę .NET. Atrybuty mogą być stosowane, dając ich nazwę, wraz z dowolnymi argumentami, wewnątrz nawiasów kwadratowych tuż przed skojarzoną deklaracją. Jeśli nazwa atrybutu `Attribute` zostanie zakończona, ta część nazwy może zostać pominięta, gdy występuje odwołanie do atrybutu. Na przykład `HelpAttribute` może być użyta w następujący sposób.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="UseAttributes":::

Ten przykład dołącza `HelpAttribute` do `Widget` klasy. Dodaje kolejną `HelpAttribute` do `Display` metody w klasie. Publiczne konstruktory klasy atrybutów kontrolują informacje, które muszą być dostarczone, gdy atrybut jest dołączony do jednostki programu. Dodatkowe informacje można uzyskać, odwołując się do właściwości publicznego odczytu i zapisu klasy atrybutów (takich jak odwołanie do `Topic` Właściwości wcześniej).

Metadane zdefiniowane przez atrybuty mogą być odczytywane i manipulowane w czasie wykonywania przy użyciu odbicia. Gdy określony atrybut jest żądany przy użyciu tej techniki, Konstruktor klasy atrybutu jest wywoływany z informacjami podanymi w źródle programu i zwracane jest wystąpienie atrybutu wynikowego. Jeśli dodatkowe informacje zostały przekazane za pomocą właściwości, te właściwości są ustawiane na podane wartości przed zwróceniem wystąpienia atrybutu.

Poniższy przykład kodu demonstruje, jak uzyskać `HelpAttribute` wystąpienia skojarzone z `Widget` klasą i jej `Display` metodzie.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="ReadAttributes":::

## <a name="learn-more"></a>Więcej tutaj

Więcej informacji na temat języka C# można uzyskać, próbując skorzystać z jednego z naszych [samouczków](../tutorials/index.md).

>[!div class="step-by-step"]
>[Poprzednie](program-building-blocks.md)
