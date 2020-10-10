---
title: Wersje, poprawki i pomoc techniczna platformy .NET
description: Dowiedz się więcej o wersjach, poprawkach i obsłudze programu .NET 5 (w tym .NET Core) i nowszych wersjach.
ms.date: 10/07/2020
ms.topic: overview
ms.author: tdykstra
author: tdykstra
ms.openlocfilehash: 45286e18c41da7eb6717729360077b64539c3db5
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877730"
---
# <a name="releases-and-support-for-net-core-and-net-5"></a>Wersje i pomoc techniczna dla platformy .NET Core i .NET 5

Firma Microsoft dostarcza główne wersje, drobne wersje i aktualizacje obsługi (poprawki) dla programu .NET 5,0 (oraz platformy .NET Core) i nowszych wersji. W tym artykule opisano typy wydań, aktualizacje obsługi, paski funkcji zestawu SDK, okresy pomocy technicznej i opcje pomocy technicznej.

## <a name="release-types"></a>Typy wersji

Informacje o typie każdej wersji są zakodowane w numerze wersji w postaci *główna. pomocnicza. poprawka*.

Na przykład:

* .NET Core 3,0 i NET 5,0 są wersjami głównymi.
* .NET Core 3,1 to pierwsza wersja pomocnicza po wersji głównej programu .NET Core 3,0.
* .NET Core 3.1.7 to siódma poprawka dla programu .NET Core 3,1.

### <a name="major-releases"></a>Wersje główne

Główne wydania obejmują nowe funkcje, nowy publiczny obszar powierzchniowy interfejsu API i poprawki błędów. Przykłady obejmują platformy .NET Core 3,0 i .NET 5,0.  Ze względu na charakter zmian, te wersje powinny mieć istotne zmiany. Wersje główne instalują się obok poprzednich wersji głównych.

### <a name="minor-releases"></a>Wersje pomocnicze

Wersje pomocnicze obejmują również nowe funkcje, publiczny obszar powierzchniowy interfejsu API i poprawki błędów, a także mogą ulec zmianie. Przykłady obejmują platformy .NET Core 2,1 i .NET Core 3,1. Różnica między tymi i głównymi wersjami polega na tym, że wielkość zmian jest mniejsza. Aktualizacja aplikacji z platformy .NET Core 3,0 do 3,1 ma mniejszy skok, aby przejść do przodu. Wersje pomocnicze instalują się równolegle z poprzednimi wersjami pomocniczymi.

### <a name="servicing-updates"></a>Obsługa aktualizacji

Obsługa aktualizacji (poprawek) jest wysyłana niemal co miesiąc, a te aktualizacje zawierają poprawki dotyczące zabezpieczeń i niezwiązanych z zabezpieczeniami. Na przykład .NET Core 3.1.8 to ósma Aktualizacja dla programu .NET Core 3,1. Gdy te aktualizacje zawierają poprawki zabezpieczeń, są one publikowane w "wtorek poprawek", który jest zawsze drugi wtorek miesiąca. Oczekiwanie na zachowanie zgodności z aktualizacjami. Począwszy od platformy .NET Core 3,1, aktualizacje obsługi są uaktualnieniami, które usuwają poprzednią aktualizację. Na przykład Najnowsza aktualizacja dotycząca obsługi dla 3,1 usuwa poprzednią aktualizację 3,1 po pomyślnej instalacji.

### <a name="feature-bands-sdk-only"></a>Paski funkcji (tylko SDK)

Obsługa wersji zestawu .NET SDK działa nieco inaczej niż środowisko uruchomieniowe platformy .NET. Aby można było wyrównać nowe wersje programu Visual Studio, aktualizacje zestawu SDK platformy .NET czasami obejmują nowe funkcje lub nowe wersje składników, takich jak MSBuild i NuGet. Te nowe funkcje lub składniki mogą być niezgodne z wersjami dostarczanymi w poprzednich aktualizacjach zestawu SDK dla tej samej wersji głównej lub pomocniczej.

Aby odróżnić te aktualizacje, zestaw SDK platformy .NET używa koncepcji grup funkcji. Na przykład pierwszy zestaw SDK programu .NET Core 3,1 został 3.1.100. Ta wersja odnosi się do  *grupy funkcji*3.1.1 XX. Paski funkcji są zdefiniowane w grupach setek w trzeciej sekcji numeru wersji. Na przykład 3.1.101 i 3.1.201 są wersjami w dwóch różnych funkcjach, a 3.1.101 i 3.1.199 znajdują się w tej samej funkcji. Gdy zestaw .NET Core SDK 3.1.101 jest zainstalowana, zestaw .NET Core SDK 3.1.100 jest usuwana z komputera, jeśli istnieje. Gdy zestaw .NET Core SDK 3.1.200 jest zainstalowana na tym samym komputerze, zestaw .NET Core SDK 3.1.101 nie zostanie usunięta.

