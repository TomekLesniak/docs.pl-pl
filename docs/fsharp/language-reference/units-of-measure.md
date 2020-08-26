---
title: Jednostki miary
description: 'Dowiedz się, w jaki sposób zmiennoprzecinkowe i podpisane wartości całkowite w F # mogą mieć skojarzone jednostki miary, które zwykle są używane do wskazywania długości, ilości i masy.'
ms.date: 08/15/2020
ms.openlocfilehash: 0262f89e80697dd86161c93fe37381122972b56f
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811577"
---
# <a name="units-of-measure"></a>Jednostki miary

Wartości zmiennoprzecinkowe i ze znakami całkowitymi w F # mogą mieć skojarzone jednostki miary, które zwykle są używane do wskazywania długości, objętości, masy itd. Korzystając z ilości w jednostkach, należy włączyć kompilator, aby sprawdzić, czy relacje arytmetyczne mają poprawne jednostki, co pomaga zapobiegać błędom programowania.

## <a name="syntax"></a>Składnia

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a>Uwagi

Poprzednia składnia definiuje *nazwę jednostki* jako jednostkę miary. Opcjonalna część służy do definiowania nowej miary w warunkach wcześniej zdefiniowanych jednostek. Na przykład poniższy wiersz definiuje miarę `cm` (centymetr).

```fsharp
[<Measure>] type cm
```

Poniższy wiersz definiuje miarę `ml` (milliliter) jako centymetr sześcienny ( `cm^3` ).

```fsharp
[<Measure>] type ml = cm^3
```

W poprzedniej składni *miary* jest formułą, która obejmuje jednostki. W formułach obejmujących jednostki, obsługiwane są uprawnienia całek (dodatnie i ujemne), spacje między jednostkami wskazują iloczyn dwóch jednostek, `*` wskazuje również iloczyn jednostek i `/` wskazuje iloraz jednostek. W przypadku jednostki wzajemnej można użyć ujemnej potęgi całkowitej lub `/` , która wskazuje oddzielenie między licznikiem i mianownikiem formuły jednostkowej. Wiele jednostek w mianowniku należy ująć w nawiasy. Jednostki rozdzielone spacjami po `/` wartości są interpretowane jako część mianownika, ale wszystkie jednostki po `*` są interpretowane jako część licznika.

Możesz użyć 1 w wyrażeniach jednostkowych, aby wskazać ilość bez wymiaru lub łącznie z innymi jednostkami, takimi jak w liczniku. Na przykład jednostki dla stawki byłyby zapisywane jako `1/s` , gdzie `s` wskazuje sekundy. Nawiasy nie są używane w formułach jednostkowych. Nie określono liczbowych stałych konwersji w formułach jednostkowych; można jednak definiować stałe konwersji z jednostkami oddzielnie i używać ich w obliczeniach sprawdzanych przez jednostkę.

Formuły jednostkowe, które oznaczają te same czynności, można napisać na różne sposoby. W związku z tym kompilator konwertuje formuły jednostkowe na spójną postać, która konwertuje negatywne uprawnienia do reciprocals, grupuje jednostki w pojedynczy licznik i mianownik, a alphabetizes jednostki w liczniku i mianowniku.

Na przykład formuły jednostkowe `kg m s^-2` i `m /s s * kg` są konwertowane na `kg m/s^2` .

W wyrażeniach zmiennoprzecinkowych są używane jednostki miary. Użycie liczb zmiennoprzecinkowych razem ze skojarzonymi jednostkami miary dodaje inny poziom bezpieczeństwa typów i pomaga uniknąć błędów niezgodności jednostek, które mogą wystąpić w formułach w przypadku używania słabo wpisanych liczb zmiennoprzecinkowych. Jeśli piszesz wyrażenie zmiennoprzecinkowe używające jednostek, jednostki w wyrażeniu muszą być zgodne.

Można dodać adnotacje do literałów z formułą jednostkową w nawiasach kątowych, jak pokazano w poniższych przykładach.

```fsharp
1.0<cm>
55.0<miles/hour>
```

Nie umieszczasz spacji między liczbą i nawiasem ostrym; można jednak dołączyć sufiks literału, taki jak `f` w poniższym przykładzie.

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

Taka adnotacja zmienia typ literału z jego typu pierwotnego (na przykład `float` ) na typ wymiarowy, taki jak `float<cm>` lub, w tym przypadku `float<miles/hour>` . Adnotacja jednostki `<1>` wskazuje ilość bez wymiaru, a jej typ jest równoważny z typem pierwotnym bez parametru jednostki.

