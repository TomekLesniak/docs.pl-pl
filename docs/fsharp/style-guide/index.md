---
title: F# — przewodnik dotyczący stylu
description: 'Poznaj pięć zasad dobrego kodu języka F #.'
ms.date: 12/10/2018
ms.openlocfilehash: 9f47257626e04b09b546de2ae315d48d791678be
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223651"
---
# <a name="f-style-guide"></a>F# — przewodnik dotyczący stylu

W poniższych artykułach opisano wskazówki dotyczące formatowania kodu F # i wskazówki dotyczące istotna dla funkcji języka i sposobu ich używania.

Wskazówki te zostały sformułowane w oparciu o użycie języka F # w dużych bazach kodu z różnorodną grupą programistów. Te wskazówki zazwyczaj prowadzą do pomyślnego użycia języka F # i minimalizują frustrations, gdy wymagania dotyczące programów zmieniają się wraz z upływem czasu.

## <a name="five-principles-of-good-f-code"></a>Pięć zasad dobrego kodu języka F #

Należy pamiętać o każdorazowym zapisaniu kodu w języku F #, szczególnie w systemach, które zmieniają się w miarę upływu czasu. Każda część wskazówek w dalszych artykułach jest odnosząca się do tych pięciu punktów.

1. **Dobry kod języka F # to zwięzły, wyraźny i umożliwiający utworzenie**

    Język F # ma wiele funkcji, które umożliwiają wyrażanie działań w mniejszej liczbie wierszy kodu i ponowne użycie funkcji ogólnych. Biblioteka podstawowa F # zawiera również wiele przydatnych typów i funkcji służących do pracy z typowymi kolekcjami danych. Skład własnych funkcji i tych w bibliotece podstawowej F # (lub innych bibliotekach) jest częścią rutynowego programowania w języku F #. Zgodnie z ogólną zasadą, jeśli można wyrazić rozwiązanie problemu w mniejszej liczbie wierszy kodu, inni deweloperzy (lub w przyszłości) będą znaczących. Zdecydowanie zaleca się również korzystanie z biblioteki, takiej jak FSharp. Core, szerokich [bibliotek .NET](../../../api/index.md) , na których działa program F #, lub pakietu innej firmy na platformie [NuGet](https://www.nuget.org/) , gdy trzeba wykonać nieproste zadanie.

2. **Dobry kod języka F # jest interoperacyjny**

    Międzyoperacyjność może przyjmować wiele form, w tym używanie kodu w różnych językach. Granice kodu, z którymi korzystają inne obiekty wywołujące, to elementy o znaczeniu krytycznym, nawet jeśli obiekty wywołujące znajdują się również w języku F #. Podczas pisania języka F # zawsze należy zastanawiać się, jak inny kod będzie wywoływał kod, który jest pisany, w tym, jeśli to zrobi, z innego języka, takiego jak C#. [Wskazówki dotyczące projektowania składników F #](component-design-guidelines.md) opisują szczegółowo współdziałanie.

3. **Dobry kod języka F # wykorzystuje programowanie obiektów, a nie orientację obiektu.**

    Język F # ma pełną obsługę programowania z obiektami w programie .NET, w tym [klasy](../language-reference/classes.md), [interfejsy](../language-reference/interfaces.md), [Modyfikatory dostępu](../language-reference/access-control.md), [klasy abstrakcyjne](../language-reference/abstract-classes.md)i tak dalej. Aby uzyskać bardziej skomplikowany kod funkcjonalny, taki jak funkcje, które muszą być oparte na kontekście, obiekty mogą łatwo hermetyzować informacje kontekstowe w sposób, w jaki funkcje nie mogą. Funkcje takie jak [Parametry opcjonalne](../language-reference/members/methods.md#optional-arguments) i staranne użycie [przeciążenia](../language-reference/members/methods.md#overloaded-methods) mogą ułatwić wywoływanie tej funkcji.

4. **Dobry kod języka F # działa dobrze bez uwidaczniania mutacji**

    Nie jest tajny, który umożliwia zapisanie kodu o wysokiej wydajności, należy użyć mutacji. Jest to sposób, w jaki komputery działają. Taki kod jest często podatny na błędy i trudno uzyskać prawo. Unikaj ujawniania mutacji dla obiektów wywołujących. Zamiast tego należy [utworzyć interfejs funkcjonalny, który ukrywa implementację opartą na mutacji](conventions.md#performance) , gdy wydajność jest krytyczna.

5. **Dobry kod języka F # jest narzędziem**

    Narzędzia są niecenne do pracy w dużych bazach kodu, a można napisać kod języka F #, który może być bardziej efektywnie używany z narzędziami języka F #. Jednym z przykładów jest upewnienie się, że nie nadużywać go z niezależnym stylem programowania, dzięki czemu wartości pośrednie można sprawdzić za pomocą debugera. Innym przykładem jest użycie [komentarzy dokumentacji XML](../language-reference/xml-documentation.md) opisujących konstrukcje takie jak etykietki narzędzi w edytorach mogą wyświetlać te komentarze w witrynie wywołania. Zawsze Pomyśl o tym, w jaki sposób kod będzie odczytywany, przechodzenia, debugowane i manipulowany przez innych programistów przy użyciu narzędzi.

## <a name="next-steps"></a>Następne kroki

[Wskazówki dotyczące formatowania kodu w języku F #](formatting.md) zawierają wskazówki dotyczące formatowania kodu, dzięki czemu można go łatwo odczytać.

[Konwencje kodowania języka f #](conventions.md) zawierają wskazówki dotyczące idiomy programowania f #, które będą pomocne w długoterminowej konserwacji większych baz kodu języka f #.

[Wskazówki dotyczące projektowania składników języka f #](component-design-guidelines.md) zawierają wskazówki dotyczące tworzenia składników języka f #, takich jak biblioteki.