### <a name="runtime-roll-forward-and-compatibility"></a>Przekazanie do przodu i zgodność środowiska uruchomieniowego

Aktualizacje główne i pomocnicze są instalowane równolegle z poprzednimi wersjami. Aplikacja skompilowana dla konkretnego elementu *głównego. wersja pomocnicza* nadal używa tego ukierunkowanego środowiska uruchomieniowego, nawet jeśli jest zainstalowana nowsza wersja. Aplikacja nie zostanie automatycznie przeniesiona do przodu w celu użycia nowszej wersji *głównej. pomocniczej* środowiska uruchomieniowego, chyba że użytkownik zdecyduje się na to zachowanie. Aplikacja, która została skompilowana dla platformy .NET Core 3,0, nie uruchamia się automatycznie na platformie .NET Core 3,1. Zalecamy ponowne skompilowanie aplikacji i przetestowanie jej przy użyciu nowszej głównej lub pomocniczej wersji środowiska uruchomieniowego przed wdrożeniem w środowisku produkcyjnym. Aby uzyskać więcej informacji, zobacz [aplikacje zależne od platformy —](versions/selection.md#framework-dependent-apps-roll-forward) przewinięcie do przodu i do [przodu wdrożenia](deploying/runtime-patch-selection.md).

Aktualizacje obsługi są traktowane inaczej niż wersje główne i pomocnicze. Aplikacja skompilowana dla platformy .NET Core 3,1 jest domyślnie uruchamiana w środowisku uruchomieniowym 3.1.0. Automatycznie przenosi do przodu, aby użyć nowszego środowiska uruchomieniowego 3.1.1 po zainstalowaniu tej aktualizacji. Jest to zachowanie domyślne, ponieważ chcemy używać poprawek zabezpieczeń zaraz po ich zainstalowaniu bez konieczności wykonywania żadnych innych czynności. Możesz zrezygnować z tego domyślnego zachowania do przekazywania.

## <a name="net-core-and-net-5-version-lifecycles"></a>Cykle życia .NET Core i .NET 5

Platformy .NET Core, .NET 5 i nowsze wersje przyjmują [nowoczesne cykl życia](/lifecycle/policies/modern) zamiast [stałego cyklu życia](/lifecycle/policies/fixed) , który został użyty dla wydań .NET Framework. Produkty ze stałym cyklem życia zapewniają długotrwały okres pomocy technicznej, na przykład 5 lat wsparcia podstawowego i kolejne 5 lat wsparcia dodatkowego. Wsparcie podstawowe obejmuje poprawki zabezpieczeń i niezwiązanych z zabezpieczeniami, natomiast Rozszerzona pomoc techniczna zawiera tylko poprawki zabezpieczeń. Produkty, które stosują nowoczesne cykl życia, mają większy model wsparcia o podobnym obsłudze, z krótszymi okresami pomocy technicznej i wieloma częstymi wersjami.

### <a name="release-tracks"></a>Ścieżki wydań

Istnieją dwa ślady pomocy technicznej dla wydań:

* *Bieżące* wersje

  Te wersje są obsługiwane do 3 miesięcy od następnych głównych lub pomocniczych wersji.

  Przykład:

  * Program .NET Core 3,0 został wysłany we wrześniu 2019 i nastąpiło po nim .NET Core 3,1 w grudniu 2019.
  * Obsługa platformy .NET Core 3,0 zakończyła się w 2020 marca, 3 miesiącach po 3,1.

* Wersje *długoterminowe pomocy technicznej* (LTS)

  Te wersje są obsługiwane przez co najmniej 3 lata lub 1 rok po następnej wersji LTS, jeśli ta data będzie późniejsza.

  Przykład:

  * Program .NET Core 2,1 został zwolniony w maju 2018 i został uznany za LTS wydanie w sierpniu 2018.
  * Platforma .NET Core 3,1 była następną wersją LTS i została wydana w grudniu 2019.
  * Ze względu na to, że 2021 sierpnia (3 lata) jest późniejsza niż grudzień 2020 (rok po 3,1 wydania), program .NET Core 2,1 jest obsługiwany do roku 2021.

Zwalnia alternatywę z LTS i Current, dzięki czemu wcześniejsza wersja jest obsługiwana dłużej niż w nowszej wersji. Na przykład platforma .NET Core 2,1 to wersja LTS z obsługą do 2021 sierpnia. Wydanie 3,0 zostało wysłane ponad rok później, ale wystąpiło wcześniejsze wsparcie w grudniu 2019.

Obsługa aktualizacji jest miesięczna i obejmuje poprawki dotyczące zabezpieczeń i niezwiązanych z zabezpieczeniami (niezawodność, zgodność i stabilność). Aktualizacje obsługi są obsługiwane do momentu wydania następnej aktualizacji obsługi. Obsługa aktualizacji ma zachowanie w czasie wykonywania. Oznacza to, że aplikacje domyślnie działają w najnowszej zainstalowanej aktualizacji obsługi środowiska uruchomieniowego.

## <a name="how-to-choose-a-release"></a>Jak wybrać wydanie

Jeśli tworzysz usługę i oczekujesz, że będzie ona regularnie aktualizowana, to bieżąca wersja, taka jak .NET 5,0, może być najlepszą opcją do uzyskania Aktualności dzięki najnowszym funkcjom platformy .NET.

W przypadku kompilowania aplikacji klienckiej, która będzie dystrybuowana do klientów, stabilność może być ważniejsze niż dostęp do najnowszych funkcji. Aplikacja musi być obsługiwana przez określony czas, zanim użytkownik będzie mógł uaktualnić do następnej wersji aplikacji. W takim przypadku wersja LTS, taka jak .NET Core 3,1, może być właściwą opcją.

### <a name="servicing-updates"></a>Obsługa aktualizacji

Aktualizacje obsługi platformy .NET są obsługiwane do momentu wydania następnej aktualizacji obsługi. Erze wydania jest miesięczna.

Należy regularnie instalować aktualizacje obsługi, aby upewnić się, że aplikacje są w stanie bezpiecznym i obsługiwanym. Na przykład jeśli Najnowsza aktualizacja obsługi dla platformy .NET Core 3,1 to 3.1.8, a my 3.1.9, 3.1.8 nie jest już Najnowsza. Obsługiwany poziom obsługi dla 3,1 jest następnie 3.1.9.

Informacje o najnowszych aktualizacjach obsługi dla każdej wersji głównej i pomocniczej znajdują się na [stronie pliki do pobrania platformy .NET](https://dotnet.microsoft.com/download/dotnet-core).

## <a name="end-of-support"></a>Koniec wsparcia

Koniec pomocy technicznej oznacza datę, po której firma Microsoft nie udostępnia już poprawek, aktualizacji lub pomocy technicznej dla wersji produktu. Przed tą datą upewnij się, że została przeniesiona do korzystania z obsługiwanej wersji. Nieobsługiwane wersje nie będą już otrzymywać aktualizacji zabezpieczeń chroniących Twoje aplikacje i dane.

## <a name="supported-operating-systems"></a>Obsługiwane systemy operacyjne

Programy .NET 5 (i .NET Core) i nowsze wersje można uruchamiać w różnych systemach operacyjnych. Każdy z tych systemów operacyjnych ma cykl życia zdefiniowany przez organizację sponsorowania (na przykład Microsoft, Red Hat lub Apple). Te harmonogramy cyklu życia są uwzględniane podczas dodawania i usuwania obsługi wersji systemu operacyjnego.

Gdy wersja systemu operacyjnego wyjdzie z pomocy technicznej, przestanie ona być testowana i zapewnia pomoc techniczną dla tej wersji. Aby uzyskać pomoc techniczną, użytkownicy muszą przejść do przodu do obsługiwanej wersji systemu operacyjnego.

Aby uzyskać więcej informacji, zobacz [Zasady cyklu życia systemu operacyjnego .NET](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md).

## <a name="get-support"></a>Uzyskiwanie pomocy technicznej

Użytkownik ma możliwość wyboru między pomocą techniczną firmy Microsoft i pomocą techniczną.

### <a name="microsoft-support"></a>Pomoc techniczna firmy Microsoft

Aby uzyskać pomoc techniczną, [skontaktuj się z pomoc techniczna firmy Microsoft Professional](https://support.microsoft.com/supportforbusiness/productselection/?sapid=4fd4947b-15ea-ce01-080f-97f2ca3c76e8).

Musisz mieć obsługiwany poziom obsługi (najnowsza dostępna aktualizacja obsługi), aby kwalifikować się do pomocy technicznej. Jeśli na komputerze jest uruchomiony system 3,1, a aktualizacja obsługi 3.1.8 została wydana, należy zainstalować ją jako pierwszy krok.

### <a name="community-support"></a>Pomoc techniczna w społeczności

Aby uzyskać pomoc techniczną, zobacz [stronę społeczności](https://dotnet.microsoft.com/platform/community).

## <a name="see-also"></a>Zobacz też

Aby uzyskać więcej informacji, w tym obsługiwane zakresy dat dla każdej wersji platformy .NET Core i programu .NET 5, zobacz [zasady pomocy technicznej](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).
