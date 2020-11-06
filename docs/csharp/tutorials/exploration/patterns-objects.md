---
title: Używanie wzorców w obiektach — samouczek języka C#
description: W tym samouczku przedstawiono techniki używania dopasowania wzorca w składowych klasy do tworzenia lepszych modeli dla zachowań obiektów
ms.date: 11/05/2020
ms.openlocfilehash: 072f6f57696504c2d691473e3a43c1cda53f227f
ms.sourcegitcommit: 6bef8abde346c59771a35f4f76bf037ff61c5ba3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2020
ms.locfileid: "94332192"
---
# <a name="use-pattern-matching-to-build-your-class-behavior-for-better-code"></a>Użyj dopasowania wzorca, aby utworzyć zachowanie klasy dla lepszego kodu

Funkcje dopasowania wzorców w języku C# zapewniają składnię do wyrażania algorytmów. Za pomocą tych technik można zaimplementować zachowanie w klasach. Można połączyć projekt klasy zorientowany obiektowo z implementacją zorientowaną na dane, aby zapewnić zwięzły kod podczas modelowania rzeczywistych obiektów.

Z tego samouczka dowiesz się, jak wykonywać następujące czynności:

> [!div class="checklist"]
>
> - Wyrażaj klasy zorientowane obiektowo przy użyciu wzorców danych.
> - Zaimplementuj te wzorce przy użyciu funkcji dopasowania do wzorca języka C#.
> - Aby sprawdzić poprawność implementacji, Skorzystaj z diagnostyki kompilatora.

## <a name="prerequisites"></a>Wymagania wstępne

Musisz skonfigurować maszynę do uruchamiania programu .NET 5, w tym kompilatora C# 9,0. Kompilator języka C# 9,0 jest dostępny w programie [Visual Studio 2019 w 16,8 wersji zapoznawczej](https://visualstudio.microsoft.com/vs/preview/) lub [programie .NET 5,0 SDK Preview](https://dotnet.microsoft.com/download/dotnet/5.0).

## <a name="build-a-simulation-of-a-canal-lock"></a>Tworzenie symulacji blokady kanału

W tym samouczku utworzysz klasę języka C#, która symuluje [blokadę kanału](https://en.wikipedia.org/wiki/Lock_(water_navigation)). Krótko, blokada kanału to urządzenie, które podnosi i obniża liczbę łodzi, gdy podróżują między dwoma rozciągami się wodą na różnych poziomach. Blokada ma dwie bramy i pewne mechanizmy zmiany poziomu wody.

W normalnej operacji jednostka pływająca wchodzi w skład jednej z bram, podczas gdy poziom wody w blokadzie dopasowuje poziom wody po stronie. Po zablokowaniu poziom wody zostanie zmieniony w celu dopasowania do poziomu wody, w którym łódź opuści blokadę. Po dopasowaniu poziomu wody do tej strony zostanie otwarta brama po stronie zamykania. Środki bezpieczeństwa upewnij się, że operator nie może utworzyć niebezpiecznej sytuacji w obszarze kanału. Poziom wody można zmienić tylko wtedy, gdy obie bramy są zamknięte. Można otworzyć co najwyżej jedną bramę. Aby otworzyć bramę, poziom wody w blokadzie musi pasować do poziomu wody poza otwartą bramą.

Aby modelować to zachowanie, można utworzyć klasę języka C#. `CanalLock`Klasa może obsługiwać polecenia otwierania lub zamykania jednej bramy. Inne polecenia mogą podnieść lub obniżyć wodę. Klasa powinna również obsługiwać właściwości, aby odczytać bieżący stan obu bram i poziomu wody. Metody implementują środki bezpieczeństwa.

## <a name="define-a-class"></a>Definiowanie klasy

Utworzysz aplikację konsolową w celu przetestowania `CanalLock` klasy. Utwórz nowy projekt konsoli dla platformy .NET 5 przy użyciu programu Visual Studio lub interfejsu wiersza polecenia platformy .NET. Następnie Dodaj nową klasę i nadaj jej nazwę `CanalLock` . Następnie Zaprojektuj publiczny interfejs API, ale pozostaw nie zaimplementowane metody:

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="APIDesign":::

Poprzedni kod inicjuje obiekt, aby obie bramy były zamknięte, a poziom wody jest niski. Następnie Napisz następujący kod testowy w swojej `Main` metodzie, aby poprowadzić Cię przez proces tworzenia pierwszej implementacji klasy:

:::code language="csharp" source="snippets/pattern-objects/Program.cs" ID="HappyTests":::

