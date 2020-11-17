---
title: Korzystanie z typów rekordów — samouczek języka C#
description: Dowiedz się, jak używać typów rekordów, tworzyć hierarchie rekordów i Kiedy wybierać rekordy dla klas.
ms.date: 11/12/2020
ms.openlocfilehash: 8a2cb6966ab4f93432723fd6f82618efa86b26aa
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688588"
---
# <a name="create-record-types"></a>Tworzenie typów rekordów

W języku C# 9 wprowadzono *rekordy*, nowy typ referencyjny, który można utworzyć zamiast klas lub struktur. Rekordy różnią się od klas w tych typach rekordów, które używają *równości względem wartości*. Dwie zmienne typu rekordu są równe, jeśli definicje typu rekordu są identyczne, a jeśli dla każdego pola, wartości w obu rekordach są równe. Dwie zmienne typu klasy są równe, jeśli obiekty określone jako są tego samego typu, a zmienne odwołują się do tego samego obiektu. Równość oparta na wartości oznacza inne możliwości, które prawdopodobnie będą potrzebne w typach rekordów. Kompilator generuje wiele z tych członków, gdy deklarujesz `record` zamiast `class` .

Z tego samouczka dowiesz się, jak wykonywać następujące czynności:

> [!div class="checklist"]
>
> - Zdecyduj, czy należy zadeklarować element `class` lub `record` .
> - Zadeklaruj typy rekordów i typy rekordów pozycyjnych.
> - Podstaw metody dla metod generowanych przez kompilator w rekordach.

## <a name="prerequisites"></a>Wymagania wstępne

Musisz skonfigurować maszynę do uruchamiania programu .NET 5 lub nowszego, w tym kompilatora C# 9,0 lub nowszego. Kompilator języka C# 9,0 jest dostępny począwszy od [programu Visual Studio 2019 w wersji 16,8](https://visualstudio.microsoft.com/vs) lub [zestawu .NET 5,0 SDK](https://dotnet.microsoft.com/download).

## <a name="characteristics-of-records"></a>Charakterystyki rekordów

*Rekord* można zdefiniować przez zadeklarowanie typu za pomocą `record` słowa kluczowego, zamiast `class` `struct` słowa kluczowego or. Rekord a to typ referencyjny, który jest zgodny z semantyką równości opartą na wartości. Aby wymusić semantykę wartości, kompilator generuje kilka metod dla typu rekordu:

- Zastąpienie elementu <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> .
- Metoda wirtualna `Equals` , której parametr jest typem rekordu.
- Zastąpienie elementu <xref:System.Object.GetHashCode?displayProperty=nameWithType> .
- Metody dla `operator ==` i `operator !=` .
- Implementacja typów rekordów <xref:System.IEquatable%601?displayProperty=nameWithType> .

Ponadto rekordy zapewniają przesłonięcie <xref:System.Object.ToString?displayProperty=nameWithType> . Kompilator służy do syntezowania metod wyświetlania rekordów przy użyciu <xref:System.Object.ToString?displayProperty=nameWithType> . Poznasz te elementy w trakcie pisania kodu dla tego samouczka. Rejestruje `with` wyrażenia obsługi, aby umożliwić nieniszczącą mutację rekordów.

*Rekordy pozycyjne* można także deklarować przy użyciu bardziej zwięzłej składni. Kompilator pozwala uzyskać więcej metod przy deklarowaniu rekordów pozycyjnych:

- Podstawowy Konstruktor, którego parametry pasują do parametrów pozycyjnych w deklaracji rekordu.
- Publiczne właściwości tylko do inicjacji dla każdego parametru konstruktora podstawowego.
- `Deconstruct`Metoda wyodrębniania właściwości z rekordu.

## <a name="build-temperature-data"></a>Kompiluj dane temperatury

Dane i statystyki są między scenariuszami, w których chcesz używać rekordów. W tym samouczku utworzysz aplikację, która obliczy zakres *dni* dla różnych zastosowań. *Stopień dni* to miara ciepła (lub braku ciepła) w okresie dni, tygodni lub miesięcy. Zakres dni śledzenia i przewidywania zużycia energii. Więcej hotter dni oznacza więcej warunków użytkowania powietrza, a większa liczba dni w chłodni oznacza więcej użycia pieca. Zakres dni ułatwia zarządzanie populacją zakładu. Zakres dni jest skorelowany do wzrostu zakładu w miarę zmiany sezonów. Stopień dni ułatwia śledzenie migracji zwierząt dla gatunków, które podróżują w celu dopasowania klimatu.

