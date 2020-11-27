---
title: Model obiektów odnajdywania WCF
ms.date: 03/30/2017
ms.assetid: 8365a152-eacd-4779-9130-bbc48fa5c5d9
ms.openlocfilehash: 06984766fa8199a18197255c57492863a888e3aa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281940"
---
# <a name="wcf-discovery-object-model"></a>Model obiektów odnajdywania WCF

Funkcja odnajdywania WCF składa się z zestawu typów, które udostępniają ujednolicony model programowania, który umożliwia pisanie usług, które są wykrywalne w czasie wykonywania i klientów, którzy znajdą i korzystają z tych usług.  
  
## <a name="making-a-service-discoverable-and-finding-services"></a>Umożliwienie odnajdywania usługi i znajdowania usług  

 Aby umożliwić odnajdywanie usługi WCF, Dodaj element <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> do <xref:System.ServiceModel.Description.ServiceDescription> hosta usługi i Dodaj punkt końcowy odnajdywania. Jeśli usługa jest skonfigurowana do wysyłania komunikatów anonsu (przez dodanie <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> ), anons jest wysyłany, gdy host usługi jest otwarty i zamknięty.  
  
 Klient, który chce nasłuchiwać komunikatów anonsu usługi hostuje usługę anonsowania i dodaje jeden lub więcej punktów końcowych anonsów. Usługa anonsowania odbiera komunikaty anonsu i zgłasza zdarzenia anonsów.  
  
 Klient używa <xref:System.ServiceModel.Discovery.DiscoveryClient> klasy w celu wyszukania dostępnych usług. Aplikacja kliencka tworzy wystąpienie <xref:System.ServiceModel.Discovery.DiscoveryClient> klasy, przekazując punkt końcowy odnajdywania, który określa, gdzie mają być wysyłane komunikaty odnajdywania. Klient wywołuje <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> metodę, która wysyła `Probe` żądanie. Usługi nasłuchujące komunikatów odnajdywania odbierają to `Probe` żądanie. Jeśli usługa spełnia kryteria określone w `Probe` , wysyła `ProbeMatch` komunikat z powrotem do klienta.  
  
## <a name="object-model"></a>Model obiektów  

 Interfejs API odnajdywania WCF definiuje następujące klasy:  
  
- <xref:System.ServiceModel.Discovery.AnnouncementClient>  
  
- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
  
- <xref:System.ServiceModel.Discovery.AnnouncementService>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryClient>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryMessageSequenceGenerator>  
  
- <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryProxy>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryService>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryVersion>  
  
- <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
  
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>  
  
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>  
  
- <xref:System.ServiceModel.Discovery.FindCriteria>  
  
- <xref:System.ServiceModel.Discovery.FindRequestContext>  
  
- <xref:System.ServiceModel.Discovery.FindResponse>  
  
- <xref:System.ServiceModel.Discovery.ResolveCriteria>  
  
- <xref:System.ServiceModel.Discovery.ResolveResponse>  
  
- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>  

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
  
- <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
  
## <a name="announcementclient"></a>AnnouncementClient  

 <xref:System.ServiceModel.Discovery.AnnouncementClient>Klasa zapewnia metody synchroniczne i asynchroniczne do wysyłania komunikatów anonsu. Istnieją dwa typy komunikatów anonsów, Hello i bye. Wiadomość powitalna jest wysyłana w celu wskazania, że usługa stanie się dostępna, a komunikat bye jest wysyłany w celu wskazania, że istniejąca usługa stanie się niedostępna. Deweloper tworzy <xref:System.ServiceModel.Discovery.AnnouncementClient> wystąpienie, przekazując wystąpienie <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> jako parametr konstruktora.  
  
## <a name="announcementendpoint"></a>AnnouncementEndpoint  

 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> reprezentuje standardowy punkt końcowy ze stałym kontraktem anonsu. Jest on używany przez usługę lub klienta do wysyłania i odbierania komunikatów anonsów. Domyślnie <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> Klasa jest ustawiona do korzystania z wersji protokołu WS_Discovery 11.  
  
## <a name="announcementservice"></a>AnnouncementService  

 <xref:System.ServiceModel.Discovery.AnnouncementService> to oparta na systemie implementacja usługi anonsu, która odbiera i przetwarza Komunikaty anonsu. Po odebraniu komunikatu Hello lub bye <xref:System.ServiceModel.Discovery.AnnouncementService> wystąpienie wywołuje odpowiednią metodę wirtualną <xref:System.ServiceModel.Discovery.AnnouncementService.OnBeginOnlineAnnouncement%2A> lub <xref:System.ServiceModel.Discovery.AnnouncementService.OnBeginOfflineAnnouncement%2A> , która wywołuje zdarzenia anonsu.  
  
