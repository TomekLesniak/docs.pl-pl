---
title: Odrzuty — Przewodnik C#
description: Opisuje obsługę odrzutów języka C#, które są nieprzypisanymi, zmiennymi odrzuconymi i sposobami, w których można używać odrzutów.
ms.technology: csharp-fundamentals
ms.date: 09/22/2020
ms.openlocfilehash: 4de48aebaeb896b198b2e9f2431c6a38ba11469e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869327"
---
# <a name="discards---c-guide"></a>Odrzuty — Przewodnik C#

Począwszy od języka C# 7,0, C# obsługuje odrzucanie, które są tymczasowymi, fikcyjnymi zmienne, które są celowo nieużywane w kodzie aplikacji. Odrzucenia są równoważne z nieprzypisanymi zmiennymi; nie mają wartości. Ponieważ istnieje tylko jedna zmienna odrzucona, a ta zmienna nie może nawet być przydzielone magazynem, odrzucanie może zmniejszyć alokacje pamięci. Ponieważ sprawiają, że zamierzenie kodu jest jasne, zwiększa czytelność i łatwość utrzymania.

Wskazujesz, że zmienna jest odrzucana przez przypisanie do niej znaku podkreślenia ( `_` ) jako nazwy. Na przykład następujące wywołanie metody zwraca 3-krotkę, w której pierwsze i drugie wartości są odrzucane, a *obszar* jest wcześniej zadeklarowaną zmienną, która ma być ustawiona na odpowiedni trzeci składnik zwrócony przez *GetCityInformation*:

```csharp
(_, _, area) = city.GetCityInformation(cityName);
```

W języku C# 7,0 i nowszych odrzuty są obsługiwane w przypisaniach w następujących kontekstach:

- Krotka i [dekonstrukcja](deconstruct.md)obiektu.
- Zgodne ze wzorcem [parametrem](language-reference/keywords/switch.md) [is](language-reference/keywords/is.md) i switch.
- Wywołania metod z `out` parametrami.
- Autonomiczny, `_` gdy nie `_` jest w zakresie.

Począwszy od języka C# 9,0, można użyć odrzucania, aby określić nieużywane parametry wejściowe wyrażenia lambda. Aby uzyskać więcej informacji, zobacz [Parametry wejściowe sekcji wyrażenie lambda](language-reference/operators/lambda-expressions.md#input-parameters-of-a-lambda-expression) w artykule [wyrażenia lambda](language-reference/operators/lambda-expressions.md) .

Gdy `_` jest prawidłowym odrzucaniem, próba pobrania jego wartości lub użycia w operacji przypisania generuje błąd kompilatora CS0301, "nazwa" \_ "nie istnieje w bieżącym kontekście". Dzieje się tak `_` , ponieważ nie ma przypisanej wartości i może nie mieć przypisanej lokalizacji magazynu. Jeśli była to zmienna rzeczywista, nie można odrzucić więcej niż jednej wartości, jak w poprzednim przykładzie.

## <a name="tuple-and-object-deconstruction"></a>Krotka i dekonstrukcja obiektu

Odrzucenia są szczególnie przydatne podczas pracy z krotkami, gdy kod aplikacji używa niektórych elementów krotki, ale ignoruje inne. Na przykład Poniższa `QueryCityDataForYears` Metoda zwraca 6-krotkę z nazwą miasta, jego obszarem, rokiem, populacją miasta dla tego roku, drugi rok i populacją miasta dla tego drugiego roku. W przykładzie pokazano zmianę populacji między tymi dwoma latami. Danych dostępnych w spójnej kolekcji nie ma w tym obszarze miasta i wiemy, że imię i nazwisko miasto oraz dwie daty w czasie projektowania. W związku z tym interesuje tylko dwie wartości populacji przechowywane w spójnej kolekcji i mogą obsługiwać pozostałe wartości jako odrzucenia.  

