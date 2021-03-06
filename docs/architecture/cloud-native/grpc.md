---
title: gRPC
description: Dowiedz się więcej na temat gRPC, jego roli w aplikacjach natywnych w chmurze i różnice między komunikacją HTTP RESTful.
author: robvet
no-loc:
- Blazor
- Blazor WebAssembly
ms.date: 05/13/2020
ms.openlocfilehash: 9ed6906bd388a1ddef7f97bbaac001b4274853f9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158087"
---
# <a name="grpc"></a>gRPC

Do tej pory ta książka koncentruje się na komunikacji [opartej na protokole REST](/azure/architecture/best-practices/api-design) . Wiemy, że reszta jest elastycznym stylem architektonicznym, który definiuje operacje oparte na CRUDniu w odniesieniu do zasobów jednostki. Klienci współpracują z zasobami w protokole HTTP z modelem komunikacji żądania/odpowiedzi. Podczas gdy usługa REST jest szeroko zaimplementowana, nowsza Technologia komunikacji, gRPC, zyskała ogromne możliwości w całej społeczności natywnej w chmurze.

## <a name="what-is-grpc"></a>Co to jest gRPC?

gRPC to nowoczesne środowisko o wysokiej wydajności, które powoduje rozwój starego protokołu [zdalnego wywołania procedury (RPC)](https://en.wikipedia.org/wiki/Remote_procedure_call) w wieku. Na poziomie aplikacji gRPC usprawnia obsługę komunikatów między klientami a usługami zaplecza. Pochodzący z usługi Google, gRPC jest typu open source i częścią ekosystemu  [macierzystego przetwarzania w chmurze (CNCF)](https://www.cncf.io/) w ramach ofert natywnych w chmurze. CNCF traktuje gRPC [projekt inkubacji](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc). Inkubacja oznacza, że użytkownicy końcowi korzystają z technologii w aplikacjach produkcyjnych, a projekt ma w dobrej kondycji liczbę współautorów.

Typowa aplikacja kliencka gRPC będzie uwidaczniać lokalną funkcję w procesie, która implementuje operację biznesową. W obszarze okładek ta funkcja lokalna wywołuje inną funkcję na komputerze zdalnym. To, co wydaje się być wywołaniem lokalnym, stanowi przezroczyste wywołanie poza procesem do usługi zdalnej. Połączona z usługą RPC tworzy abstrakcyjną komunikację między komputerami, serializacji i wykonania w sieci.

W aplikacjach natywnych w chmurze deweloperzy często pracują w różnych językach programowania, strukturach i technologiach. Takie *współdziałanie* komplikuje kontrakty dotyczące komunikatów i instalację wodociągową wymaganą do komunikacji między platformami.  gRPC zapewnia "jednorodną warstwę poziomą", która jest abstrakcyjna. Kod deweloperów w swojej natywnej platformie skupia się na funkcjonalności biznesowej, podczas gdy gRPC obsługuje komunikację wodociągową.

gRPC oferuje kompleksową pomoc techniczną dla najpopularniejszych stosów programistycznych, w tym Java, JavaScript, C#, go, Swift i NodeJS.

## <a name="grpc-benefits"></a>Korzyści z gRPC

gRPC używa protokołu HTTP/2 do protokołu transportowego. Chociaż zgodne z protokołem HTTP 1,1, usługa HTTP/2 oferuje wiele zaawansowanych możliwości:

- Binarny protokół ramek do transportu danych — w przeciwieństwie do protokołu HTTP 1,1, który jest oparty na tekście.
- Obsługa multipleksowania do wysyłania wielu żądań równoległych za pośrednictwem tego samego połączenia — limity protokołu HTTP 1,1 w czasie przetwarzania do jednego komunikatu żądania/odpowiedzi jednocześnie.
- Dwukierunkowa komunikacja dwustronna służąca do jednoczesnego wysyłania zarówno żądań klientów, jak i odpowiedzi na serwer.
- Wbudowane przesyłanie strumieniowe i przekazywanie żądań i odpowiedzi na asynchroniczne strumienie dużych zestawów danych.
- Kompresja nagłówka, która zmniejsza użycie sieci.

gRPC jest lekki i wysoce wydajny. Może to być nawet 8x szybciej niż Serializacja JSON z komunikatami 60-80% mniejszych. W programie Microsoft [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) sprzężeniem wydajność gRPC przekracza szybkość i wydajność wysoce zoptymalizowanych [powiązań NetTCP](/dotnet/api/system.servicemodel.nettcpbinding?view=netframework-4.8). W przeciwieństwie do NetTCP, który preferuje stos firmy Microsoft, gRPC jest dla wielu platform.

## <a name="protocol-buffers"></a>Bufory protokołu

gRPC obejmuje technologię "open source" o nazwie [bufory protokołu](https://developers.google.com/protocol-buffers/docs/overview). Zapewniają wysoce wydajny i neutralny dla platformy format serializacji służący do serializowania komunikatów strukturalnych wysyłanych przez usługi. Deweloperzy mogą definiować kontrakt usługi dla każdej mikrousługi przy użyciu języka definicji (IDL) dla wielu platform. Umowa zaimplementowana jako `.proto` plik tekstowy, opisuje metody, dane wejściowe i wyjściowe dla każdej usługi. Ten sam plik kontraktu może służyć do gRPC klientów i usług opartych na różnych platformach deweloperskich.

Przy użyciu pliku proto, kompilatora protobuf, `protoc` program generuje kod klienta i usługi dla platformy docelowej. Kod zawiera następujące składniki:

- Obiekty silnie wpisane, udostępnione przez klienta i usługę, które reprezentują operacje usługi i elementy danych dla wiadomości.
- Klasa bazowa o jednoznacznie określonym typie z wymaganą siecią wodociągową, którą zdalna usługa gRPC może dziedziczyć i zwiększać.
- Procedura wejścia klienta, która zawiera wymagane instalacje wodociągowe do wywołania zdalnej usługi gRPC.

W czasie wykonywania każdy komunikat jest serializowany jako standardowa reprezentacja protobuf i wymieniany między klientem a usługą zdalną. W przeciwieństwie do JSON lub XML, komunikaty protobuf są serializowane jako skompilowane bajty binarne.

Książka [gRPC dla deweloperów programu WCF](../grpc-for-wcf-developers/index.md)dostępna w witrynie architektury firmy Microsoft zapewnia szczegółowe pokrycie GRPC i buforów protokołów.

## <a name="grpc-support-in-net"></a>Obsługa gRPC w programie .NET

gRPC jest zintegrowany z zestawem SDK platformy .NET Core 3,0 i nowszymi wersjami. Obsługiwane są następujące narzędzia:

- Program Visual Studio 2019, wersja 16,3 lub nowsza z zainstalowanym obciążeniem programowaniem w sieci Web.
- Visual Studio Code
- Interfejs wiersza polecenia dotnet

Zestaw SDK zawiera narzędzia dla routingu punktów końcowych, wbudowane IoC i rejestrowanie. Serwer sieci Web Kestrel "open source" obsługuje połączenia HTTP/2. Rysunek 4-20 pokazuje szablon programu Visual Studio 2019, który tworzy szkielet projektu szkieletu dla usługi gRPC. Zwróć uwagę na to, jak platforma .NET Core w pełni obsługuje systemy Windows, Linux i macOS.

![Obsługa gRPC w programie Visual Studio 2019](./media/visual-studio-2019-grpc-template.png)

**Rysunek 4-20**. Obsługa gRPC w programie Visual Studio 2019
  
Rysunek 4-21 przedstawia usługi szkieletowej gRPC wygenerowanej na podstawie wbudowanej szkieletu zawartej w programie Visual Studio 2019.  

![projekt gRPC w programie Visual Studio 2019](./media/grpc-project.png  )

**Rysunek 4-21**. projekt gRPC w programie Visual Studio 2019

Na poprzedniej ilustracji Zanotuj plik opisu proto i kod usługi. Jak zobaczysz szybko, program Visual Studio generuje dodatkową konfigurację zarówno dla klasy startowej, jak i bazowego pliku projektu.

## <a name="grpc-usage"></a>gRPC użycie

Preferuj gRPC w następujących scenariuszach:

- Synchroniczna komunikacja mikrousługi zaplecza do mikrousług w przypadku, gdy do dalszego przetwarzania jest wymagana natychmiastowa odpowiedź.
- Środowiska Polyglot, które muszą obsługiwać mieszane platformy programistyczne.
- Niska opóźnienia i Wysoka przepływność komunikacji, w której wydajność jest krytyczna.
- Komunikacja między punktami w czasie rzeczywistym — gRPC może wypychanie wiadomości w czasie rzeczywistym bez sondowania i zapewnia doskonałą obsługę transmisji dwukierunkowej.
- Środowiska ograniczone do sieci — binarne komunikaty gRPC są zawsze mniejsze niż odpowiedni tekst tekstowy w formacie JSON.

W tej chwili ten zapis gRPC jest używany głównie z usługami zaplecza. Nowoczesne przeglądarki nie mogą zapewnić poziomu kontroli protokołu HTTP/2 wymaganego do obsługi klienta frontonu gRPC. Takie rozwiązanie jest obsługiwane przez program [gRPC-Web with .NET](https://devblogs.microsoft.com/aspnet/grpc-web-for-net-now-available/) , który umożliwia gRPC komunikację z aplikacjami opartymi na przeglądarce skompilowanymi przy użyciu języka JavaScript lub Blazor WebAssembly technologii. [gRPC-Web](https://github.com/grpc/grpc/blob/master/doc/PROTOCOL-WEB.md) ASP.NET Core umożliwia aplikacji gRPC do obsługi funkcji gRPC w aplikacjach przeglądarki:

- Jednoznacznie wpisane, generowane przez kod klientów
- Kompaktowe komunikaty protobuf
- Przesyłanie strumieniowe serwera

## <a name="grpc-implementation"></a>Implementacja gRPC

Architektura referencyjna mikrousług [eshop na kontenerach](https://github.com/dotnet-architecture/eShopOnContainers)od firmy Microsoft pokazuje, jak zaimplementować usługi gRPC Services w aplikacjach .NET Core. Rysunek 4-22 przedstawia architekturę zaplecza.

![Architektura zaplecza dla eShop na kontenerach](./media/eshop-with-aggregators.png)

**Rysunek 4-22**. Architektura zaplecza dla eShop na kontenerach

Na poprzedniej ilustracji należy zwrócić uwagę, w jaki sposób eShop jest wdrażany w ramach [wzorca dla frontonów](/azure/architecture/patterns/backends-for-frontends) (BFF) przez udostępnienie wielu bram interfejsu API. Omawiamy wzorzec BFF we wcześniejszej części tego rozdziału. Zwróć szczególną uwagę na mikrousługę agregatora (szarą), która znajduje się między wielousługową bramą interfejsu API zakupów w sieci Web i mikrousługimi zakupów zaplecza. Agregator odbiera pojedyncze żądanie od klienta, wysyła je do różnych mikrousług, agreguje wyniki i odsyła je do żądającego klienta. Takie operacje zwykle wymagają komunikacji synchronicznej jako do wygenerowania natychmiastowej odpowiedzi. W eShop, wywołania zaplecza z agregatora są wykonywane przy użyciu gRPC, jak pokazano na rysunku 4-23.

![gRPC w eShop w kontenerach](./media/grpc-implementation.png)

**Rysunek 4-23**. gRPC w eShop w kontenerach

Komunikacja gRPC wymaga zarówno składnika klienta, jak i serwera. Na poprzedniej ilustracji należy zwrócić uwagę na to, jak agregator zakupów implementuje klienta gRPC. Klient dokonuje synchronicznych wywołań gRPC (czerwony) do mikrousług zaplecza, z których każdy implementuje serwer gRPC. Zarówno klient, jak i serwer wykorzystują wbudowaną gRPCą instalację z zestaw .NET Core SDK. Klasy *pośredniczące* po stronie klienta zapewniają instalację do wywoływania zdalnych wywołań gRPC. Składniki po stronie serwera zapewniają gRPCą, że niestandardowe klasy usług mogą dziedziczyć i zużywać.

Mikrousługi, które uwidaczniają interfejs API RESTful i komunikację gRPC, wymagają wielu punktów końcowych do zarządzania ruchem. Należy otworzyć punkt końcowy, który nasłuchuje ruchu HTTP dla wywołań RESTful i drugi dla wywołań gRPC. Punkt końcowy gRPC musi być skonfigurowany dla protokołu HTTP/2, który jest wymagany do komunikacji gRPC.

Staramy się oddzielić mikrousługi z wzorcem komunikacji asynchronicznej, ponieważ niektóre operacje wymagają bezpośrednich wywołań. gRPC powinien być głównym wyborem do bezpośredniej komunikacji synchronicznej między mikrousługami. Jej protokół komunikacyjny o wysokiej wydajności oparty na protokole HTTP/2 i bufory protokołu sprawiają, że jest idealnym wyborem.

## <a name="looking-ahead"></a>Spojrzenie na przyszłość

Patrząc na przyszłość, gRPC będzie nadal uzyskać trakcję dla systemów natywnych w chmurze. Zalety wydajności i łatwość programowania są atrakcyjne. Jednakże reszta będzie prawdopodobnie przez długi czas. Program Excel IT dla publicznie uwidocznionych interfejsów API i ze względu na zgodność z poprzednimi wersjami.

>[!div class="step-by-step"]
>[Poprzedni](service-to-service-communication.md) 
> [Dalej](service-mesh-communication-infrastructure.md)