Formuła jest zależna od średniej temperatury w danym dniu i temperatury linii bazowej. Aby obliczyć zakres dni w czasie, w danym okresie będzie potrzebna najwyższa i niska temperatura. Zacznijmy od utworzenia nowej aplikacji. Utwórz nową aplikację konsolową. Utwórz nowy typ rekordu w nowym pliku o nazwie "DailyTemperature.cs":

:::code language="csharp" source="snippets/record-types/InterimSteps.cs" ID="DailyRecord":::

Poprzedni kod definiuje *rekord pozycyjny*. Utworzono typ referencyjny, który zawiera dwie właściwości: `HighTemp` , i `LowTemp` . Właściwości te są *jedynymi właściwościami inicjującymi*, co oznacza, że można je ustawić w konstruktorze lub przy użyciu inicjatora właściwości. `DailyTemperature`Typ ma także *podstawowy Konstruktor* , który ma dwa parametry, które pasują do dwóch właściwości. Użyj konstruktora podstawowego do zainicjowania `DailyTemperature` rekordu:

:::code language="csharp" source="snippets/record-types/Program.cs" ID="DeclareData":::

Możesz dodać własne właściwości lub metody do rekordów, w tym rekordy pozycyjne. Należy obliczyć średnią temperaturę dla każdego dnia. Możesz dodać tę właściwość do `DailyTemperature` rekordu:

:::code language="csharp" source="snippets/record-types/DailyTemperature.cs" ID="TemperatureRecord":::

Upewnij się, że możesz użyć tych danych. Dodaj następujący kod do `Main` metody:

```csharp
foreach (var item in data)
    Console.WriteLine(item);
```

Uruchom aplikację i zobaczysz dane wyjściowe podobne do następującego ekranu (kilka wierszy usuniętych dla obszaru):

```dotnetcli
DailyTemperature { HighTemp = 57, LowTemp = 30, Mean = 43.5 }
DailyTemperature { HighTemp = 60, LowTemp = 35, Mean = 47.5 }


DailyTemperature { HighTemp = 80, LowTemp = 60, Mean = 70 }
DailyTemperature { HighTemp = 85, LowTemp = 66, Mean = 75.5 }
```

Powyższy kod przedstawia dane wyjściowe z przesłonięcia, które zostały przesłonięte `ToString` przez kompilator. Jeśli wolisz inny tekst, możesz napisać własną wersję programu `ToString` . Uniemożliwia to kompilatorowi wyszukanie wersji.

## <a name="compute-degree-days"></a>Liczba dni obliczeniowych

Aby obliczyć liczbę dni, należy wziąć pod nich różnicę z temperatury linii bazowej i średniej temperatury danego dnia. Aby zmierzyć ciepło w czasie, odrzucasz dni, w których średnia temperatura jest poniżej linii bazowej. Aby zmierzyć zimny czas, odrzucaj dni, w których średnia temperatura jest wyższa od linii bazowej. Na przykład stan USA używa 65F jako podstawy dla obu dni ogrzewania i chłodzenia. Jest to temperatura, w której nie jest wymagana ogrzewanie ani chłodzenie. Jeśli dzień ma średnią temperaturę 70F, ten dzień to 5 dni w poziomie chłodzenia i 0 stopni ogrzewania. Z drugiej strony, jeśli średnia temperatura to 55F, ten dzień wynosi 10 dni w poziomie ogrzewania i 0 stopni chłodzenia.

Te formuły można wyrazić jako małą hierarchię typów rekordów: abstrakcyjny typ dnia i dwa typy konkretnego poziomu ogrzewania dla dni i stopnia chłodzenia. Te typy mogą również zawierać rekordy pozycyjne. Przyjmują one temperaturę bazową i sekwencję dziennych rekordów temperatury jako argumenty konstruktora podstawowego:

:::code language="csharp" source="snippets/record-types/InterimSteps.cs" ID="DegreeDaysRecords":::