## <a name="discoveryclient"></a>Obiekt DiscoveryClient  

 <xref:System.ServiceModel.Discovery.DiscoveryClient>Klasa jest używana przez aplikację kliencką do znajdowania i rozwiązywania dostępnych usług. Zapewnia metody synchroniczne i asynchroniczne do znajdowania i rozpoznawania usług w oparciu o określone <xref:System.ServiceModel.Discovery.FindCriteria> i <xref:System.ServiceModel.Discovery.ResolveCriteria> odpowiednio. Deweloper tworzy <xref:System.ServiceModel.Discovery.DiscoveryClient> wystąpienie i udostępnia wystąpienie <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> jako parametr konstruktora.  
  
 Aby znaleźć usługę, deweloper wywołuje metodę synchroniczną lub asynchroniczną `Find` , która dostarcza <xref:System.ServiceModel.Discovery.FindCriteria> wystąpienie, które zawiera kryteria wyszukiwania do użycia. <xref:System.ServiceModel.Discovery.DiscoveryClient>Tworzy `Probe` komunikat z odpowiednimi nagłówkami i wysyła żądanie find. Ponieważ w dowolnym momencie może istnieć więcej niż jedno zaległe `Find` żądanie, klient skorelowany odebrane odpowiedzi i weryfikuje odpowiedź. Następnie dostarcza wyniki do obiektu wywołującego `Find` operacji przy użyciu <xref:System.ServiceModel.Discovery.FindResponse> .  
  
 Aby rozwiązać znaną usługę, deweloper wywołuje metodę synchroniczną lub asynchroniczną, `Resolve` która zapewnia wystąpienie <xref:System.ServiceModel.Discovery.ResolveCriteria> , które zawiera <xref:System.ServiceModel.EndpointAddress> znaną usługę. <xref:System.ServiceModel.Discovery.DiscoveryClient>Tworzy `Resolve` komunikat z odpowiednimi nagłówkami i wysyła żądanie rozwiązania. Odebrana odpowiedź jest skorelowane względem oczekujących żądań rozpoznawania, a wynik jest dostarczany do obiektu wywołującego `Resolve` operacji przy użyciu <xref:System.ServiceModel.Discovery.ResolveResponse> .  
  
 Jeśli serwer proxy odnajdywania jest dostępny w sieci i <xref:System.ServiceModel.Discovery.DiscoveryClient> wysyła żądanie odnajdywania w sposób multiemisyjny, serwer proxy odnajdywania może odpowiedzieć na wiadomość powitalną pomijania multiemisji. <xref:System.ServiceModel.Discovery.DiscoveryClient>Wywołuje `ProxyAvailable` zdarzenie po odebraniu komunikatów Hello w odpowiedzi na oczekujące `Find` lub `Resolve` żądania. `ProxyAvailable`Zdarzenie zawiera <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> Informacje o serwerze proxy odnajdywania. Aby skorzystać z tych informacji, można przełączyć się do trybu zarządzania z usługi ad hoc na tryb zarządzany.  
  
## <a name="discoveryendpoint"></a>DiscoveryEndpoint  

 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> reprezentuje standardowy punkt końcowy ze stałym kontraktem odnajdowania. Jest on używany przez usługę lub klienta do wysyłania i odbierania komunikatów odnajdywania. Domyślnie <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> jest ustawiony do użycia <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode.Managed?displayProperty=nameWithType> tryb i WSDiscovery11 WS-Discovery wersja.  
  
## <a name="discoverymessagesequencegenerator"></a>DiscoveryMessageSequenceGenerator  

 <xref:System.ServiceModel.Discovery.DiscoveryMessageSequenceGenerator> służy do generowania elementu, <xref:System.ServiceModel.Discovery.DiscoveryMessageSequence> gdy usługa wysyła komunikaty wykrywania lub anonsu.  
  
