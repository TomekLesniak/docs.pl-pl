---
title: .NET Standard
description: Dowiedz się więcej na temat .NET Standard, jej wersji i implementacji platformy .NET, które go obsługują.
ms.date: 10/05/2020
ms.technology: dotnet-standard
ms.custom: updateeachrelease
ms.assetid: c044882c-af15-45f2-96d1-534557a5ee9b
ms.openlocfilehash: a4a59fea3ab1a6bc93a12e3f0aa13dea726d8121
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050403"
---
# <a name="net-standard"></a>.NET Standard

[.NET Standard](https://github.com/dotnet/standard) to formalna Specyfikacja interfejsów API platformy .NET, które są dostępne w wielu implementacjach platformy .NET. Uzasadnienie .NET Standard było bardziej jednorodne w ekosystemie platformy .NET. Jednak w programie .NET 5 jest stosowane inne podejście do ustanowienia jednorodności, a nowe podejście eliminuje konieczność .NET Standard w wielu scenariuszach. Aby uzyskać więcej informacji, zobacz [.NET 5 i .NET Standard](#net-5-and-net-standard) w dalszej części tego artykułu.

## <a name="net-implementation-support"></a>Obsługa implementacji platformy .NET

Różne implementacje platformy .NET przeznaczone dla konkretnych wersji .NET Standard. Każda wersja implementacji platformy .NET anonsuje najwyższą obsługiwaną przez nią wersję .NET Standard, instrukcję, która oznacza, że obsługuje także poprzednie wersje. Na przykład .NET Framework 4,6 implementuje .NET Standard 1,3, co oznacza, że uwidacznia wszystkie interfejsy API zdefiniowane w .NET Standard wersje 1,0 za pośrednictwem 1,3. Podobnie .NET Framework 4.6.1 implementuje .NET Standard 1,4, podczas gdy .NET 5,0 implementuje .NET Standard 2,1.

W poniższej tabeli wymieniono **minimalne** wersje implementacji, które obsługują każdą wersję .NET Standard. Oznacza to, że nowsze wersje wymienionej implementacji obsługują również odpowiednią wersję .NET Standard. Na przykład program .NET Core 2,1 i jego nowsze wersje obsługują .NET Standard 2,0 i wcześniejszych wersjach.

[!INCLUDE [net-standard-table](../../includes/net-standard-table.md)]

Aby znaleźć najwyższą wersję .NET Standard, która może być docelowa, wykonaj następujące czynności:

1. Znajdź wiersz wskazujący implementację platformy .NET, która ma zostać uruchomiona.
1. Znajdź w tym wierszu kolumnę, która wskazuje wersję rozpoczynającą od prawej do lewej.
1. Nagłówek kolumny wskazuje wersję .NET Standard obsługiwaną przez element docelowy. Możesz również określić dowolną niższą wersję .NET Standard. Nowsze wersje .NET Standard obsługują również Twoją implementację.
1. Powtórz ten proces dla każdej platformy, która ma być docelowa. Jeśli masz więcej niż jedną platformę docelową, należy wybrać mniejszą wersję między nimi. Na przykład jeśli chcesz uruchomić na .NET Framework 4,8 i .NET 5,0, najwyższa .NET Standard wersja, której można użyć, to .NET Standard 2,0.

### <a name="which-net-standard-version-to-target"></a>Która wersja .NET Standard ma być docelowa

W przypadku wybrania wersji .NET Standard docelowej należy wziąć pod uwagę tę wymianę:

- Im wyższa wersja, tym więcej interfejsów API są dostępne dla kodu biblioteki.
- Im niższa wersja, tym więcej aplikacji i bibliotek może korzystać z biblioteki.

Zalecamy, aby była dostępna *Najniższa* wersja .NET Standard. Po znalezieniu największej wersji .NET Standard można dowiedzieć się, wykonaj następujące kroki:

1. Wybierz następną niższą wersję .NET Standard i skompiluj projekt.
2. Jeśli projekt zostanie pomyślnie skompilowany, Powtórz krok 1. W przeciwnym razie Przekieruj do następnej wyższej wersji i jest to wersja, której chcesz użyć.

Jednak w przypadku mniejszych wersji .NET Standard wprowadzono kilka zależności pomocy technicznej. Jeśli projekt jest obiektem docelowym .NET Standard 1. x, zalecamy *również* przeprowadzenie .NET Standard 2,0. Upraszcza to wykres zależności dla użytkowników biblioteki, które działają na .NET Standard 2,0 zgodnych implementacji i zmniejsza liczbę pakietów potrzebnych do pobrania.

### <a name="net-standard-versioning-rules"></a>Reguły obsługi wersji .NET Standard

Istnieją dwie podstawowe reguły obsługi wersji:

- Dodatek: wersje .NET Standard są logicznie skoncentrowane koła: wyższe wersje obejmują wszystkie interfejsy API z poprzednich wersji. Nie ma żadnych istotnych zmian między wersjami.
- Niezmienne: po wysłaniu wersje .NET Standard są zamrożone.

Nie będą dostępne żadne nowe wersje .NET Standard po 2,1. Aby uzyskać więcej informacji, zobacz [.NET 5 i .NET Standard](#net-5-and-net-standard) w dalszej części tego artykułu.

## <a name="specification"></a>Specyfikacja

Specyfikacja .NET Standard to standardowy zestaw interfejsów API. Specyfikacja jest obsługiwana przez implementacje platformy .NET, w tym dla firmy Microsoft (w tym .NET Framework, .NET Core i mono) i Unity.

### <a name="official-artifacts"></a>Oficjalne artefakty

Oficjalną specyfikacją jest zestaw plików *CS* , które definiują interfejsy API, które są częścią standardu. [Katalog ref](https://github.com/dotnet/standard/tree/master/src/netstandard/ref) w [repozytorium dotnet/Standard](https://github.com/dotnet/standard) definiuje .NET Standard interfejsów API.

Pakiet webpackage [. Library](https://www.nuget.org/packages/NETStandard.Library) ([Źródło](https://github.com/dotnet/standard/blob/master/src/netstandard/pkg/NETStandard.Library.dependencies.props)) opisuje zestaw bibliotek, które definiują (w części) co najmniej jedną wersję .NET Standard.

Dany składnik, taki jak `System.Runtime` , zawiera opis:

- Część .NET Standard (tylko jej zakres).
- Wiele wersji .NET Standard dla tego zakresu.

Są udostępniane artefakty pochodne umożliwiające wygodniejsze odczytywanie i włączanie niektórych scenariuszy deweloperskich (na przykład przy użyciu kompilatora).

- [Lista interfejsów API w promocji](https://github.com/dotnet/standard/tree/master/docs/versions)
- Zestawy odwołań dystrybuowane jako pakiety NuGet, do których odwołuje się pakiet [.](https://www.nuget.org/packages/NETStandard.Library/)

### <a name="package-representation"></a>Reprezentacja pakietu

Podstawowym nośnikiem dystrybucji dla zestawów odwołań .NET Standard są pakiety NuGet. Implementacje są dostarczane na różne sposoby, odpowiednie dla każdej implementacji platformy .NET.

Pakiety NuGet mają co najmniej jedną [platformę](frameworks.md). Pakiety .NET Standard są przeznaczone dla struktury ".NET Standard". Można kierować platformą .NET Standard przy użyciu `netstandard` [TFM kompaktowy](frameworks.md) (na przykład `netstandard1.4` ). Biblioteki przeznaczone do uruchamiania w wielu implementacjach platformy .NET powinny wskazywać tę strukturę. Dla najszerszego zestawu interfejsów API, miejsce docelowe, `netstandard2.0` ponieważ liczba dostępnych interfejsów API jest większa niż dwa .NET Standard 1,6 i 2,0.

[`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library/)Pakiet webpackage odwołuje się do kompletnego zestawu pakietów NuGet, które definiują .NET Standard.  Najbardziej typowym sposobem docelowym `netstandard` jest odwołanie do tego pakietu. Opisuje i zapewnia dostęp do bibliotek platformy .NET ~ 40 i skojarzonych z nimi interfejsów API, które definiują .NET Standard. Możesz odwoływać się do dodatkowych pakietów, których celem jest `netstandard` uzyskanie dostępu do dodatkowych interfejsów API.

### <a name="versioning"></a>Przechowywanie wersji

Specyfikacja nie jest pojedyncza, ale zestaw interfejsów API z określoną wersją. Pierwsza wersja standardu ustanawia zestaw bazowy interfejsów API. Kolejne wersje dodają interfejsy API i dziedziczą interfejsy API zdefiniowane przez poprzednie wersje. Nie ma ustanowionego udostępniania do usuwania interfejsów API ze standardu.

.NET Standard nie jest specyficzna dla żadnej z implementacji platformy .NET ani nie jest zgodna ze schematem przechowywania wersji żadnej z tych implementacji.

Jak wspomniano wcześniej, nie będą dostępne żadne nowe wersje .NET Standard po 2,1.

## <a name="target-net-standard"></a>.NET Standard docelowe

Można [tworzyć .NET Standard bibliotek](../core/tutorials/libraries.md) przy użyciu kombinacji `netstandard` struktury i `NETStandard.Library` pakietu.

## <a name="net-framework-compatibility-mode"></a>.NET Framework tryb zgodności

Począwszy od .NET Standard 2,0, wprowadzono .NET Framework tryb zgodności. Ten tryb zgodności umożliwia projektom .NET Standard odwoływanie się do bibliotek .NET Framework, tak jakby były kompilowane dla .NET Standard. Odwoływanie się do bibliotek .NET Framework nie działa dla wszystkich projektów, takich jak biblioteki używające interfejsów API Windows Presentation Foundation (WPF).

Aby uzyskać więcej informacji, zobacz [.NET Framework tryb zgodności](../core/porting/third-party-deps.md#net-framework-compatibility-mode).

## <a name="net-standard-libraries-and-visual-studio"></a>Biblioteki .NET Standard i Visual Studio

Aby można było tworzyć biblioteki .NET Standard w programie Visual Studio, upewnij się, że masz program [Visual studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) lub visual Studio 2017 w wersji 15,3 lub nowszej zainstalowany w systemie Windows lub [Visual Studio dla komputerów Mac w wersji 7,1](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) lub nowszej zainstalowany na macOS.

Jeśli potrzebujesz korzystać tylko z bibliotek .NET Standard 2,0 w projektach, możesz to zrobić również w programie Visual Studio 2015. Konieczne jest jednak zainstalowanie klienta NuGet 3,6 lub nowszego. Klienta NuGet dla programu Visual Studio 2015 można pobrać ze strony [plików do pobrania](https://www.nuget.org/downloads) w programie NuGet.

## <a name="net-5-and-net-standard"></a>.NET 5 i .NET Standard

.NET 5 to implementacja platformy .NET, którą aktywnie opracowuje firma Microsoft. Jest to jeden produkt z jednolitym zestawem możliwości i interfejsów API, które mogą być używane dla aplikacji klasycznych systemu Windows i aplikacji konsolowych dla wielu platform, usług w chmurze i witryn sieci Web. [TFMs](frameworks.md) .NET 5,0 odzwierciedla te szerokie zakresy scenariuszy:

* `net5.0`

  Ten TFM jest przeznaczony dla kodu, który działa wszędzie. Kilka wyjątków zawiera tylko technologie, które działają na wielu platformach. W przypadku kodu platformy .NET 5 `net5.0` zastępuje zarówno parametr, `netcoreapp` jak i `netstandard` TFMs.

* `net5.0-windows`

  Jest to przykład [TFMs specyficzny dla systemu](frameworks.md#net-5-os-specific-tfms) operacyjnego, który dodaje funkcję specyficzną dla systemu operacyjnego do wszystkich elementów, które `net5.0` odwołują się do programu.

### <a name="when-to-target-net50-vs-netstandard"></a>Kiedy należy kierować do programu NET 5.0 a Standard

Dla istniejącego kodu, który `netstandard` jest celem, nie ma potrzeby zmiany TFM na `net5.0` . .NET 5,0 implementuje .NET Standard 2,1 i starsze. Jedyną przyczyną przekierowania z .NET Standard do programu .NET 5,0 jest uzyskanie dostępu do większej liczby funkcji środowiska uruchomieniowego, funkcji języka lub interfejsów API. Na przykład w celu użycia języka C# 9 należy wskazać platformę .NET 5,0. W celu uzyskania dostępu do nowszych funkcji można uzyskać dostęp do programu .NET 5,0 i .NET Standard, aby udostępnić bibliotekę innym implementacjom platformy .NET.

Poniżej przedstawiono niektóre wskazówki dotyczące nowego kodu dla programu .NET 5:

* Składniki aplikacji

  Jeśli używasz bibliotek do podziału aplikacji na kilka składników, zalecamy, aby określić, `net5.x` gdzie `5.x` jest najwcześniejszą wersją programu .NET 5, którą aplikacja może kierować. Dla uproszczenia najlepiej zachować wszystkie projekty, które tworzą aplikację w tej samej wersji platformy .NET. Następnie możesz założyć te same funkcje BCL wszędzie.

* Biblioteki wielokrotnego użytku

  Jeśli tworzysz biblioteki wielokrotnego użytku, które planujesz dostarczać przy użyciu narzędzia NuGet, weź pod uwagę różnice między zasięgiem i dostępnym zestawem funkcji. .NET Standard 2,0 to Najnowsza wersja obsługiwana przez .NET Framework, dzięki czemu zapewnia dobry zasięg z dość dużym zestawem funkcji. Nie zaleca się określania wartości docelowej .NET Standard 1. x, ponieważ ograniczenie dostępnego zestawu funkcji jest minimalne.

  Jeśli nie musisz obsługiwać .NET Framework, możesz przejść do .NET Standard 2,1 lub .NET 5. Zalecamy pominięcie .NET Standard 2,1 i przejście bezpośrednio do programu .NET 5. Najczęściej używane biblioteki będą kończyć wiele elementów docelowych dla .NET Standard 2,0 i .NET 5. Obsługa .NET Standard 2,0 zapewnia największą zasięg, a obsługa programu .NET 5 zapewnia możliwość korzystania z najnowszych funkcji platformy dla klientów, którzy znajdują się już w programie .NET 5.

### <a name="net-standard-problems"></a>.NET Standard problemy

Poniżej przedstawiono niektóre problemy dotyczące .NET Standard, które pomagają w wyjaśnieniu, dlaczego platforma .NET 5 jest lepszym sposobem udostępniania kodu między platformami i obciążeniami:

- Powolne Dodawanie nowych interfejsów API

  .NET Standard został utworzony jako zestaw interfejsów API, że wszystkie implementacje platformy .NET będą musiały być obsługiwane, w związku z czym wystąpił proces recenzowania w celu dodania nowych interfejsów API. Celem było ujednolicenie tylko interfejsów API, które można zaimplementować we wszystkich bieżących i przyszłych platformach .NET. W efekcie, gdyby funkcja była niedostępna do określonej wersji, może być konieczne odczekanie przez kilka lat przed dodaniem jej do wersji Standard. Następnie poczekaj, aż Nowa wersja .NET Standard będzie ogólnie obsługiwana.

  **Rozwiązanie w programie .NET 5:** Gdy funkcja jest zaimplementowana, jest już dostępna dla każdej aplikacji i biblioteki platformy .NET 5, ponieważ baza kodu jest udostępniona. I ponieważ nie ma żadnych różnic między specyfikacją interfejsu API i jego implementacją, można korzystać z nowych funkcji znacznie szybciej niż w przypadku .NET Standard.

- Wersja złożona

  Oddzielenie specyfikacji interfejsu API od jej implementacji powoduje złożone mapowanie między wersjami specyfikacji interfejsu API i wersjami implementacji. Ta złożoność jest widoczna w tabeli pokazanej wcześniej w tym artykule i instrukcje dotyczące sposobu jej interpretacji.

  **Rozwiązanie w programie .NET 5:** Nie ma rozdzielenia między specyfikacją interfejsu API programu .NET 5. x i jej implementacją. Wynikiem jest uproszczony schemat TFM. Istnieje jeden prefiks TFM dla wszystkich obciążeń: `net5.0` jest używany w bibliotekach, aplikacjach konsolowych i aplikacjach sieci Web. Jedyną różnicą jest [sufiks określający interfejsy API specyficzne dla platformy](frameworks.md#net-5-os-specific-tfms) dla określonej platformy, takie jak `net5.0-windows` . Dzięki tej konwencji nazewnictwa TFM można łatwo stwierdzić, czy dana aplikacja może korzystać z danej biblioteki. Nie jest wymagana tabela odpowiedników numerów wersji, taka jak ta dla .NET Standard.

- Platforma — nieobsługiwane wyjątki w czasie wykonywania

  .NET Standard udostępnia interfejsy API specyficzne dla platformy. Kod może kompilować bez błędów i prawdopodobnie być przenośny na dowolną platformę, nawet jeśli nie jest przenośny. Gdy jest uruchomiona na platformie, która nie ma implementacji dla danego interfejsu API, pojawiają się błędy czasu wykonywania.

  **Rozwiązanie w programie .NET 5:** Zestaw SDK programu .NET 5 zawiera analizatory kodu, które są domyślnie włączone. Analizator zgodności platformy wykrywa niezamierzone użycie interfejsów API, które nie są obsługiwane na platformach, na których zamierzasz pracować. Aby uzyskać więcej informacji, zobacz [Analizator zgodności platformy](analyzers/platform-compat-analyzer.md).

### <a name="net-standard-not-deprecated"></a>Nie .NET Standard przestarzałe

.NET Standard jest nadal wymagana dla bibliotek, które mogą być używane przez wiele implementacji platformy .NET. Zalecamy .NET Standard w następujących scenariuszach:

* Służy `netstandard2.0` do udostępniania kodu między .NET Framework i wszystkimi innymi implementacjami programu .NET.
* Służy `netstandard2.1` do udostępniania kodu między programami mono, Xamarin i .NET Core 3. x.

## <a name="see-also"></a>Zobacz też

- [Wersje .NET Standard (Źródło)](https://github.com/dotnet/standard/blob/master/docs/versions.md)
- [Wersje .NET Standard (interaktywny interfejs użytkownika)](https://dotnet.microsoft.com/platform/dotnet-standard#versions)
- [Kompilowanie biblioteki .NET Standard](../core/tutorials/library-with-visual-studio.md)
- [Obsługiwane rozwiązania międzyplatformowe](./library-guidance/cross-platform-targeting.md)