Typ jednostki miary jest zmiennoprzecinkowym lub podpisanym typem całkowitym wraz z dodatkową adnotacją jednostki, wskazanym w nawiasach. W ten sposób podczas pisania typu konwersji z `g` (gramów) do `kg` (kilogramów) należy opisać typy w następujący sposób.

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

Jednostki miary są używane do sprawdzania jednostek czasu kompilacji, ale nie są utrwalane w środowisku wykonawczym. W związku z tym nie wpływają one na wydajność.

Jednostki miary można zastosować do dowolnego typu, a nie tylko typów zmiennoprzecinkowych; jednak tylko typy zmiennoprzecinkowe, podpisane typy całkowite i typy dziesiętne obsługują wielkości zwymiarowane. W związku z tym warto używać tylko jednostek miary w typach pierwotnych i w agregacjach, które zawierają te typy pierwotne.

Poniższy przykład ilustruje użycie jednostek miary.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

Poniższy przykład kodu ilustruje sposób konwersji z liczby zmiennoprzecinkowej bezwymiarowej na zwymiarowaną wartość zmiennoprzecinkową. Przemnożono o 1,0, stosując wymiary do 1,0. Można go abstrakcyjnić do funkcji, takiej jak `degreesFahrenheit` .

Ponadto, gdy wartości wymiarów są przekazywane do funkcji, które oczekują liczb zmiennoprzecinkowych bezwymiarowych, należy anulować jednostki lub rzutować do `float` przy użyciu `float` operatora. W tym przykładzie dzieli się przez `1.0<degC>` argumenty z, `printf` ponieważ `printf` oczekuje to ilości bez wymiaru.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

Poniższa przykładowa sesja pokazuje dane wyjściowe z i wejścia do tego kodu.

```console
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a>Korzystanie z jednostek generycznych

Można napisać funkcje ogólne, które działają na danych ze skojarzoną jednostką miary. W tym celu należy określić typ razem z jednostką ogólną jako parametr typu, jak pokazano w poniższym przykładzie kodu.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a>Tworzenie typów zagregowanych z jednostkami ogólnymi

Poniższy kod pokazuje, jak utworzyć typ zagregowany składający się z pojedynczych wartości zmiennoprzecinkowych, które mają jednostki, które są ogólne. Dzięki temu można utworzyć pojedynczy typ, który działa z różnymi jednostkami. Ponadto jednostki ogólne zachowują bezpieczeństwo typu przez zapewnienie, że typ ogólny, który ma jeden zestaw jednostek, jest innego typu niż ten sam typ ogólny z innym zestawem jednostek. Podstawą tej metody jest to, że `Measure` atrybut może być stosowany do parametru typu.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a>Jednostki w czasie wykonywania

Jednostki miary są używane do sprawdzania typu statycznego. Gdy wartości zmiennoprzecinkowe są kompilowane, jednostki miary są eliminowane, więc jednostki zostaną utracone w czasie wykonywania. W związku z tym każda próba zaimplementowania funkcji, która zależy od sprawdzania jednostek w czasie wykonywania, nie jest możliwa. Na przykład zaimplementowanie `ToString` funkcji do drukowania jednostek nie jest możliwe.

## <a name="conversions"></a>Konwersje

Aby skonwertować typ, który ma jednostki (na przykład `float<'u>` ) na typ, który nie ma jednostek, można użyć standardowej funkcji konwersji. Na przykład można użyć `float` do konwersji na `float` wartość, która nie ma jednostek, jak pokazano w poniższym kodzie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

Aby skonwertować wartość bezjednostkową na wartość, która ma jednostki, można pomnożyć wartość 1 lub 1,0, która ma adnotację z odpowiednimi jednostkami. Jednak w przypadku pisania warstw współdziałania dostępne są również pewne jawne funkcje, których można użyć do konwersji wartości bezjednostkowych na wartości w jednostkach. Znajdują się one w module [FSharp. Core. LanguagePrimitives](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html) . Na przykład aby przeprowadzić konwersję z bezjednostkowego `float` na a `float<cm>` , użyj [FloatWithMeasure —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html#FloatWithMeasure), jak pokazano w poniższym kodzie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a>Jednostki miary w podstawowej bibliotece języka F #

Biblioteka jednostek jest dostępna w `FSharp.Data.UnitSystems.SI` przestrzeni nazw. Zawiera jednostki SI w obu ich symbolach (na przykład `m` dla miernika) w `UnitSymbols` przestrzeni nazw, a ich pełna nazwa (na przykład `meter` dla miernika) w `UnitNames` przestrzeni nazw.

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka F #](index.md)
