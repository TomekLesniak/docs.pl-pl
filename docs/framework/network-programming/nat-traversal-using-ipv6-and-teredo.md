---
title: Przechodzenie translatora adresów sieciowych przy użyciu protokołu IPv6 i Teredo
ms.date: 03/30/2017
ms.assetid: 568cd245-3300-49ef-a995-d81bf845d961
ms.openlocfilehash: a6448ddf117e1f454338869820751ae5d9e0070e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258624"
---
# <a name="nat-traversal-using-ipv6-and-teredo"></a>Przechodzenie translatora adresów sieciowych przy użyciu protokołu IPv6 i Teredo

Wprowadzono ulepszenia zapewniające obsługę przechodzenia do translacji adresów sieciowych (NAT). Te zmiany są przeznaczone do użycia z protokołami IPv6 i Teredo, ale mają zastosowanie również do innych technologii tunelowania IP. Te ulepszenia wpływają na klasy w <xref:System.Net> i powiązanych przestrzeniach nazw.  
  
 Te zmiany mogą mieć wpływ na aplikacje klienta i serwera, które zaplanowali korzystanie z technologii tunelowania IP.  
  
 Zmiany obsługujące przechodzenie do translatora adresów sieciowych są dostępne tylko dla aplikacji korzystających z programu .NET Framework w wersji 4. Te funkcje nie są dostępne we wcześniejszych wersjach .NET Framework.  
  
## <a name="overview"></a>Omówienie  

 Protokół internetowy w wersji 4 (IPv4) definiuje adres IPv4 jako 32 bitów Long. W efekcie protokół IPv4 obsługuje około 4 000 000 000 unikatowych adresów IP (2 ^ 32). Ponieważ liczba komputerów i urządzeń sieciowych w sieci Internet rozwiniętych w 1990s, limity przestrzeni adresów IPv4 stały się widoczne.  
  
 Jedną z kilku technik służących do rozbudowania okresu istnienia protokołu IPv4 jest wdrożenie translatora adresów sieciowych w celu zezwolenia na użycie jednego unikatowego publicznego adresu IP do reprezentowania dużej liczby prywatnych adresów IP (prywatnego intranetu). Prywatne adresy IP znajdujące się za urządzeniem NAT współdzielą jeden publiczny adres IPv4. Urządzenie NAT może być dedykowanym urządzeniem sprzętowym (na przykład niedrogim punktem dostępu bezprzewodowego i routerem) lub komputerem z uruchomioną usługą w celu zapewnienia translatora adresów sieciowych. Urządzenie lub usługa dla tego publicznego adresu IP tłumaczy pakiety sieciowe IP między publicznym Internetem a prywatnym intranetem.  
  
 Ten schemat działa dobrze w przypadku aplikacji klienckich działających w prywatnym intranecie, które wysyłają żądania do innych adresów IP (zazwyczaj serwerów) w Internecie. Urządzenie NAT lub serwer może zachować mapowanie żądań klientów, aby w przypadku zwrócenia odpowiedzi wiadomość o miejscu, w którym ma zostać wysłana odpowiedź. Jednak ten schemat nakłada problemy dla aplikacji działających w prywatnym intranecie za urządzeniem NAT, które chcą zapewnić usługi, nasłuchiwanie pakietów i reagowanie na nie. Jest to szczególnie przypadek w przypadku aplikacji równorzędnych.  
  
 Protokół IPv6 definiuje adres IPv4 jako 128 bitów. W efekcie protokół IPv6 obsługuje bardzo dużą przestrzeń adresów IP wynoszącą 3,2 x 10 ^ 38 unikatowych adresów (2 ^ 128). Mając przestrzeń adresową tego rozmiaru, jest możliwe, aby każde urządzenie połączone z Internetem miało unikatowy adres. Występują problemy. Większość świata nadal używa tylko protokołu IPv4. W szczególności wiele istniejących routerów i punktów dostępu bezprzewodowego używanych przez małe firmy, organizacje i gospodarstwa domowe nie obsługują protokołu IPv6. Niektórzy dostawcy usług internetowych, którzy obsługują tych klientów, nie obsługują lub nie skonfigurowali obsługi protokołu IPv6.  
  
 W pakiecie IPv4 opracowano kilka technologii przejściowych IPv6 do tunelowania adresów IPv6. Technologie te obejmują tunele 6to4, ISATAP i Teredo, które zapewniają przypisanie adresu i automatyczne tunelowanie do ruchu IPv6 emisji pojedynczej, gdy hosty IPv6 muszą przechodzą sieci IP4, aby dotrzeć do innych sieci IPv6. Pakiety IPv6 są wysyłane jako pakiety IPv4. Używane są kilka technik tunelowania, które umożliwiają przechodzenie translatora adresów sieciowych do adresów IPv6 za pomocą urządzenia NAT.  
  
 Protokół Teredo jest jedną z technologii przejściowych IPv6, która zapewnia łączność IPv6 z sieciami IPv4. Protokół Teredo jest udokumentowany w dokumencie RFC 4380 opublikowanym przez Internet Engineering Task Force (IETF). System Windows XP z dodatkiem SP2 lub nowszy zapewnia obsługę wirtualnej karty Teredo, która umożliwia udostępnienie publicznego adresu IPv6 w zakresie 2001:0::/32. Tego adresu IPv6 można użyć do nasłuchiwania połączeń przychodzących z Internetu i można je dostarczyć klientom obsługującym protokół IPv6, którzy chcą połączyć się z usługą nasłuchiwania. Spowoduje to zwolnienie aplikacji o sposobie rozwiązywania problemów z komputerem za urządzeniem NAT, ponieważ aplikacja może po prostu połączyć się z nim przy użyciu adresu IPv6 protokołu Teredo.  
  
