---
title: Używanie gniazd klientów
description: Ten przykład pokazuje, jak utworzyć połączenie TCP/IP z usługą zdalną przy użyciu gniazda w .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- Socket class, client sockets
- protocols, sockets
- Internet, sockets
- sockets, client sockets
- client sockets
ms.assetid: 81de9f59-8177-4d98-b25d-43fc32a98383
ms.openlocfilehash: 6982d09c20cd0d7e9d27fc63880b39e0982c86ef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265196"
---
# <a name="using-client-sockets"></a><span data-ttu-id="ac15d-103">Używanie gniazd klientów</span><span class="sxs-lookup"><span data-stu-id="ac15d-103">Using Client Sockets</span></span>

<span data-ttu-id="ac15d-104">Aby można było zainicjować konwersację za pomocą programu <xref:System.Net.Sockets.Socket> , należy utworzyć potok danych między aplikacją a urządzeniem zdalnym.</span><span class="sxs-lookup"><span data-stu-id="ac15d-104">Before you can initiate a conversation through a <xref:System.Net.Sockets.Socket>, you must create a data pipe between your application and the remote device.</span></span> <span data-ttu-id="ac15d-105">Chociaż istnieją inne rodziny i protokoły adresów sieciowych, w tym przykładzie pokazano, jak utworzyć połączenie TCP/IP z usługą zdalną.</span><span class="sxs-lookup"><span data-stu-id="ac15d-105">Although other network address families and protocols exist, this example shows how to create a TCP/IP connection to a remote service.</span></span>  
  
 <span data-ttu-id="ac15d-106">Protokół TCP/IP używa adresu sieciowego i numeru portu usługi do unikatowego identyfikowania usługi.</span><span class="sxs-lookup"><span data-stu-id="ac15d-106">TCP/IP uses a network address and a service port number to uniquely identify a service.</span></span> <span data-ttu-id="ac15d-107">Adres sieciowy identyfikuje określone urządzenie w sieci; Numer portu identyfikuje konkretną usługę na tym urządzeniu, z którą ma zostać nawiązane połączenie.</span><span class="sxs-lookup"><span data-stu-id="ac15d-107">The network address identifies a specific device on the network; the port number identifies the specific service on that device to connect to.</span></span> <span data-ttu-id="ac15d-108">Kombinacja adresu sieciowego i portu usługi nosi nazwę punktu końcowego, który jest reprezentowany w .NET Framework przez <xref:System.Net.EndPoint> klasę.</span><span class="sxs-lookup"><span data-stu-id="ac15d-108">The combination of network address and service port is called an endpoint, which is represented in the .NET Framework by the <xref:System.Net.EndPoint> class.</span></span> <span data-ttu-id="ac15d-109">Element podrzędny **punktu końcowego** jest zdefiniowany dla każdej obsługiwanej rodziny adresów; w przypadku rodziny adresów IP Klasa jest <xref:System.Net.IPEndPoint> .</span><span class="sxs-lookup"><span data-stu-id="ac15d-109">A descendant of **EndPoint** is defined for each supported address family; for the IP address family, the class is <xref:System.Net.IPEndPoint>.</span></span>  
  
 <span data-ttu-id="ac15d-110"><xref:System.Net.Dns>Klasa zapewnia usługi nazw domen dla aplikacji, które korzystają z usług internetowych TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="ac15d-110">The <xref:System.Net.Dns> class provides domain-name services to applications that use TCP/IP Internet services.</span></span> <span data-ttu-id="ac15d-111"><xref:System.Net.Dns.Resolve%2A>Metoda wysyła zapytanie do serwera DNS w celu zamapowania przyjaznej dla użytkownika nazwy domeny (takiej jak "host.contoso.com") na liczbowy adres internetowy (na przykład 192.168.1.1).</span><span class="sxs-lookup"><span data-stu-id="ac15d-111">The <xref:System.Net.Dns.Resolve%2A> method queries a DNS server to map a user-friendly domain name (such as "host.contoso.com") to a numeric Internet address (such as 192.168.1.1).</span></span> <span data-ttu-id="ac15d-112">Funkcja **Rozwiązuj** zwraca element zawierający <xref:System.Net.IPHostEntry> listę adresów i aliasów dla żądanej nazwy.</span><span class="sxs-lookup"><span data-stu-id="ac15d-112">**Resolve** returns an <xref:System.Net.IPHostEntry> that contains a list of addresses and aliases for the requested name.</span></span> <span data-ttu-id="ac15d-113">W większości przypadków można użyć pierwszego adresu zwróconego w <xref:System.Net.IPHostEntry.AddressList%2A> tablicy.</span><span class="sxs-lookup"><span data-stu-id="ac15d-113">In most cases, you can use the first address returned in the <xref:System.Net.IPHostEntry.AddressList%2A> array.</span></span> <span data-ttu-id="ac15d-114">Poniższy kod pobiera <xref:System.Net.IPAddress> zawierający adres IP serwera Host.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ac15d-114">The following code gets an <xref:System.Net.IPAddress> containing the IP address for the server host.contoso.com.</span></span>  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 <span data-ttu-id="ac15d-115">Urząd IANA (Internet Assigned Numbers Authority) definiuje numery portów dla typowych usług (Aby uzyskać więcej informacji, zobacz [rejestr numerów portów i protokołów transportu](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)).</span><span class="sxs-lookup"><span data-stu-id="ac15d-115">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (for more information, see [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)).</span></span> <span data-ttu-id="ac15d-116">Inne usługi mogą mieć zarejestrowane numery portów z zakresu od 1 024 do 65 535.</span><span class="sxs-lookup"><span data-stu-id="ac15d-116">Other services can have registered port numbers in the range 1,024 to 65,535.</span></span> <span data-ttu-id="ac15d-117">Poniższy kod łączy adres IP host.contoso.com z numerem portu, aby utworzyć zdalny punkt końcowy dla połączenia.</span><span class="sxs-lookup"><span data-stu-id="ac15d-117">The following code combines the IP address for host.contoso.com with a port number to create a remote endpoint for a connection.</span></span>  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 <span data-ttu-id="ac15d-118">Po ustaleniu adresu urządzenia zdalnego i wybraniu portu do użycia w ramach połączenia aplikacja może próbować nawiązać połączenie z urządzeniem zdalnym.</span><span class="sxs-lookup"><span data-stu-id="ac15d-118">After determining the address of the remote device and choosing a port to use for the connection, the application can attempt to establish a connection with the remote device.</span></span> <span data-ttu-id="ac15d-119">Poniższy przykład używa istniejącej **IPEndPoint** do nawiązywania połączenia z urządzeniem zdalnym i przechwytuje wszystkie zgłoszone wyjątki.</span><span class="sxs-lookup"><span data-stu-id="ac15d-119">The following example uses an existing **IPEndPoint** to connect to a remote device and catches any exceptions that are thrown.</span></span>  
  
