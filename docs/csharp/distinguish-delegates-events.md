---
title: Delegaty a zdarzenia
description: Zapoznaj się z różnicą między delegatami i zdarzeniami oraz kiedy korzystać z każdej z tych funkcji platformy .NET Core.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 0fdc8629-2fdb-4a7c-a433-5b9d04eaf911
ms.openlocfilehash: 193a9b0fe0e0c36deb6552449c92135057412225
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414672"
---
# <a name="distinguishing-delegates-and-events"></a>Wyróżniające się obiekty delegowane i zdarzenia

[Poprzednie](modern-events.md)

Deweloperzy, którzy są nowym środowiskiem .NET Core, często decydują się, gdy projekt jest oparty na projekcie `delegates` i opiera się na projekcie `events` . Wybór delegatów lub zdarzeń jest często trudny, ponieważ dwie funkcje języka są podobne. Zdarzenia są nawet kompilowane przy użyciu obsługi języka dla delegatów.

Obie te funkcje oferują scenariusz późnego wiązania: włączają scenariusze, w których składnik komunikuje się, wywołując metodę, która jest znana tylko w czasie wykonywania. Obsługują one metody jednego i wielu subskrybentów. Może to być nazywane singlecast i obsługą multiemisji. Obie te funkcje obsługują podobną składnię do dodawania i usuwania programów obsługi. Na koniec, podnoszenie poziomu zdarzenia i wywołanie delegata używa dokładnie tej samej składni wywołania metody. Obie te funkcje obsługują tę samą `Invoke()` składnię metody do użycia z `?.` operatorem.

W przypadku wszystkich tych podobieństw można łatwo mieć problemy z ustaleniem, kiedy należy używać tego programu.

## <a name="listening-to-events-is-optional"></a>Nasłuchiwanie zdarzeń jest opcjonalne

Najważniejszym zagadnieniem przy określaniu, które funkcje języka mają być używane, jest to, czy musi być dołączonym subskrybentem. Jeśli kod musi wywoływać kod dostarczony przez subskrybenta, należy użyć projektu opartego na delegatach, gdy zachodzi potrzeba zaimplementowania wywołania zwrotnego. Jeśli kod może zakończyć całą pracę bez wywoływania subskrybentów, należy użyć projektu opartego na zdarzeniach.

Rozważ przykłady skompilowane w tej sekcji. Kod utworzony przy użyciu `List.Sort()` musi mieć funkcję porównującą, aby poprawnie sortować elementy. Zapytania LINQ muszą zostać dostarczone z delegatami w celu ustalenia, jakie elementy mają być zwracane. Oba używane projekty skompilowane z delegatami.

Rozważ `Progress` zdarzenie. Raportuje postęp zadania.
Zadanie kontynuuje działanie niezależnie od tego, czy istnieją odbiorniki.
`FileSearcher`Jest to kolejny przykład. Nadal będzie można wyszukiwać i znajdować wszystkie pliki, które zostały uzyskane, nawet jeśli nie załączono żadnych subskrybentów zdarzeń.
Formanty środowiska użytkownika nadal działają poprawnie, nawet jeśli nie ma subskrybentów nasłuchujących zdarzeń. Oba używają projektów opartych na zdarzeniach.

## <a name="return-values-require-delegates"></a>Wartości zwracane wymagają delegatów

Innym zagadnieniem jest prototyp metody dla metody delegata. Jak widać, delegatów używanych dla zdarzeń wszystkie mają typ zwracany void. Zobaczysz również, że istnieją idiomy do tworzenia programów obsługi zdarzeń, które przekazują informacje z powrotem do źródeł zdarzeń przez modyfikowanie właściwości obiektu argumentu zdarzenia. Chociaż te idiomy pracują, nie są tak naturalne jak zwracanie wartości z metody.

Należy zauważyć, że te dwa heurystyke mogą często być obecne: Jeśli metoda Delegate zwraca wartość, prawdopodobnie będzie to miało wpływ na algorytm.

## <a name="events-have-private-invocation"></a>Zdarzenia mają prywatne wywołanie

Klasy inne niż te, w których zdarzenie jest zawarte może dodawać i usuwać detektory zdarzeń; zdarzenie może wywołać tylko klasę zawierającą zdarzenie. Zdarzenia są zwykle publicznymi elementami członkowskimi klas.
W wyniku porównania Delegaty są często przesyłane jako parametry i przechowywane jako prywatne elementy członkowskie klasy, jeśli są przechowywane w ogóle.

## <a name="event-listeners-often-have-longer-lifetimes"></a>Detektory zdarzeń często mają dłuższe okresy istnienia

Te detektory zdarzeń mają dłuższy okres istnienia to nieco słabsze uzasadnienie. Jednak można stwierdzić, że projekty oparte na zdarzeniach są bardziej naturalne, gdy źródło zdarzeń będzie w długim czasie podnieść zdarzenia. Możesz zobaczyć przykłady projektowania opartego na zdarzeniach dla formantów środowiska użytkownika w wielu systemach. Po zasubskrybowaniu zdarzenia Źródło zdarzenia może zgłosić zdarzenia przez cały okres istnienia programu.
(Możesz anulować subskrypcję zdarzeń, gdy nie są już potrzebne.)

Kontrast, który ma wiele projektów opartych na delegatach, gdzie delegat jest używany jako argument do metody i delegat nie jest używany po powrocie tej metody.

## <a name="evaluate-carefully"></a>Dokładnie Oceń

Powyższe uwagi nie są regułami twardymi i szybkimi. Zamiast tego przedstawiają wskazówki, które mogą pomóc zdecydować, który wybór jest najlepszy dla danego użycia. Ze względu na to, że są podobne, można nawet prototypować i zastanowić się, że będzie bardziej naturalna współpraca z nimi. Oba obsługują również scenariusze późnego wiązania. Użyj tego, który komunikuje się z projektem najlepiej.