## <a name="enhancements-to-support-nat-traversal-and-teredo"></a>Ulepszenia obsługi przechodzenia NAT i Teredo  

 Ulepszenia są dodawane do <xref:System.Net> <xref:System.Net.NetworkInformation> przestrzeni nazw, i i <xref:System.Net.Sockets> obsługują przechodzenie NAT przy użyciu protokołu IPv6 i Teredo.  
  
 Do klasy dodawane są kilka metod w <xref:System.Net.NetworkInformation.IPGlobalProperties?displayProperty=nameWithType> celu uzyskania listy adresów IP emisji pojedynczej na hoście. <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A>Metoda rozpoczyna asynchroniczne żądanie pobrania stabilnej tabeli adresów IP emisji pojedynczej na komputerze lokalnym. <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A>Metoda przerywa oczekujące asynchroniczne żądanie, aby pobrać stabilną tabelę adresów IP emisji pojedynczej na komputerze lokalnym. <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A>Metoda jest żądaniem synchronicznym, aby pobrać stabilną tabelę adresów IP emisji pojedynczej na komputerze lokalnym, czekając na zastabilizację tabeli adresów w razie potrzeby.  
  
 <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=nameWithType>Właściwość może służyć do określenia, czy <xref:System.Net.IPAddress> jest adresem IPv6 protokołu Teredo.  
  
 Korzystanie z tych nowych <xref:System.Net.NetworkInformation.IPGlobalProperties> metod klasy w połączeniu z <xref:System.Net.IPAddress.IsIPv6Teredo%2A> właściwością umożliwia aplikacji Łatwe znajdowanie adresu Teredo. Aplikacja zwykle musi znać lokalny adres Teredo, jeśli komunikuje się te informacje z aplikacjami zdalnymi. Na przykład aplikacja równorzędna może wysyłać wszystkie adresy IPv6 do serwera Matchmaking, który następnie przekazuje je do innych elementów równorzędnych w celu włączenia komunikacji bezpośredniej.  
  
 Aplikacja powinna zwykle ustawić nasłuchiwanie usługi nasłuchujących <xref:System.Net.IPAddress.IPv6Any?displayProperty=nameWithType> , a nie na lokalnym adresie Teredo. Dlatego jeśli Klient zdalny lub węzeł równorzędny mają bezpośrednią trasę IPv6 do hosta usługi nasłuchiwania, klient lub element równorzędny może połączyć się bezpośrednio przy użyciu protokołu IPv6 i nie musi używać protokołu Teredo do tunelowania pakietów.  
  
 W przypadku aplikacji TCP <xref:System.Net.Sockets.TcpListener?displayProperty=nameWithType> Klasa ma metodę umożliwiającą <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A> Przechodzenie translatora adresów sieciowych. W przypadku aplikacji UDP <xref:System.Net.Sockets.UdpClient?displayProperty=nameWithType> Klasa ma metodę umożliwiającą <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A> Przechodzenie translatora adresów sieciowych.  
  
 W przypadku aplikacji korzystających z <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> klas i pokrewnych <xref:System.Net.Sockets.Socket.GetSocketOption%2A> <xref:System.Net.Sockets.Socket.SetSocketOption%2A> metody i mogą być używane z <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType> opcją Socket, aby wysyłać zapytania, włączać lub wyłączać przechodzenie translatora adresów sieciowych.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=nameWithType>
- <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A?displayProperty=nameWithType>
- <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A?displayProperty=nameWithType>
- <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.SetIPProtectionLevel%2A?displayProperty=nameWithType>
- <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A?displayProperty=nameWithType>
- <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A?displayProperty=nameWithType>