Rekord abstrakcyjny `DegreeDays` jest współdzieloną klasą bazową dla `HeatingDegreeDays` `CoolingDegreeDays` rekordów i. Deklaracje konstruktora podstawowego dotyczące rekordów pochodnych pokazują, jak zarządzać inicjalizacją rekordu podstawowego. Rekord pochodny deklaruje parametry dla wszystkich parametrów w podstawowym konstruktorze bazowym rekordów. Rekord podstawowy deklaruje i inicjuje te właściwości. Rekord pochodny nie jest ukrywany, ale tylko tworzy i inicjuje właściwości dla parametrów, które nie są zadeklarowane w rekordzie podstawowym. W tym przykładzie rekordy pochodne nie dodają nowych parametrów konstruktora podstawowego. Przetestuj swój kod, dodając następujący kod do `Main` metody:

:::code language="csharp" source="snippets/record-types/Program.cs" ID="HeatingAndCooling":::

Zostaną wyświetlone dane wyjściowe podobne do następujących:

```dotnetcli
HeatingDegreeDays { BaseTemperature = 65, TempRecords = record_types.DailyTemperature[], DegreeDays = 85 }
CoolingDegreeDays { BaseTemperature = 65, TempRecords = record_types.DailyTemperature[], DegreeDays = 71.5 }
```

## <a name="define-compiler-synthesized-methods"></a>Definiowanie metod z syntezą kompilatora

Kod oblicza poprawną liczbę dni ogrzewania i chłodzenia w tym okresie. Ale w tym przykładzie pokazano, dlaczego warto zastąpić niektóre metody z syntezą dla rekordów. Można zadeklarować własną wersję dowolnego z metod, które zostały wykorzystane przez kompilator w typie rekordu, z wyjątkiem metody klonowania. Metoda klonowania ma nazwę wygenerowaną przez kompilator i nie można podać innej implementacji. Te metody z syntezą obejmują Konstruktor kopiujący, elementy członkowskie <xref:System.IEquatable%601?displayProperty=nameWithType> interfejsu, testy równości i nierówności oraz <xref:System.Object.GetHashCode> . W tym celu będziesz je wyszukiwać `PrintMembers` . Można również zadeklarować własne `ToString` , ale `PrintMembers` zapewnia lepszą opcję dla scenariuszy dziedziczenia. Aby zapewnić własną wersję metody z syntezą, sygnatura musi być zgodna z metodą z syntezą.

`TempRecords`Element w danych wyjściowych konsoli nie jest przydatny. Wyświetla typ, ale nic innego. Możesz zmienić to zachowanie, dostarczając własną implementację metody z syntezą `PrintMembers` . Podpis zależy od modyfikatorów stosowanych do `record` deklaracji:

- Jeśli typ rekordu to `sealed` , podpis jest `private bool PrintMembers(StringBuilder builder);`
- Jeśli typ rekordu nie jest `sealed` i pochodzi od `object` (oznacza to, że nie deklaruje rekordu bazowego), podpis jest `protected virtual bool PrintMembers(StringBuilder builder);`
- Jeśli typ rekordu nie jest `sealed` i pochodzi od innego rekordu, podpis jest `protected override bool PrintMembers(StringBuilder builder);`

Te reguły są najłatwiej comprehend przez zrozumienie celu `PrintMembers` . `PrintMembers` dodaje informacje o każdej właściwości w typie rekordu do ciągu. Kontrakt wymaga rekordów bazowych, aby dodać ich członków do ekranu i przyjęto, że pochodni członkowie doda ich członków. Każdy typ rekordu `ToString` określa przesłonięcie, który wygląda podobnie do następującego przykładu `HeatingDegreeDays` :

```csharp
public override string ToString()
{
    StringBuilder stringBuilder = new StringBuilder();
    stringBuilder.Append("HeatingDegreeDays");
    stringBuilder.Append(" { ");
    if (PrintMembers(stringBuilder))
    {
        stringBuilder.Append(" ");
    }
    stringBuilder.Append("}");
    return stringBuilder.ToString();
}
```

Należy zadeklarować `PrintMembers` metodę w `DegreeDays` rekordzie, który nie drukuje typu kolekcji:

:::code language="csharp" source="snippets/record-types/DegreeDays.cs" ID="AddPrintMembers":::

Podpis deklaruje `virtual protected` metodę zgodną z wersją kompilatora. Nie martw się, Jeśli otrzymujesz odpowiednie metody dostępu; Język wymusza poprawność podpisu. Jeśli zapomnisz o poprawnym modyfikatorze dla dowolnej metody z syntezą, kompilator wygeneruje ostrzeżenia lub błędy, które pomogą Ci uzyskać właściwy podpis.

## <a name="non-destructive-mutation"></a>Mutacja nieniszcząca