Następnie Dodaj pierwszą implementację każdej metody w `CanalLock` klasie. Poniższy kod implementuje metody klasy bez obaw dla reguł bezpieczeństwa. Później dodasz testy bezpieczeństwa:

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="FirstImplementation":::

Testy, które zostały przez Ciebie zrobione, zostały przekazane do tej pory. Podstawowe informacje zostały zaimplementowane. Teraz Napisz test pod kątem pierwszego warunku niepowodzenia. Na końcu poprzednich testów obie bramy są zamknięte, a poziom wody jest ustawiony na niski. Dodaj test, aby spróbować otworzyć górną bramę:

:::code language="csharp" source="snippets/pattern-objects/Program.cs" ID="HighGateSafetyTest":::

Ten test zakończy się niepowodzeniem, ponieważ Brama zostanie otwarta. Jako Pierwsza implementacja można rozwiązać ten problem przy użyciu następującego kodu:

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="SecondImplementation":::

Testy zostały zakończone pomyślnie. Ale w miarę dodawania kolejnych testów należy dodać więcej `if` klauzul i przetestować różne właściwości. Wkrótce te metody będą zbyt skomplikowane podczas dodawania większej liczby warunków.

## <a name="implement-the-commands-with-patterns"></a>Implementowanie poleceń przy użyciu wzorców

Lepszym sposobem jest użycie *wzorców* w celu ustalenia, czy obiekt jest w prawidłowym stanie do wykonania polecenia. Można podać, czy polecenie jest dozwolone jako funkcja trzech zmiennych: stanu bramy, poziomu wody i nowego ustawienia:

| Nowe ustawienie | Stan bramy | Poziom wody | Wynik             |
| ----------- | ---------- | ----------- | ------------------ |
| Zamknięty      | Zamknięty     | Wysoki        | Zamknięty             |
| Zamknięty      | Zamknięty     | Niski         | Zamknięty             |
| Zamknięty      | Otwórz       | Wysoki        | Otwórz               |
| ~~Zamknięty~~  | ~~Otwórz~~   | ~~Niski~~     | ~~Zamknięty~~         |
| Otwórz        | Zamknięty     | Wysoki        | Otwórz               |
| Otwórz        | Zamknięty     | Niski         | Zamknięte (błąd)     |
| Otwórz        | Otwórz       | Wysoki        | Otwórz               |
| ~~Otwórz~~    | ~~Otwórz~~   | ~~Niski~~     | ~~Zamknięte (błąd)~~ |

Czwarty i ostatni wiersz w tabeli ma przekreślony tekst, ponieważ są one nieprawidłowe. Dodany kod powinien mieć pewność, że brama wysokiej wody nigdy nie jest otwierana, gdy woda jest niska.  Te Stany można zakodować jako pojedyncze wyrażenie przełącznika (należy pamiętać, że `false` wskazuje "zamknięte"):

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="ThirdImplementation":::

Wypróbuj tę wersję. Testy są przekazywane, sprawdzając, czy kod. W pełnej tabeli przedstawiono możliwe kombinacje danych wejściowych i wyników. Oznacza to, że ty i inni deweloperzy mogą szybko zapoznać się z tabelą i zobaczyć, że zostały omówione wszystkie możliwe dane wejściowe. Jeszcze łatwiejsze kompilator może również pomóc. Po dodaniu poprzedniego kodu można zobaczyć, że kompilator generuje ostrzeżenie: *CS8524* wskazuje, że wyrażenie Switch nie obejmuje wszystkich możliwych danych wejściowych. Przyczyną tego ostrzeżenia jest to, że jeden z danych wejściowych jest `enum` typem. Kompilator interpretuje "wszystkie możliwe dane wejściowe" jako wszystkie dane wejściowe z typu podstawowego, zwykle jest to `int` . To `switch` wyrażenie sprawdza tylko wartości zadeklarowane w `enum` . Aby usunąć ostrzeżenie, można dodać wzorzec catch-all dla ostatniego ramienia wyrażenia. Ten warunek zgłasza wyjątek, ponieważ wskazuje nieprawidłowe dane wejściowe:

```csharp
_  => throw new InvalidOperationException("Invalid internal state"),
```

