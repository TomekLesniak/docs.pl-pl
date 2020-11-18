---
title: System typu wspólnego i specyfikacja języka wspólnego
description: Dowiedz się, jak wspólny system typów (CTS) i Common Language Specification (CLS) umożliwiają platformie .NET obsługę wielu języków.
ms.date: 06/20/2016
ms.assetid: 3b1f5725-ac94-4f17-8e5f-244442438a4d
ms.openlocfilehash: e60205450e2f156407deb7be6b9c497d090b6f7b
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822883"
---
# <a name="common-type-system--common-language-specification"></a>System typu wspólnego i specyfikacja języka wspólnego

Ponownie, dwa warunki, które są swobodnie używane w środowisku .NET World, rzeczywiście są kluczowe, aby zrozumieć, w jaki sposób implementacja platformy .NET umożliwia programowanie wielu języków i zrozumienie, jak to działa.

## <a name="common-type-system"></a>System typu wspólnego

Aby zacząć od początku, pamiętaj, że implementacja platformy .NET to _Language niezależny od_. Nie oznacza to jedynie, że programista może napisać swój kod w dowolnym języku, który można skompilować do IL. Oznacza to również, że muszą mieć możliwość korzystania z kodu pisanego w innych językach, które mogą być używane w implementacji platformy .NET.

Aby to zrobić w sposób przezroczysty, musi istnieć typowy sposób opisywania wszystkich obsługiwanych typów. Jest to opłata za usługę Common Type System (CTS). Wprowadzono kilka rzeczy:

* Ustanów strukturę wykonywania wielu języków.
* Podaj model zorientowany obiektowo do obsługi implementacji różnych języków w implementacji platformy .NET.
* Zdefiniuj zestaw reguł, które muszą spełniać wszystkie języki, gdy chodzi o pracę z typami.
* Udostępnianie biblioteki zawierającej podstawowe typy pierwotne, które są używane podczas opracowywania aplikacji (np `Boolean` ., `Byte` `Char` itp.)

CTS definiuje dwa główne rodzaje typów, które powinny być obsługiwane: odwołania i typy wartości. Ich nazwy wskazują ich definicje.

Typy odwołań "obiekty są reprezentowane przez odwołanie do rzeczywistej wartości obiektu; odwołanie jest podobne do wskaźnika w C/C++. Odnosi się po prostu do lokalizacji pamięci, w której znajdują się wartości obiektów. Ma to głęboki wpływ na to, jak te typy są używane. Jeśli przypiszesz do zmiennej typ referencyjny, a następnie przekażesz tę zmienną do metody, na przykład wszelkie zmiany w obiekcie zostaną odzwierciedlone w obiekcie głównym; nie ma kopiowania.

Typy wartości są przeciwieństwem, gdzie obiekty są reprezentowane przez ich wartości. Jeśli przypiszesz typ wartości do zmiennej, zasadniczo kopiujesz wartość obiektu.

CTS definiuje kilka kategorii typów, z których każda ma określoną semantykę i użycie:

* Klasy
* Struktury
* Wyliczenia
* Interfejsy
* Delegaty

CTS definiuje także wszystkie inne właściwości typów, takie jak Modyfikatory dostępu, jakie są prawidłowe elementy członkowskie typu, jak działa dziedziczenie i Przeciążenie. Niestety, przechodzenie do któregokolwiek z tych elementów wykracza poza zakres artykułu wprowadzającego, takiego jak ten, ale możesz zapoznać się z sekcją [więcej zasobów](#more-resources) na końcu, aby uzyskać linki do bardziej szczegółowej zawartości, która obejmuje te tematy.

## <a name="common-language-specification"></a>Specyfikacja języka wspólnego

Aby włączyć pełne scenariusze współdziałania, wszystkie obiekty, które są tworzone w kodzie, muszą opierać się na pewnych wspólnie w językach, które je zużywają (są ich _wywołującymi_). Ponieważ istnieje wiele różnych języków, środowisko .NET określiło te commonalities w elemencie **Common Language Specification** o nazwie (CLS). CLS definiuje zestaw funkcji, które są zbędne przez wiele typowych aplikacji. Zawiera również opis przepisu dla dowolnego języka, który jest implementowany w oparciu o platformę .NET na potrzeby obsługi.

CLS jest podzbiorem CTS. Oznacza to, że wszystkie reguły w CTS stosują się również do specyfikacji CLS, chyba że reguły CLS są bardziej rygorystyczne. Jeśli składnik jest zbudowany przy użyciu tylko reguł w specyfikacji CLS, oznacza to, że uwidacznia tylko funkcje CLS w jego interfejsie API, jest to **zgodne ze specyfikacją CLS**. Na przykład, `<framework-librares>` są zgodne ze specyfikacją CLS, ponieważ muszą one współpracować we wszystkich językach obsługiwanych przez platformę .NET.

Zapoznaj się z dokumentami w sekcji [więcej zasobów](#more-resources) poniżej, aby zapoznać się z omówieniem wszystkich funkcji w specyfikacji CLS.

## <a name="more-resources"></a>Dodatkowe zasoby

* [Wspólny system typów](./base-types/common-type-system.md)
* [Specyfikacja języka wspólnego](language-independence-and-language-independent-components.md)