Syntezy w rekordach pozycyjnych nie modyfikują stanu rekordu. Celem jest możliwość łatwiejszego tworzenia niezmiennych rekordów. Zapoznaj się ponownie z powyższymi deklaracjami dla `HeatingDegreeDays` i `CoolingDegreeDays` . Dodane elementy członkowskie wykonują obliczenia na wartościach rekordu, ale nie są zmieniane. Rekordy pozycyjne ułatwiają tworzenie niemodyfikowalnych typów referencyjnych.

Tworzenie niemodyfikowalnych typów referencyjnych oznacza, że chcesz użyć mutacji nieniszczącej. Tworzysz nowe wystąpienia rekordów podobne do istniejących wystąpień rekordów przy użyciu [ `with` wyrażeń](../../language-reference/operators/with-expression.md). Te wyrażenia są kopią kopii z dodatkowymi przypisaniami, które modyfikują kopię. Wynik jest nowym wystąpieniem rekordu, w którym każda właściwość została skopiowana z istniejącego rekordu i opcjonalnie zmodyfikowana. Oryginalny rekord nie został zmieniony.

Dodajmy do programu kilka funkcji, które demonstrują `with` wyrażenia. Najpierw utwórz nowy rekord, aby obliczyć rosnący wzrost dni przy użyciu tych samych danych. *Coraz* większy zakres dni zwykle używa 41F jako linii bazowej i mierzy temperaturę ponad linię bazową. Aby użyć tych samych danych, można utworzyć nowy rekord podobny do `coolingDegreeDays` , ale z inną temperaturą bazową:

:::code language="csharp" source="snippets/record-types/Program.cs" ID="GrowingDegreeDays":::

Można porównać liczbę stopni obliczanych z wartościami wygenerowanymi przez wyższą temperaturę linii bazowej. Należy pamiętać, że rekordy są *typami odwołań* , a te kopie to płytki kopie. Tablica danych nie jest kopiowana, ale oba rekordy odwołują się do tych samych danych. Jest to korzyść w jednym innym scenariuszu. W przypadku rosnących dni warto śledzić łączną wartość w ciągu ostatnich 5 dni. Można tworzyć nowe rekordy z różnymi danymi źródłowymi przy użyciu `with` wyrażeń. Poniższy kod tworzy kolekcję tych kumulacji, a następnie wyświetla wartości:

:::code language="csharp" source="snippets/record-types/Program.cs" ID="RunningFiveDayTotal":::

Możesz również użyć `with` wyrażeń do tworzenia kopii rekordów. Nie określaj żadnych właściwości między nawiasami klamrowymi `with` wyrażenia. Oznacza to utworzenie kopii i nie zmienia żadnych właściwości:

```csharp
var growingDegreeDaysCopy = growingDegreeDays with { };
```

Uruchom ukończoną aplikację, aby wyświetlić wyniki.

## <a name="summary"></a>Podsumowanie

W tym samouczku pokazano kilka aspektów rekordów. Rekordy zapewniają zwięzłą składnię dla typów referencyjnych, w których podstawowe użycie zapisuje dane. W przypadku klas zorientowanych obiektowo, podstawowe użycie polega na definiowaniu obowiązków. Ten samouczek koncentruje się na *rekordach pozycyjnych*, gdzie można użyć zwięzłej składni do deklarowania właściwości tylko do inicjacji dla rekordu. Kompilator umożliwia wyszukanie kilku elementów członkowskich rekordu do kopiowania i porównywania rekordów. Możesz dodać innych członków potrzebnych dla typów rekordów. Można tworzyć niezmienne typy rekordów, wiedząc, że żaden z elementów członkowskich generowanych przez kompilator nie będzie mógł zmodyfikować stanu. W przypadku rekordów pozycyjnych `with` wyrażenia ułatwiają obsługę mutacji nieniszczącej.

Rekordy dodają inny sposób definiowania typów. Za pomocą `class` definicji można tworzyć hierarchie zorientowane obiektowo, które koncentrują się na odpowiedzialności i zachowaniu obiektów. Tworzysz `struct` typy struktur danych, które przechowują dane i są wystarczająco małe, aby można je było wydajnie kopiować. Rekordy są tworzone, gdy chcesz, aby dane były zgodne i porównywane, nie chcesz kopiować wartości i chcieć używać zmiennych referencyjnych.

Aby poznać pełny opis rekordów, należy odczytać [proponowaną specyfikację typu rekordu](~/_csharplang/proposals/csharp-9.0/records.md).