## <a name="discoveryservice"></a>DiscoveryService  

 <xref:System.ServiceModel.Discovery.DiscoveryService>Klasa abstrakcyjna zapewnia strukturę do odbioru i przetwarzania `Probe` oraz `Resolve` komunikatów. Po `Probe` odebraniu komunikatu program <xref:System.ServiceModel.Discovery.DiscoveryService> tworzy wystąpienie <xref:System.ServiceModel.Discovery.FindRequestContext> oparte na komunikacie przychodzącym i wywołuje <xref:System.ServiceModel.Discovery.DiscoveryService.OnBeginFind%2A> metodę wirtualną. Po `Resolve` odebraniu komunikatu <xref:System.ServiceModel.Discovery.DiscoveryService> wywołuje <xref:System.ServiceModel.Discovery.DiscoveryService.OnBeginResolve%2A> metodę wirtualną. Można dziedziczyć z tej klasy, aby zapewnić niestandardową implementację usługi odnajdywania.  
  
## <a name="discoveryproxy"></a>Obiektu DiscoveryProxy  

 <xref:System.ServiceModel.Discovery.DiscoveryProxy>Klasa abstrakcyjna zapewnia strukturę do otrzymywania i przetwarzania komunikatów odnajdywania i anonsowania. Po wdrożeniu niestandardowego serwera proxy odnajdywania dziedziczą z tej klasy. Po `Probe` odebraniu komunikatu przez multiemisję <xref:System.ServiceModel.Discovery.DiscoveryProxy> Klasa wywołuje `BeginShouldRedirectFind` metodę wirtualną, aby określić, czy powinien zostać wysłany komunikat o pominięciu multiemisji. Jeśli deweloper zdecyduje się nie wysyłać komunikatu pomijania multiemisji lub `Probe` komunikat został odebrany za pośrednictwem emisji pojedynczej, tworzy wystąpienie <xref:System.ServiceModel.Discovery.FindRequestContext> klasy na podstawie komunikatu przychodzącego i wywołuje `OnBeginFind` metodę wirtualną. Po `Resolve` odebraniu komunikatu przez multiemisję <xref:System.ServiceModel.Discovery.DiscoveryProxy> Klasa wywołuje `ShouldRedirectResolve` metodę wirtualną, aby określić, czy powinien zostać wysłany komunikat o pominięciu multiemisji. Jeśli deweloper zdecyduje się nie wysyłać komunikatu pomijania multiemisji lub `Resolve` komunikat został odebrany za pośrednictwem emisji pojedynczej, tworzy wystąpienie <xref:System.ServiceModel.Discovery.ResolveCriteria> klasy na podstawie komunikatu przychodzącego i wywołuje `OnBeginResolve` metodę wirtualną. Po odebraniu komunikatu Hello lub bye <xref:System.ServiceModel.Discovery.DiscoveryProxy> wywołuje odpowiednią metodę wirtualną ( `OnBeginOnlineAnnouncement` lub `OnBeingOfflineAnnouncement` ), która wywołuje zdarzenia anonsowania.  
  
## <a name="discoveryversion"></a>DiscoveryVersion  

 <xref:System.ServiceModel.Discovery.DiscoveryVersion>Klasa reprezentuje wersję protokołu odnajdywania do użycia.  
  
## <a name="endpointdiscoverybehavior"></a>EndpointDiscoveryBehavior  

 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>Klasa służy do kontrolowania wykrywalności punktu końcowego, określania rozszerzeń, dodatkowych nazw typów kontraktu. i zakresy skojarzone z tym punktem końcowym. To zachowanie jest dodawane do punktu końcowego aplikacji w celu jego skonfigurowania <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> . Po <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> dodaniu do hosta usługi wszystkie punkty końcowe aplikacji hostowane przez hosta usługi domyślnie stają się wykrywalne. Deweloper może wyłączyć odnajdywanie dla określonego punktu końcowego przez ustawienie <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Enabled%2A> właściwości na `false` .  
  
## <a name="endpointdiscoverymetadata"></a>Obiektu EndpointDiscoveryMetadata  

 <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>Klasa zawiera niezależną od wersji reprezentację punktu końcowego opublikowanego przez usługę. Zawiera adresy punktów końcowych, identyfikatory URI nasłuchiwania, nazwy typów kontraktów, zakresy, wersję i rozszerzenia metadanych określone przez dewelopera usługi. <xref:System.ServiceModel.Discovery.FindCriteria>Wysłany przez klienta podczas `Probe` operacji jest dopasowywany do <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> . Jeśli kryteria są zgodne, <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> zostanie zwrócone do klienta. Adres punktu końcowego w programie <xref:System.ServiceModel.Discovery.ResolveCriteria> jest dopasowany do adresu punktu końcowego <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> . Jeśli kryteria są zgodne, <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> zostanie zwrócone do klienta.  
  