```vb  
Try  
    s.Connect(ipe)  
Catch ae As ArgumentNullException  
    Console.WriteLine("ArgumentNullException : {0}", _  
        ae.ToString())  
Catch se As SocketException  
    Console.WriteLine("SocketException : {0}", se.ToString())  
Catch e As Exception  
    Console.WriteLine("Unexpected exception : {0}", e.ToString())  
End Try  
```  
  
```csharp  
try {  
    s.Connect(ipe);  
} catch(ArgumentNullException ae) {  
    Console.WriteLine("ArgumentNullException : {0}", ae.ToString());  
} catch(SocketException se) {  
    Console.WriteLine("SocketException : {0}", se.ToString());  
} catch(Exception e) {  
    Console.WriteLine("Unexpected exception : {0}", e.ToString());  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac15d-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ac15d-120">See also</span></span>

- [<span data-ttu-id="ac15d-121">Używanie synchronicznego gniazda klienta</span><span class="sxs-lookup"><span data-stu-id="ac15d-121">Using a Synchronous Client Socket</span></span>](using-a-synchronous-client-socket.md)
- [<span data-ttu-id="ac15d-122">Używanie asynchronicznego gniazda klienta</span><span class="sxs-lookup"><span data-stu-id="ac15d-122">Using an Asynchronous Client Socket</span></span>](using-an-asynchronous-client-socket.md)
- [<span data-ttu-id="ac15d-123">Instrukcje: tworzenie gniazda</span><span class="sxs-lookup"><span data-stu-id="ac15d-123">How to: Create a Socket</span></span>](how-to-create-a-socket.md)
- [<span data-ttu-id="ac15d-124">Gniazda</span><span class="sxs-lookup"><span data-stu-id="ac15d-124">Sockets</span></span>](sockets.md)