Poprzedni ARM przełącznika musi być ostatni w `switch` wyrażeniu, ponieważ dopasowuje wszystkie dane wejściowe. Eksperymentuj przez przeniesienie go wcześniej w kolejności. Powoduje błąd kompilatora *CS8510* dla nieosiągalnego kodu we wzorcu.  Naturalna struktura wyrażeń przełączników umożliwia kompilatorowi generowanie błędów i ostrzeżeń dla możliwych błędów. Kompilator "bezpieczeństwo sieci" ułatwia tworzenie poprawnego kodu w mniejszej liczbie iteracji i swobodę łączenia broni przełączania z symbolami wieloznacznymi. Kompilator będzie wystawiał błędy, jeśli Twoje połączenie powoduje nieosiągalne nieoczekiwane poręczenia, i ostrzeżenia w przypadku usunięcia wymaganej aktywacji.

Pierwsza zmiana polega na połączeniu wszystkich ramion, w których polecenie zamyka bramę; jest to zawsze dozwolone. Dodaj następujący kod jako pierwszy ARM w wyrażeniu przełącznika:

```csharp
(false, _, _) => false,
```

Po dodaniu poprzedniego ramienia aktywacji uzyskasz cztery błędy kompilatora, po jednym dla każdej z ramion, gdzie polecenie jest `false` . Te poręczenia zostały już omówione przez nowo dodaną ramię. Możesz bezpiecznie usunąć te cztery wiersze. Ten nowy przełącznik ARM zakończył te warunki.

Następnie można uprościć cztery ramiona, w których polecenie służy do otwierania bramy. W obu przypadkach, gdy poziom wody jest wysoki, bramę można otworzyć. (W jednym jest już otwarty). Jeden przypadek, w którym poziom wody jest niski zgłasza wyjątek, a drugi nie powinien wystąpić. Jeśli blokada wodna jest już w nieprawidłowym stanie, należy ją bezpiecznie zgłosić. Dla tych broni można wykonać następujące uproszczenia:

```csharp
(true, _, WaterLevel.High) => true,
(true, false, WaterLevel.Low) => throw new InvalidOperationException("Cannot open high gate when the water is low"),
_ => throw new InvalidOperationException("Invalid internal state"),
```

Uruchom ponownie testy i przekaże je. Oto Ostatnia wersja `SetHighGate` metody:

:::code language="csharp" source="snippets/pattern-objects/CanalLock.cs" ID="FinalImplementaton":::

## <a name="implement-patterns-yourself"></a>Zaimplementuj wzorce

Teraz, gdy zobaczysz technikę, Wypełnij `SetLowGate` `SetWaterLevel` metody i.  Zacznij od dodania poniższego kodu w celu przetestowania nieprawidłowych operacji na tych metodach:

:::code language="csharp" source="snippets/pattern-objects/Program.cs" ID="FinalTestCode":::

Uruchom aplikację ponownie. Można zobaczyć, że nowe testy zakończą się niepowodzeniem, a blokada kanału jest w nieprawidłowym stanie. Spróbuj samodzielnie zaimplementować pozostałe metody. Metoda ustawiania dolnej bramy powinna być podobna do metody w celu ustawienia górnej bramy. Metoda, która zmienia poziom wody, ma inne sprawdzenia, ale powinna być zgodna z podobną strukturą. Pomocne może być użycie tego samego procesu dla metody, która ustawia poziom wody. Zacznij od wszystkich czterech danych wejściowych: stanu obu bram, bieżącego stanu wody i żądanego nowego poziomu wody. Wyrażenie Switch powinno rozpoczynać się od:

```csharp
CanalLockWaterLevel = (newLevel, CanalLockWaterLevel, LowWaterGateOpen, HighWaterGateOpen) switch
{
    // elided
};
```

Masz 16 łącznych ramion do przełączania, aby wypełnić. Następnie przetestuj i Uprość.

Czy zostały wprowadzone metody podobne do tego?

:::code language="csharp" source="snippets/pattern-objects/CanalLock.cs" ID="FinalExercise":::

Testy powinny być przekazywane, a blokada kanału powinna działać bezpiecznie.

## <a name="summary"></a>Podsumowanie

W ramach tego samouczka nauczysz się użyć dopasowania wzorców do sprawdzenia stanu wewnętrznego obiektu przed zastosowaniem jakichkolwiek zmian w tym stanie. Można sprawdzić kombinacje właściwości. Po skompilowaniu tabel dla dowolnego z tych przejść Przetestuj swój kod, a następnie Uprość go pod kątem czytelności i utrzymania. Te początkowe refaktoryzacje mogą sugerować dalsze refaktoryzacje, które weryfikują stan wewnętrzny lub zarządzają zmianami interfejsu API. Ten samouczek umożliwia łączenie klas i obiektów z bardziej zorientowanymi na dane oparte na wzorcu podejściem do implementowania tych klas.