## <a name="findcriteria"></a>Kryteria znajdowania  

 <xref:System.ServiceModel.Discovery.FindCriteria>Klasa jest klasą niezależną od wersji służącą do określania kryteriów używanych podczas znajdowania usługi. W pełni obsługuje on kryteria zdefiniowane w usłudze WS-Discovery dla pasujących usług. Ma także rozszerzenia, za pomocą których deweloperzy mogą określać wartości niestandardowe, które mogą być używane w procesie dopasowywania. Deweloper może podać kryteria zakończenia dla `Find` operacji <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> , określając, która określa łączną liczbę usług szukanych przez dewelopera lub określa wartość, która określa, <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> jak długo klient czeka na odpowiedzi.  
  
## <a name="findrequestcontext"></a>FindRequestContext  

 <xref:System.ServiceModel.Discovery.FindRequestContext>Klasa jest tworzona przez usługę odnajdywania na podstawie komunikatu, który `Probe` odbiera, gdy klient inicjuje `Find` operację. Zawiera ono wystąpienie <xref:System.ServiceModel.Discovery.FindCriteria> , które zostało określone przez klienta.  
  
## <a name="findresponse"></a>FindResponse  

 <xref:System.ServiceModel.Discovery.FindResponse>Klasa jest zwracana do obiektu wywołującego <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> z odpowiedziami `Find` operacji. Jest również obecny w <xref:System.ServiceModel.Discovery.FindCompletedEventArgs> . Zawiera kolekcję <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> , która jest kolekcją odnalezionych punktów końcowych i słownika <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> i <xref:System.ServiceModel.Discovery.DiscoveryMessageSequence> .  
  
## <a name="resolvecriteria"></a>ResolveCriteria  

 <xref:System.ServiceModel.Discovery.ResolveCriteria>Klasa jest klasą niezależną od wersji służącą do określania kryteriów używanych podczas rozpoznawania już znanej usługi. Zawiera adres punktu końcowego znanej usługi. Deweloper może podać kryteria zakończenia operacji rozpoznawania przez określenie <xref:System.ServiceModel.Discovery.ResolveCriteria.Duration%2A> , która określa, jak długo klient czeka na odpowiedzi.  
  
## <a name="resolveresponse"></a>ResolveResponse  

 Element <xref:System.ServiceModel.Discovery.ResolveResponse> jest zwracany do obiektu wywołującego <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> metody z odpowiedzią `Resolve` operacji. Jest również obecny w <xref:System.ServiceModel.Discovery.ResolveCompletedEventArgs> . Zawiera ono wystąpienie <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> , które jest wykrytymi punktami końcowymi i wystąpieniem <xref:System.ServiceModel.Discovery.DiscoveryMessageSequence> .  
  
## <a name="servicediscoverybehavior"></a>ServiceDiscoveryBehavior  

 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>Klasa umożliwia deweloperowi dodanie funkcji odnajdywania do usługi. To zachowanie zostanie dodane do <xref:System.ServiceModel.ServiceHost> . <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>Klasa iteruje punkty końcowe aplikacji dodane do hosta usługi i tworzy kolekcję <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> z wykrywalnych punktów końcowych. Domyślnie są wykrywalne wszystkie punkty końcowe. Wykrywalność określonego punktu końcowego można kontrolować przez dodanie <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> do tego konkretnego punktu końcowego. Jeśli punkty końcowe anonsu są dodawane do <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> , ogłoszenie wszystkich wykrywalnych punktów końcowych jest wysyłane przez poszczególne punkty końcowe anonsu, gdy host usługi jest otwarty lub zamknięty.  
  
## <a name="udpannouncementendpoint"></a>UdpAnnouncementEndpoint  

 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>Klasa jest standardowym punktem końcowym anonsu, który jest wstępnie skonfigurowany dla anonsu za pośrednictwem powiązania MULTIEMISJI UDP. Domyślnie program <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> jest ustawiony tak, aby korzystał z WSApril2005 wersja WS_Discovery.  
  
## <a name="udpdiscoveryendpoint"></a>UdpDiscoveryEndpoint  

 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>Klasa jest standardowym punktem końcowym odnajdywania, który jest wstępnie skonfigurowany do odnajdywania za pośrednictwem powiązania MULTIEMISJI UDP. Domyślnie program <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> jest ustawiony tak, aby korzystał z WSDiscovery11 WS-Discovery wersja i <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode.Adhoc?displayProperty=nameWithType> tryb.