[!code-csharp[Tuple-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

Aby uzyskać więcej informacji na temat dekonstrukcji krotek z odrzuconymi, zobacz [dekonstrukcja krotek i inne typy](deconstruct.md#deconstructing-tuple-elements-with-discards).

`Deconstruct`Metoda klasy, struktury lub interfejsu umożliwia również pobieranie i dekonstrukcja określonego zestawu danych z obiektu. Można użyć odrzuconych, gdy interesuje Cię pracę tylko z podzbiorem wartości, które zostały zbudowane. Poniższy przykład dekonstruuje `Person` obiekt na cztery ciągi (imię i nazwisko, miasto i stan), ale odrzuca ostatnią nazwę i stan.

[!code-csharp[Class-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/class-discard1.cs)]

Aby uzyskać więcej informacji na temat dekonstruowania typów zdefiniowanych przez użytkownika z odrzuconymi, zobacz [dekonstrukcja kroteks i innych typów](deconstruct.md#deconstructing-a-user-defined-type-with-discards).

## <a name="pattern-matching-with-switch-and-is"></a>Dopasowanie wzorców do `switch` i `is`

*Wzorca Discard* można używać w połączeniu ze wzorcem ze słowami kluczowymi [is](language-reference/keywords/is.md) i [Switch](language-reference/keywords/switch.md) . Każde wyrażenie jest zawsze zgodne ze wzorcem odrzucania.

W poniższym przykładzie zdefiniowano `ProvidesFormatInfo` metodę, która używa instrukcji [is](language-reference/keywords/is.md) , aby określić, czy obiekt dostarcza <xref:System.IFormatProvider> implementację i sprawdza, czy obiekt jest `null` . Używa również wzorca odrzucania do obsługi obiektów innych niż null dla innych typów.

[!code-csharp[discard-pattern](../../samples/snippets/csharp/programming-guide/discards/discard-pattern2.cs)]

## <a name="calls-to-methods-with-out-parameters"></a>Wywołania metod z parametrami out

Podczas wywoływania `Deconstruct` metody w celu odtworzenia typu zdefiniowanego przez użytkownika (wystąpienie klasy, struktury lub interfejsu) można odrzucić wartości poszczególnych `out` argumentów. Ale można również odrzucić wartość `out` argumentów podczas wywoływania dowolnej metody z parametrem out.

Poniższy przykład wywołuje metodę [DateTime. TryParse (String, out DateTime)](<xref:System.DateTime.TryParse(System.String,System.DateTime@)>) , aby określić, czy ciąg reprezentujący datę jest prawidłowy w bieżącej kulturze. Ponieważ przykład dotyczy tylko walidacji ciągu daty i nie jest analizowany w celu wyodrębnienia daty, `out` argument metody jest odrzucany.

[!code-csharp[discard-with-out](../../samples/snippets/csharp/programming-guide/discards/discard-out1.cs)]

## <a name="a-standalone-discard"></a>Odrzucanie autonomiczne

Możesz użyć odrzucania autonomicznego, aby wskazać dowolną zmienną, która ma być ignorowana. W poniższym przykładzie jest stosowane autonomiczne odrzucanie w celu ignorowania <xref:System.Threading.Tasks.Task> obiektu zwróconego przez operację asynchroniczną. Ma to wpływ na pominięcie wyjątku, który operacja zgłasza, gdy zostanie zakończone.

[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard1.cs)]

Należy pamiętać, że `_` jest również prawidłowym identyfikatorem. Gdy jest używana poza obsługiwanym kontekstem, `_` jest traktowana jako odrzucona, ale jako prawidłowa zmienna. Jeśli identyfikator o nazwie `_` znajduje się już w zakresie, użycie `_` jako odrzucanie autonomiczne może skutkować:

- Przypadkowe modyfikacje wartości zmiennej w zakresie `_` przez przypisanie jej wartości zamierzonego odrzucenia. Przykład:

   [!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#1)]

- Błąd kompilatora dotyczący naruszania bezpieczeństwa typów. Przykład:

   [!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#2)]

- Błąd kompilatora CS0136, "lokalny lub parametr o nazwie" \_ "nie może zostać zadeklarowany w tym zakresie, ponieważ ta nazwa jest używana w otaczającym zakresie lokalnym w celu zdefiniowania lokalnego lub parametru". Przykład:

   [!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#3)]

## <a name="see-also"></a>Zobacz też

- [Dekonstrukcja krotek i innych typów](deconstruct.md)
- [`is` kodu](language-reference/keywords/is.md)
- [`switch` kodu](language-reference/keywords/switch.md)
