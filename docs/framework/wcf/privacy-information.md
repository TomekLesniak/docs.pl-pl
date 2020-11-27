---
title: Informacje o prywatności dotyczące architektury WCF (Windows Communication Foundation)
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, privacy information
- WCF, privacy information
- privacy information [WCF]
ms.assetid: c9553724-f3e7-45cb-9ea5-450a22d309d9
ms.openlocfilehash: 5ecd1c39a4ad6a146c734aab8349c5caa4212662
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249946"
---
# <a name="windows-communication-foundation-privacy-information"></a><span data-ttu-id="f1553-102">Informacje o prywatności dotyczące architektury WCF (Windows Communication Foundation)</span><span class="sxs-lookup"><span data-stu-id="f1553-102">Windows Communication Foundation Privacy Information</span></span>

<span data-ttu-id="f1553-103">Firma Microsoft jest zobowiązana do ochrony prywatności użytkowników końcowych.</span><span class="sxs-lookup"><span data-stu-id="f1553-103">Microsoft is committed to protecting end user privacy.</span></span> <span data-ttu-id="f1553-104">W przypadku kompilowania aplikacji przy użyciu programu Windows Communication Foundation (WCF) w wersji 3,0 Aplikacja może mieć wpływ na prywatność użytkowników końcowych.</span><span class="sxs-lookup"><span data-stu-id="f1553-104">When you build an application using Windows Communication Foundation (WCF), version 3.0, your application may impact your end users' privacy.</span></span> <span data-ttu-id="f1553-105">Na przykład aplikacja może jawnie zbierać informacje kontaktowe użytkownika lub może zażądać lub wysłać informacje przesyłane przez Internet do witryny sieci Web.</span><span class="sxs-lookup"><span data-stu-id="f1553-105">For example, your application may explicitly collect user contact information, or it may request or send information over the Internet to your Web site.</span></span> <span data-ttu-id="f1553-106">Jeśli osadzisz technologię firmy Microsoft w aplikacji, ta technologia może mieć własne zachowanie, które może mieć wpływ na prywatność.</span><span class="sxs-lookup"><span data-stu-id="f1553-106">If you embed Microsoft technology in your application, that technology may have its own behavior that might affect privacy.</span></span> <span data-ttu-id="f1553-107">Usługa WCF nie wysyła żadnych informacji do firmy Microsoft z aplikacji, chyba że użytkownik lub użytkownik końcowy zdecyduje się wysłać do nas.</span><span class="sxs-lookup"><span data-stu-id="f1553-107">WCF does not send any information to Microsoft from your application unless you or the end user choose to send it to us.</span></span>  
  
## <a name="wcf-in-brief"></a><span data-ttu-id="f1553-108">WCF w skrócie</span><span class="sxs-lookup"><span data-stu-id="f1553-108">WCF in Brief</span></span>  

 <span data-ttu-id="f1553-109">WCF to dystrybuowana struktura obsługi komunikatów przy użyciu platformy Microsoft .NET, która umożliwia deweloperom tworzenie aplikacji rozproszonych.</span><span class="sxs-lookup"><span data-stu-id="f1553-109">WCF is a distributed messaging framework using the Microsoft .NET Framework that allows developers to build distributed applications.</span></span> <span data-ttu-id="f1553-110">Komunikaty przesyłane między dwiema aplikacjami zawierają informacje o nagłówku i treści.</span><span class="sxs-lookup"><span data-stu-id="f1553-110">Messages communicated between two applications contain header and body information.</span></span>  
  
 <span data-ttu-id="f1553-111">Nagłówki mogą zawierać routing wiadomości, informacje o zabezpieczeniach, transakcje i wiele więcej w zależności od usług używanych przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="f1553-111">Headers may contain message routing, security information, transactions, and more depending on the services used by the application.</span></span> <span data-ttu-id="f1553-112">Komunikaty są zwykle szyfrowane domyślnie.</span><span class="sxs-lookup"><span data-stu-id="f1553-112">Messages are typically encrypted by default.</span></span> <span data-ttu-id="f1553-113">Jedynym wyjątkiem jest użycie `BasicHttpBinding` , który został zaprojektowany do użycia z niezabezpieczonymi, starszymi usługami sieci Web.</span><span class="sxs-lookup"><span data-stu-id="f1553-113">The one exception is when using the `BasicHttpBinding`, which was designed for use with non-secured, legacy Web services.</span></span> <span data-ttu-id="f1553-114">Jako projektant aplikacji jest odpowiedzialny za końcowy projekt.</span><span class="sxs-lookup"><span data-stu-id="f1553-114">As the application designer, you are responsible for the final design.</span></span> <span data-ttu-id="f1553-115">Komunikaty w treści protokołu SOAP zawierają dane specyficzne dla aplikacji; Jednak te dane, takie jak zdefiniowane przez aplikację dane osobowe, mogą być chronione przy użyciu funkcji szyfrowania lub poufności programu WCF.</span><span class="sxs-lookup"><span data-stu-id="f1553-115">Messages in the SOAP body contain application-specific data; however, this data, such as application-defined personal information, can be secured by using WCF encryption or confidentiality features.</span></span> <span data-ttu-id="f1553-116">W poniższych sekcjach opisano funkcje, które mogą mieć wpływ na prywatność.</span><span class="sxs-lookup"><span data-stu-id="f1553-116">The following sections describe the features that potentially impact privacy.</span></span>  
  
## <a name="messaging"></a><span data-ttu-id="f1553-117">Obsługa wiadomości</span><span class="sxs-lookup"><span data-stu-id="f1553-117">Messaging</span></span>  

 <span data-ttu-id="f1553-118">Każdy komunikat WCF ma nagłówek adresu, który określa miejsce docelowe wiadomości i miejsce, w którym odpowiedź powinna zostać wysłana.</span><span class="sxs-lookup"><span data-stu-id="f1553-118">Each WCF message has an address header that specifies the message destination and where the reply should go.</span></span>  
  
 <span data-ttu-id="f1553-119">Składnik adresu punktu końcowego jest Uniform Resource Identifier (URI), który identyfikuje punkt końcowy.</span><span class="sxs-lookup"><span data-stu-id="f1553-119">The address component of an endpoint address is a Uniform Resource Identifier (URI) that identifies the endpoint.</span></span> <span data-ttu-id="f1553-120">Adres może być adresem sieciowym lub adresem logicznym.</span><span class="sxs-lookup"><span data-stu-id="f1553-120">The address can be a network address or a logical address.</span></span> <span data-ttu-id="f1553-121">Adres może zawierać nazwę komputera (nazwa hosta, w pełni kwalifikowaną nazwę domeny) i adres IP.</span><span class="sxs-lookup"><span data-stu-id="f1553-121">The address may include machine name (hostname, fully qualified domain name) and an IP address.</span></span> <span data-ttu-id="f1553-122">Adres punktu końcowego może również zawierać unikatowy identyfikator globalny (GUID) lub kolekcję identyfikatorów GUID do tymczasowego adresowania służącego do rozpoznać każdego adresu.</span><span class="sxs-lookup"><span data-stu-id="f1553-122">The endpoint address may also contain a globally unique identifier (GUID), or a collection of GUIDs for temporary addressing used to discern each address.</span></span> <span data-ttu-id="f1553-123">Każdy komunikat zawiera identyfikator, który jest identyfikatorem GUID.</span><span class="sxs-lookup"><span data-stu-id="f1553-123">Each message contains a message ID that is a GUID.</span></span> <span data-ttu-id="f1553-124">Ta funkcja jest zgodna ze standardem referencyjnym WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="f1553-124">This feature follows the WS-Addressing reference standard.</span></span>  
  
 <span data-ttu-id="f1553-125">Warstwa obsługi komunikatów WCF nie zapisuje żadnych danych osobowych na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="f1553-125">The WCF messaging layer does not write any personal information to the local machine.</span></span> <span data-ttu-id="f1553-126">Jednak może ona propagować dane osobowe na poziomie sieci, jeśli deweloper usługi utworzył usługę, która udostępnia takie informacje (na przykład przy użyciu nazwy osoby w nazwie punktu końcowego lub w tym informacje osobiste w Web Services Description Language punktu końcowego, ale nie wymaga od klientów używania protokołu HTTPS w celu uzyskania dostępu do języka WSDL).</span><span class="sxs-lookup"><span data-stu-id="f1553-126">However, it might propagate personal information at the network level if a service developer has created a service that exposes such information (for example, by using a person's name in an endpoint name, or including personal information in the endpoint's Web Services Description Language but not requiring clients to use https to access the WSDL).</span></span> <span data-ttu-id="f1553-127">Ponadto, jeśli deweloper uruchamia narzędzie do obsługi [metadanych ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) dla punktu końcowego, który ujawnia informacje osobiste, dane wyjściowe narzędzia mogą zawierać te informacje, a plik wyjściowy jest zapisywana na lokalnym dysku twardym.</span><span class="sxs-lookup"><span data-stu-id="f1553-127">Also, if a developer runs the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) tool against an endpoint that exposes personal information, the tool's output could contain that information, and the output file is written to the local hard disk.</span></span>  
  
## <a name="hosting"></a><span data-ttu-id="f1553-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="f1553-128">Hosting</span></span>  

 <span data-ttu-id="f1553-129">Funkcja hostingu w programie WCF umożliwia uruchamianie aplikacji na żądanie lub Włączanie udostępniania portów między wieloma aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="f1553-129">The hosting feature in WCF allows applications to start on demand or to enable port sharing between multiple applications.</span></span> <span data-ttu-id="f1553-130">Aplikacja WCF może być hostowana w Internet Information Services (IIS), podobnie jak ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f1553-130">A WCF application can be hosted in Internet Information Services (IIS), similar to ASP.NET.</span></span>  
  
 <span data-ttu-id="f1553-131">Hosting nie ujawnia żadnych określonych informacji w sieci i nie przechowuje danych na komputerze.</span><span class="sxs-lookup"><span data-stu-id="f1553-131">Hosting does not expose any specific information on the network and it does not keep data on the machine.</span></span>  
  
## <a name="message-security"></a><span data-ttu-id="f1553-132">Zabezpieczenia komunikatów</span><span class="sxs-lookup"><span data-stu-id="f1553-132">Message Security</span></span>  

 <span data-ttu-id="f1553-133">Zabezpieczenia WCF zapewniają funkcje zabezpieczeń dla aplikacji do obsługi komunikatów.</span><span class="sxs-lookup"><span data-stu-id="f1553-133">WCF security provides the security capabilities for messaging applications.</span></span> <span data-ttu-id="f1553-134">Dostępne funkcje zabezpieczeń obejmują uwierzytelnianie i autoryzację.</span><span class="sxs-lookup"><span data-stu-id="f1553-134">The security functions provided include authentication and authorization.</span></span>  
  
 <span data-ttu-id="f1553-135">Uwierzytelnianie jest wykonywane przez przekazywanie poświadczeń między klientami i usługami.</span><span class="sxs-lookup"><span data-stu-id="f1553-135">Authentication is performed by passing credentials between the clients and services.</span></span> <span data-ttu-id="f1553-136">Uwierzytelnianie może należeć przez zabezpieczenia na poziomie transportu lub przez zabezpieczenia na poziomie komunikatów protokołu SOAP w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="f1553-136">Authentication can be either through transport-level security or through SOAP message-level security, as follows:</span></span>  
  
- <span data-ttu-id="f1553-137">W zabezpieczeniach protokołu SOAP uwierzytelnianie odbywa się za pośrednictwem poświadczeń, takich jak nazwa użytkownika/hasła, certyfikaty X. 509, bilety protokołu Kerberos i tokeny SAML, które mogą zawierać informacje osobiste, w zależności od wystawcy.</span><span class="sxs-lookup"><span data-stu-id="f1553-137">In SOAP message security, authentication is performed through credentials like username/passwords, X.509 certificates, Kerberos tickets, and SAML tokens, all of which might contain personal information, depending on the issuer.</span></span>  
  
- <span data-ttu-id="f1553-138">Korzystając z zabezpieczeń transportu, uwierzytelnianie odbywa się za pośrednictwem tradycyjnych mechanizmów uwierzytelniania transportowego, takich jak schematy uwierzytelniania HTTP (podstawowe, szyfrowane, negocjowanie, zintegrowane uwierzytelnianie systemu Windows, uwierzytelnianie NTLM, brak i anonimowe).</span><span class="sxs-lookup"><span data-stu-id="f1553-138">Using transport security, authentication is done through traditional transport authentication mechanisms like HTTP authentication schemes (Basic, Digest, Negotiate, Integrated Windows Authorization, NTLM, None, and Anonymous), and form authentication.</span></span>  
  
 <span data-ttu-id="f1553-139">Uwierzytelnianie może spowodować ustanowienie bezpiecznej sesji między komunikującymi się punktami końcowymi.</span><span class="sxs-lookup"><span data-stu-id="f1553-139">Authentication can result in a secure session established between the communicating endpoints.</span></span> <span data-ttu-id="f1553-140">Sesja jest identyfikowana przez identyfikator GUID, który jest okresem istnienia sesji zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="f1553-140">The session is identified by a GUID that lasts the lifetime of the security session.</span></span> <span data-ttu-id="f1553-141">W poniższej tabeli przedstawiono informacje o zachowaniu i miejscu.</span><span class="sxs-lookup"><span data-stu-id="f1553-141">The following table shows what is kept and where.</span></span>  
  
|<span data-ttu-id="f1553-142">Dane</span><span class="sxs-lookup"><span data-stu-id="f1553-142">Data</span></span>|<span data-ttu-id="f1553-143">Storage</span><span class="sxs-lookup"><span data-stu-id="f1553-143">Storage</span></span>|  
|----------|-------------|  
|<span data-ttu-id="f1553-144">Poświadczenia prezentacji, takie jak nazwa użytkownika, certyfikaty X. 509, tokeny protokołu Kerberos i odwołania do poświadczeń.</span><span class="sxs-lookup"><span data-stu-id="f1553-144">Presentation credentials, such as username, X.509 certificates, Kerberos tokens, and references to credentials.</span></span>|<span data-ttu-id="f1553-145">Standardowe mechanizmy zarządzania poświadczeniami systemu Windows, takie jak magazyn certyfikatów systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="f1553-145">Standard Windows credential management mechanisms such as the Windows certificate store.</span></span>|  
|<span data-ttu-id="f1553-146">Informacje o członkostwie użytkowników, takie jak nazwy użytkowników i hasła.</span><span class="sxs-lookup"><span data-stu-id="f1553-146">User membership information, such as usernames and passwords.</span></span>|<span data-ttu-id="f1553-147">ASP.NET dostawcy członkostwa.</span><span class="sxs-lookup"><span data-stu-id="f1553-147">ASP.NET membership providers.</span></span>|  
|<span data-ttu-id="f1553-148">Informacje o tożsamości dotyczące usługi używanej do uwierzytelniania usługi dla klientów.</span><span class="sxs-lookup"><span data-stu-id="f1553-148">Identity information about the service used to authenticate the service to clients.</span></span>|<span data-ttu-id="f1553-149">Adres punktu końcowego usługi.</span><span class="sxs-lookup"><span data-stu-id="f1553-149">Endpoint address of the service.</span></span>|  
|<span data-ttu-id="f1553-150">Informacje o obiekcie wywołującym.</span><span class="sxs-lookup"><span data-stu-id="f1553-150">Caller information.</span></span>|<span data-ttu-id="f1553-151">Dzienniki inspekcji.</span><span class="sxs-lookup"><span data-stu-id="f1553-151">Auditing logs.</span></span>|  
  
## <a name="auditing"></a><span data-ttu-id="f1553-152">Inspekcja</span><span class="sxs-lookup"><span data-stu-id="f1553-152">Auditing</span></span>  

 <span data-ttu-id="f1553-153">Inspekcja rejestruje sukces i niepowodzenie uwierzytelniania i zdarzeń autoryzacji.</span><span class="sxs-lookup"><span data-stu-id="f1553-153">Auditing records the success and failure of authentication and authorization events.</span></span> <span data-ttu-id="f1553-154">Rekordy inspekcji zawierają następujące dane: identyfikator URI usługi, identyfikator URI akcji i identyfikator obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="f1553-154">Auditing records contain the following data: service URI, action URI, and the caller's identification.</span></span>  
  
 <span data-ttu-id="f1553-155">Inspekcja jest rejestrowana także wtedy, gdy administrator modyfikuje konfigurację rejestrowania komunikatów (Włączanie lub wyłączanie), ponieważ rejestrowanie komunikatów może rejestrować dane specyficzne dla aplikacji w nagłówkach i treściach.</span><span class="sxs-lookup"><span data-stu-id="f1553-155">Auditing also records when the administrator modifies the configuration of message logging (turning it on or off), because message logging may log application-specific data in headers and bodies.</span></span> <span data-ttu-id="f1553-156">W przypadku systemu Windows XP rekord jest rejestrowany w dzienniku zdarzeń aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f1553-156">For Windows XP, a record is logged in the application event log.</span></span> <span data-ttu-id="f1553-157">W systemach Windows Vista i Windows Server 2003 rekord jest rejestrowany w dzienniku zdarzeń zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="f1553-157">For Windows Vista and Windows Server 2003, a record is logged in the security event log.</span></span>  
  
## <a name="transactions"></a><span data-ttu-id="f1553-158">Transakcje</span><span class="sxs-lookup"><span data-stu-id="f1553-158">Transactions</span></span>  

 <span data-ttu-id="f1553-159">Funkcja transakcji zapewnia usługi transakcyjne w aplikacji WCF.</span><span class="sxs-lookup"><span data-stu-id="f1553-159">The transactions feature provides transactional services to a WCF application.</span></span>  
  
 <span data-ttu-id="f1553-160">Nagłówki transakcji używane w propagacji transakcji mogą zawierać identyfikatory transakcji lub identyfikatory rejestracji, które są identyfikatorami GUID.</span><span class="sxs-lookup"><span data-stu-id="f1553-160">Transaction headers used in transaction propagation may contain Transaction IDs or Enlistment IDs, which are GUIDs.</span></span>  
  
 <span data-ttu-id="f1553-161">Funkcja transakcji używa programu Microsoft Distributed Transaction Coordinator (MSDTC) Transaction Manager (składnik systemu Windows) do zarządzania stanem transakcji.</span><span class="sxs-lookup"><span data-stu-id="f1553-161">The Transactions feature uses the Microsoft Distributed Transaction Coordinator (MSDTC) Transaction Manager (a Windows component) to manage transaction state.</span></span> <span data-ttu-id="f1553-162">Domyślnie komunikacja między menedżerami transakcji jest zaszyfrowana.</span><span class="sxs-lookup"><span data-stu-id="f1553-162">By default, communications between Transactions Managers are encrypted.</span></span> <span data-ttu-id="f1553-163">Menedżerowie transakcji mogą rejestrować odwołania punktów końcowych, identyfikatory transakcji i identyfikatory rejestracji w ramach ich trwałego stanu.</span><span class="sxs-lookup"><span data-stu-id="f1553-163">Transaction Managers may log endpoint references, Transaction IDs, and Enlistment IDs as part of their durable state.</span></span> <span data-ttu-id="f1553-164">Okres istnienia tego stanu zależy od okresu istnienia pliku dziennika Menedżera transakcji.</span><span class="sxs-lookup"><span data-stu-id="f1553-164">The lifetime of this state is determined by the lifetime of the Transaction Manager’s log file.</span></span> <span data-ttu-id="f1553-165">Usługa MSDTC jest własnością i utrzymuje ten dziennik.</span><span class="sxs-lookup"><span data-stu-id="f1553-165">The MSDTC service owns and maintains this log.</span></span>  
  
 <span data-ttu-id="f1553-166">Funkcja transakcji implementuje standardy transakcji WS-Coordination i WS-Atomic.</span><span class="sxs-lookup"><span data-stu-id="f1553-166">The Transactions feature implements the WS-Coordination and WS-Atomic Transaction standards.</span></span>  
  
## <a name="reliable-sessions"></a><span data-ttu-id="f1553-167">Niezawodne sesje</span><span class="sxs-lookup"><span data-stu-id="f1553-167">Reliable Sessions</span></span>  

 <span data-ttu-id="f1553-168">Niezawodne sesje w programie WCF zapewniają transfer komunikatów w przypadku wystąpienia niepowodzeń transportu lub pośrednika.</span><span class="sxs-lookup"><span data-stu-id="f1553-168">Reliable sessions in WCF provide the transfer of messages when transport or intermediary failures occur.</span></span> <span data-ttu-id="f1553-169">Zapewniają one dokładnie jeden raz transfer komunikatów, nawet gdy podstawowy transport rozłącza się (na przykład połączenie TCP w sieci bezprzewodowej) lub utraci komunikat (serwer proxy HTTP porzuca komunikat wychodzący lub przychodzący).</span><span class="sxs-lookup"><span data-stu-id="f1553-169">They provide an exactly-once transfer of messages even when the underlying transport disconnects (for example, a TCP connection on a wireless network) or loses a message (an HTTP proxy dropping an outgoing or incoming message).</span></span> <span data-ttu-id="f1553-170">Niezawodne sesje również odnoszą się do zmiany kolejności komunikatów (mogą wystąpić w przypadku routingu wielościeżkowego), zachowując kolejność przesyłania komunikatów.</span><span class="sxs-lookup"><span data-stu-id="f1553-170">Reliable sessions also recover message reordering (as may happen in the case of multipath routing), preserving the order in which the messages were sent.</span></span>  
  
 <span data-ttu-id="f1553-171">Niezawodne sesje są implementowane przy użyciu protokołu WS-ReliableMessaging (WS-RM).</span><span class="sxs-lookup"><span data-stu-id="f1553-171">Reliable sessions are implemented using the WS-ReliableMessaging (WS-RM) protocol.</span></span> <span data-ttu-id="f1553-172">Dodają nagłówki WS-RM zawierające informacje o sesji, które służą do identyfikowania wszystkich komunikatów skojarzonych z określoną niezawodną sesją.</span><span class="sxs-lookup"><span data-stu-id="f1553-172">They add WS-RM headers that contain session information, which is used to identify all messages associated with a particular reliable session.</span></span> <span data-ttu-id="f1553-173">Każda sesja WS-RM ma identyfikator, który jest identyfikatorem GUID.</span><span class="sxs-lookup"><span data-stu-id="f1553-173">Each WS-RM session has an identifier, which is a GUID.</span></span>  
  
 <span data-ttu-id="f1553-174">Na komputerze użytkownika końcowego nie są przechowywane żadne informacje osobiste.</span><span class="sxs-lookup"><span data-stu-id="f1553-174">No personal information is retained on the end user's machine.</span></span>  
  
## <a name="queued-channels"></a><span data-ttu-id="f1553-175">Kanały w kolejce</span><span class="sxs-lookup"><span data-stu-id="f1553-175">Queued Channels</span></span>  

 <span data-ttu-id="f1553-176">Kolejki przechowują wiadomości z aplikacji wysyłającej w imieniu aplikacji odbiorczej, a następnie przesyłają je dalej do aplikacji odbiorczej.</span><span class="sxs-lookup"><span data-stu-id="f1553-176">Queues store messages from a sending application on behalf of a receiving application and later forward these messages to the receiving application.</span></span> <span data-ttu-id="f1553-177">Mogą one pomóc w zapewnieniu przesyłania komunikatów wysyłanych do aplikacji, gdy na przykład aplikacja do odbioru jest przejściowa.</span><span class="sxs-lookup"><span data-stu-id="f1553-177">They help ensure the transfer of messages from sending applications to receiving applications when, for example, the receiving application is transient.</span></span> <span data-ttu-id="f1553-178">Usługa WCF zapewnia obsługę kolejkowania przy użyciu usługi kolejkowania komunikatów (MSMQ) firmy Microsoft jako transportu.</span><span class="sxs-lookup"><span data-stu-id="f1553-178">WCF provides support for queuing by using Microsoft Message Queuing (MSMQ) as a transport.</span></span>  
  
 <span data-ttu-id="f1553-179">Funkcja kanałów umieszczonych w kolejce nie dodaje nagłówków do wiadomości.</span><span class="sxs-lookup"><span data-stu-id="f1553-179">The queued channels feature does not add headers to a message.</span></span> <span data-ttu-id="f1553-180">Zamiast tego tworzy komunikat usługi kolejkowania komunikatów z odpowiednimi właściwościami komunikatów usługi kolejkowania komunikatów i wywołuje metody usługi kolejkowania komunikatów, aby umieścić komunikat w kolejce usługi kolejkowania komunikatów.</span><span class="sxs-lookup"><span data-stu-id="f1553-180">Instead it creates a Message Queuing message with appropriate Message Queuing message properties set, and invokes Message Queuing methods to put the message in the Message Queuing queue.</span></span> <span data-ttu-id="f1553-181">Usługa kolejkowania komunikatów jest opcjonalnym składnikiem dostarczanym z systemem Windows.</span><span class="sxs-lookup"><span data-stu-id="f1553-181">Message Queuing is an optional component that ships with Windows.</span></span>  
  
 <span data-ttu-id="f1553-182">Funkcja kanałów umieszczonych w kolejce nie zachowuje żadnych informacji na komputerze użytkownika końcowego, ponieważ używa usługi kolejkowania komunikatów jako infrastruktury kolejkowania.</span><span class="sxs-lookup"><span data-stu-id="f1553-182">No information is retained on the end user's machine by the queued channels feature, because it uses Message Queuing as the queuing infrastructure.</span></span>  
  
## <a name="com-integration"></a><span data-ttu-id="f1553-183">Integracja modelu COM+</span><span class="sxs-lookup"><span data-stu-id="f1553-183">COM+ Integration</span></span>  

 <span data-ttu-id="f1553-184">Ta funkcja otacza istniejące funkcje COM i COM+ w celu tworzenia usług zgodnych z usługami WCF.</span><span class="sxs-lookup"><span data-stu-id="f1553-184">This feature wraps existing COM and COM+ functionality to create services that are compatible with WCF services.</span></span> <span data-ttu-id="f1553-185">Ta funkcja nie korzysta z określonych nagłówków i nie przechowuje danych na komputerze użytkownika końcowego.</span><span class="sxs-lookup"><span data-stu-id="f1553-185">This feature does not use specific headers and it does not retain data on the end user's machine.</span></span>  
  
## <a name="com-service-moniker"></a><span data-ttu-id="f1553-186">Moniker usługi COM</span><span class="sxs-lookup"><span data-stu-id="f1553-186">COM Service Moniker</span></span>  

 <span data-ttu-id="f1553-187">Zapewnia to niezarządzaną otokę dla standardowego klienta WCF.</span><span class="sxs-lookup"><span data-stu-id="f1553-187">This provides an unmanaged wrapper to a standard WCF client.</span></span> <span data-ttu-id="f1553-188">Ta funkcja nie ma określonych nagłówków w sieci ani nie utrzymuje danych na komputerze.</span><span class="sxs-lookup"><span data-stu-id="f1553-188">This feature does not have specific headers on the wire nor does it persist data on the machine.</span></span>  
  
## <a name="peer-channel"></a><span data-ttu-id="f1553-189">Kanał elementu równorzędnego</span><span class="sxs-lookup"><span data-stu-id="f1553-189">Peer Channel</span></span>  

 <span data-ttu-id="f1553-190">Kanał równorzędny umożliwia programowanie aplikacji wieloczęściowych przy użyciu programu WCF.</span><span class="sxs-lookup"><span data-stu-id="f1553-190">A peer channel enables development of multiparty applications using WCF.</span></span> <span data-ttu-id="f1553-191">Obsługa komunikatów wieloczęściowych odbywa się w kontekście siatki.</span><span class="sxs-lookup"><span data-stu-id="f1553-191">Multiparty messaging occurs in the context of a mesh.</span></span> <span data-ttu-id="f1553-192">Siatki są identyfikowane przez nazwę, którą mogą przyłączać węzły.</span><span class="sxs-lookup"><span data-stu-id="f1553-192">Meshes are identified by a name that nodes can join.</span></span> <span data-ttu-id="f1553-193">Każdy węzeł w kanale równorzędnym tworzy odbiornik TCP na porcie określonym przez użytkownika i ustanawia połączenia z innymi węzłami w siatce w celu zapewnienia odporności.</span><span class="sxs-lookup"><span data-stu-id="f1553-193">Each node in the peer channel creates a TCP listener at a user-specified port and establishes connections with other nodes in the mesh to ensure resiliency.</span></span> <span data-ttu-id="f1553-194">Aby nawiązać połączenie z innymi węzłami w sieci, węzły również wymieniają pewne dane, w tym adres odbiornika i adresy IP maszyny, z innymi węzłami w sieci.</span><span class="sxs-lookup"><span data-stu-id="f1553-194">To connect to other nodes in the mesh, nodes also exchange some data, including the listener address and the machine's IP addresses, with other nodes in the mesh.</span></span> <span data-ttu-id="f1553-195">Komunikaty wysyłane w siatce mogą zawierać informacje o zabezpieczeniach, które odnoszą się do nadawcy, aby zapobiec fałszowaniu i manipulowaniu wiadomościami.</span><span class="sxs-lookup"><span data-stu-id="f1553-195">Messages sent around in the mesh can contain security information that pertains to the sender to prevent message spoofing and tampering.</span></span>  
  
 <span data-ttu-id="f1553-196">Na komputerze użytkownika końcowego nie są przechowywane żadne informacje osobiste.</span><span class="sxs-lookup"><span data-stu-id="f1553-196">No personal information is stored on the end user's machine.</span></span>  
  
## <a name="it-professional-experience"></a><span data-ttu-id="f1553-197">Specjalista IT</span><span class="sxs-lookup"><span data-stu-id="f1553-197">IT Professional Experience</span></span>  
  
### <a name="tracing"></a><span data-ttu-id="f1553-198">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="f1553-198">Tracing</span></span>  

 <span data-ttu-id="f1553-199">Funkcja diagnostyki infrastruktury WCF rejestruje komunikaty przekazywane przez warstwy transportu i modelu usług oraz działania i zdarzenia skojarzone z tymi komunikatami.</span><span class="sxs-lookup"><span data-stu-id="f1553-199">The diagnostics feature of the WCF infrastructure logs messages that pass through the transport and service model layers, and the activities and events associated with these messages.</span></span> <span data-ttu-id="f1553-200">Ta funkcja jest domyślnie wyłączona.</span><span class="sxs-lookup"><span data-stu-id="f1553-200">This feature is turned off by default.</span></span> <span data-ttu-id="f1553-201">Jest on włączony przy użyciu pliku konfiguracji aplikacji, a zachowanie śledzenia może być modyfikowane przy użyciu dostawcy WMI usługi WCF w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="f1553-201">It is enabled using the application’s configuration file and the tracing behavior may be modified using the WCF WMI provider at run time.</span></span> <span data-ttu-id="f1553-202">Po włączeniu infrastruktury śledzenia emituje śledzenie diagnostyczne zawierające komunikaty, działania i zdarzenia przetwarzania do skonfigurowanych odbiorników.</span><span class="sxs-lookup"><span data-stu-id="f1553-202">When enabled, the tracing infrastructure emits a diagnostic trace that contains messages, activities, and processing events to configured listeners.</span></span> <span data-ttu-id="f1553-203">Format i lokalizacja danych wyjściowych są określane przez opcje konfiguracji odbiorników administratora, ale zazwyczaj jest to plik w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="f1553-203">The format and location of the output are determined by the administrator’s listener configuration choices, but is typically an XML formatted file.</span></span> <span data-ttu-id="f1553-204">Administrator jest odpowiedzialny za ustawianie listy kontroli dostępu (ACL) dla plików śledzenia.</span><span class="sxs-lookup"><span data-stu-id="f1553-204">The administrator is responsible for setting the access control list (ACL) on the trace files.</span></span> <span data-ttu-id="f1553-205">W szczególności, gdy jest obsługiwany przez system aktywacji systemu Windows (WAS), administrator powinien upewnić się, że pliki nie są obsługiwane z publicznego wirtualnego katalogu głównego, jeśli nie jest to potrzebne.</span><span class="sxs-lookup"><span data-stu-id="f1553-205">In particular, when hosted by Windows Activation System (WAS), the administrator should make sure the files are not served from the public virtual root directory if that is not desired.</span></span>  
  
 <span data-ttu-id="f1553-206">Istnieją dwa typy śledzenia: rejestrowanie komunikatów i śledzenie diagnostyki modelu usług, opisane w następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="f1553-206">There are two types of tracing: Message logging and Service Model diagnostic tracing, described in the following section.</span></span> <span data-ttu-id="f1553-207">Każdy typ jest konfigurowany przy użyciu własnego źródła śledzenia: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> i <xref:System.ServiceModel> .</span><span class="sxs-lookup"><span data-stu-id="f1553-207">Each type is configured through its own trace source: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> and <xref:System.ServiceModel>.</span></span> <span data-ttu-id="f1553-208">Oba te źródła śledzenia rejestrowania przechwytują dane, które są lokalne dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f1553-208">Both of these logging trace sources capture data that is local to the application.</span></span>  
  
### <a name="message-logging"></a><span data-ttu-id="f1553-209">Rejestrowanie komunikatów</span><span class="sxs-lookup"><span data-stu-id="f1553-209">Message Logging</span></span>  

 <span data-ttu-id="f1553-210">Źródło śledzenia rejestrowania komunikatów ( <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> ) umożliwia administratorowi zarejestrowanie komunikatów przesyłanych przez system.</span><span class="sxs-lookup"><span data-stu-id="f1553-210">The message logging trace source (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) allows an administrator to log the messages that flow through the system.</span></span> <span data-ttu-id="f1553-211">Za pomocą konfiguracji użytkownik może zdecydować się na zarejestrowanie całych komunikatów lub tylko nagłówków wiadomości, tylko to, czy należy rejestrować warstwy transportu i/lub modelu usług oraz czy mają być uwzględniane źle sformułowane komunikaty.</span><span class="sxs-lookup"><span data-stu-id="f1553-211">Through configuration, the user may decide to log entire messages or message headers only, whether to log at the transport and/or service model layers, and whether to include malformed messages.</span></span> <span data-ttu-id="f1553-212">Ponadto użytkownik może skonfigurować filtrowanie, aby ograniczyć liczbę rejestrowanych komunikatów.</span><span class="sxs-lookup"><span data-stu-id="f1553-212">Also, the user may configure filtering to restrict which messages are logged.</span></span>  
  
 <span data-ttu-id="f1553-213">Domyślnie rejestrowanie komunikatów jest wyłączone.</span><span class="sxs-lookup"><span data-stu-id="f1553-213">By default, message logging is disabled.</span></span> <span data-ttu-id="f1553-214">Administrator komputera lokalnego może uniemożliwić administratorowi na poziomie aplikacji włączenie rejestrowania komunikatów.</span><span class="sxs-lookup"><span data-stu-id="f1553-214">The local machine administrator can prevent the application-level administrator from turning message logging on.</span></span>  
  
#### <a name="encrypted-and-decrypted-message-logging"></a><span data-ttu-id="f1553-215">Rejestrowanie zaszyfrowanych i odszyfrowanych komunikatów</span><span class="sxs-lookup"><span data-stu-id="f1553-215">Encrypted and Decrypted Message Logging</span></span>  

 <span data-ttu-id="f1553-216">Komunikaty są rejestrowane, szyfrowane lub odszyfrowywane, zgodnie z opisem w poniższych warunkach.</span><span class="sxs-lookup"><span data-stu-id="f1553-216">Messages are logged, encrypted, or decrypted, as described in the following terms.</span></span>  
  
 <span data-ttu-id="f1553-217">Rejestrowanie transportu</span><span class="sxs-lookup"><span data-stu-id="f1553-217">Transport Logging</span></span>  
 <span data-ttu-id="f1553-218">Rejestruje komunikaty odebrane i wysłane na poziomie transportu.</span><span class="sxs-lookup"><span data-stu-id="f1553-218">Logs messages received and sent at the transport level.</span></span> <span data-ttu-id="f1553-219">Te komunikaty zawierają wszystkie nagłówki i mogą być szyfrowane przed wysłaniem do sieci i w momencie odebrania.</span><span class="sxs-lookup"><span data-stu-id="f1553-219">These messages contain all headers, and may be encrypted before being sent on the wire and when being received.</span></span>  
  
 <span data-ttu-id="f1553-220">Jeśli komunikaty są szyfrowane przed wysłaniem do sieci, a po ich odebraniu są one zaszyfrowane.</span><span class="sxs-lookup"><span data-stu-id="f1553-220">If messages are encrypted before being sent on the wire and when they are received, they are logged encrypted as well.</span></span> <span data-ttu-id="f1553-221">Wyjątek polega na tym, że jest używany protokół zabezpieczeń (https): są one następnie rejestrowane przed wysłaniem i po odebraniu, nawet jeśli są szyfrowane w sieci.</span><span class="sxs-lookup"><span data-stu-id="f1553-221">An exception is when a security protocol is used (https): they are then logged decrypted before being sent and after being received even if they are encrypted on the wire.</span></span>  
  
 <span data-ttu-id="f1553-222">Rejestrowanie usługi</span><span class="sxs-lookup"><span data-stu-id="f1553-222">Service Logging</span></span>  
 <span data-ttu-id="f1553-223">Rejestruje komunikaty odebrane lub wysłane na poziomie modelu usługi, po przetworzeniu nagłówka kanału, tuż przed wprowadzeniem kodu użytkownika i po nim.</span><span class="sxs-lookup"><span data-stu-id="f1553-223">Logs messages received or sent at the service model level, after channel header processing has occurred, just before and after entering user code.</span></span>  
  
 <span data-ttu-id="f1553-224">Komunikaty zarejestrowane na tym poziomie są odszyfrowywane, nawet jeśli zostały zabezpieczone i zaszyfrowane w sieci.</span><span class="sxs-lookup"><span data-stu-id="f1553-224">Messages logged at this level are decrypted even if they were secured and encrypted on the wire.</span></span>  
  
 <span data-ttu-id="f1553-225">Źle sformułowane rejestrowanie komunikatów</span><span class="sxs-lookup"><span data-stu-id="f1553-225">Malformed Message Logging</span></span>  
 <span data-ttu-id="f1553-226">Rejestruje komunikaty, które nie mogą zrozumieć lub przetworzyć Infrastruktura WCF.</span><span class="sxs-lookup"><span data-stu-id="f1553-226">Logs messages that the WCF infrastructure cannot understand or process.</span></span>  
  
 <span data-ttu-id="f1553-227">Komunikaty są rejestrowane jako-is, czyli szyfrowane lub nie</span><span class="sxs-lookup"><span data-stu-id="f1553-227">Messages are logged as-is, that is, encrypted or not</span></span>  
  
 <span data-ttu-id="f1553-228">Gdy wiadomości są rejestrowane w postaci odszyfrowanej lub niezaszyfrowanej, domyślnie program WCF usuwa klucze zabezpieczeń i potencjalnie dane osobowe z komunikatów przed ich zarejestrowaniem.</span><span class="sxs-lookup"><span data-stu-id="f1553-228">When messages are logged in decrypted or unencrypted form, by default WCF removes security keys and potentially personal information from the messages before logging them.</span></span> <span data-ttu-id="f1553-229">W następnych sekcjach opisano, jakie informacje są usuwane i kiedy.</span><span class="sxs-lookup"><span data-stu-id="f1553-229">The next sections describe what information is removed, and when.</span></span> <span data-ttu-id="f1553-230">Aby zmienić domyślne zachowanie kluczy dziennika i potencjalnie informacji osobistych, administrator maszyny i narzędzie wdrażania aplikacji muszą wykonać pewne czynności konfiguracyjne.</span><span class="sxs-lookup"><span data-stu-id="f1553-230">The machine administrator and application deployer must both take certain configuration actions to change the default behavior to log keys and potentially personal information.</span></span>  
  
#### <a name="information-removed-from-message-headers-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="f1553-231">Informacje usunięte z nagłówków komunikatów podczas rejestrowania odszyfrowanych/nieszyfrowanych wiadomości</span><span class="sxs-lookup"><span data-stu-id="f1553-231">Information Removed from Message Headers When Logging Decrypted/Unencrypted Messages</span></span>  

 <span data-ttu-id="f1553-232">Gdy wiadomości są rejestrowane w postaci odszyfrowanej/nieszyfrowanej, klucze zabezpieczeń i potencjalnie dane osobowe są domyślnie usuwane z nagłówków wiadomości i treści wiadomości przed ich zarejestrowaniem.</span><span class="sxs-lookup"><span data-stu-id="f1553-232">When messages are logged in decrypted/unencrypted form, security keys and potentially personal information are removed by default from message headers and message bodies before they are logged.</span></span> <span data-ttu-id="f1553-233">Na poniższej liście przedstawiono, co usługa WCF traktuje klucze i potencjalnie dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="f1553-233">The following list shows what WCF considers keys and potentially personal information.</span></span>  
  
 <span data-ttu-id="f1553-234">Usunięte klucze:</span><span class="sxs-lookup"><span data-stu-id="f1553-234">Keys that are removed:</span></span>  
  
 <span data-ttu-id="f1553-235">\- Dla xmlns: wst = " http://schemas.xmlsoap.org/ws/2004/04/trust " i xmlns: wst = " http://schemas.xmlsoap.org/ws/2005/02/trust "</span><span class="sxs-lookup"><span data-stu-id="f1553-235">\- For xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"</span></span>  
  
 <span data-ttu-id="f1553-236">wst:BinarySecret</span><span class="sxs-lookup"><span data-stu-id="f1553-236">wst:BinarySecret</span></span>  
  
 <span data-ttu-id="f1553-237">wst: Entropia</span><span class="sxs-lookup"><span data-stu-id="f1553-237">wst:Entropy</span></span>  
  
 <span data-ttu-id="f1553-238">\- Dla xmlns: WSSE = " http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd " i xmlns: WSSE = " http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd "</span><span class="sxs-lookup"><span data-stu-id="f1553-238">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="f1553-239">wsse: hasło</span><span class="sxs-lookup"><span data-stu-id="f1553-239">wsse:Password</span></span>  
  
 <span data-ttu-id="f1553-240">wsse: Identyfikator jednorazowy</span><span class="sxs-lookup"><span data-stu-id="f1553-240">wsse:Nonce</span></span>  
  
 <span data-ttu-id="f1553-241">Potencjalnie usunięte informacje osobiste:</span><span class="sxs-lookup"><span data-stu-id="f1553-241">Potentially personal information that is removed:</span></span>  
  
 <span data-ttu-id="f1553-242">\- Dla xmlns: WSSE = " http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd " i xmlns: WSSE = " http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd "</span><span class="sxs-lookup"><span data-stu-id="f1553-242">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="f1553-243">wsse: Nazwa użytkownika</span><span class="sxs-lookup"><span data-stu-id="f1553-243">wsse:Username</span></span>  
  
 <span data-ttu-id="f1553-244">wsse:BinarySecurityToken</span><span class="sxs-lookup"><span data-stu-id="f1553-244">wsse:BinarySecurityToken</span></span>  
  
 <span data-ttu-id="f1553-245">\- Dla xmlns: SAML = "urn: języka Oasis: names: TC: SAML: 1.0: Assertion" usuwane są elementy pogrubione (poniżej):</span><span class="sxs-lookup"><span data-stu-id="f1553-245">\- For xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" the items in bold (below) are removed:</span></span>  
  
 <span data-ttu-id="f1553-246">\<Asercja</span><span class="sxs-lookup"><span data-stu-id="f1553-246">\<Assertion</span></span>  
  
 <span data-ttu-id="f1553-247">MajorVersion = "1"</span><span class="sxs-lookup"><span data-stu-id="f1553-247">MajorVersion="1"</span></span>  
  
 <span data-ttu-id="f1553-248">MinorVersion = "1"</span><span class="sxs-lookup"><span data-stu-id="f1553-248">MinorVersion="1"</span></span>  
  
 <span data-ttu-id="f1553-249">AssertionId = "[ID]"</span><span class="sxs-lookup"><span data-stu-id="f1553-249">AssertionId="[ID]"</span></span>  
  
 <span data-ttu-id="f1553-250">Issuer = "[ciąg]"</span><span class="sxs-lookup"><span data-stu-id="f1553-250">Issuer="[string]"</span></span>  
  
 <span data-ttu-id="f1553-251">IssueInstant = "[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="f1553-251">IssueInstant="[dateTime]"</span></span>  
  
 >  
  
 \<Conditions NotBefore="[dateTime]" NotOnOrAfter="[dateTime]">  
  
 \<AudienceRestrictionCondition>  
  
 <span data-ttu-id="f1553-252">\<Audience>adresu\</Audience>+</span><span class="sxs-lookup"><span data-stu-id="f1553-252">\<Audience>[uri]\</Audience>+</span></span>  
  
 \</AudienceRestrictionCondition>*  
  
 \<DoNotCacheCondition />*  
  
 <span data-ttu-id="f1553-253"><\!--abstrakcyjny typ podstawowy</span><span class="sxs-lookup"><span data-stu-id="f1553-253"><\!-- abstract base type</span></span>  
  
 \<Condition />*  
  
 -->  
  
 <span data-ttu-id="f1553-254">\</Conditions>?</span><span class="sxs-lookup"><span data-stu-id="f1553-254">\</Conditions>?</span></span>  
  
 \<Advice>  
  
 <span data-ttu-id="f1553-255">\<AssertionIDReference>#C1\</AssertionIDReference>\*</span><span class="sxs-lookup"><span data-stu-id="f1553-255">\<AssertionIDReference>[ID]\</AssertionIDReference>\*</span></span>  
  
 <span data-ttu-id="f1553-256">\<Assertion>twierdz\</Assertion>\*</span><span class="sxs-lookup"><span data-stu-id="f1553-256">\<Assertion>[assertion]\</Assertion>\*</span></span>  
  
 <span data-ttu-id="f1553-257">[any] \*</span><span class="sxs-lookup"><span data-stu-id="f1553-257">[any]\*</span></span>  
  
 <span data-ttu-id="f1553-258">\</Advice>?</span><span class="sxs-lookup"><span data-stu-id="f1553-258">\</Advice>?</span></span>  
  
 <span data-ttu-id="f1553-259"><\!--Abstrakcyjne typy podstawowe</span><span class="sxs-lookup"><span data-stu-id="f1553-259"><\!-- Abstract base types</span></span>  
  
 \<Statement />*  
  
 \<SubjectStatement>  
  
 \<Subject>  
  
 `<NameIdentifier`  
  
 `NameQualifier="[string]"?`  
  
 `Format="[uri]"?`  
  
 `>`  
  
 `[string]`  
  
 `</NameIdentifier>?`  
  
 \<SubjectConfirmation>  
  
 <span data-ttu-id="f1553-260">\<ConfirmationMethod>AnyUri\</ConfirmationMethod>+</span><span class="sxs-lookup"><span data-stu-id="f1553-260">\<ConfirmationMethod>[anyUri]\</ConfirmationMethod>+</span></span>  
  
 <span data-ttu-id="f1553-261">\<SubjectConfirmationData>[any] \</SubjectConfirmationData> ?</span><span class="sxs-lookup"><span data-stu-id="f1553-261">\<SubjectConfirmationData>[any]\</SubjectConfirmationData>?</span></span>  
  
 <span data-ttu-id="f1553-262">\<ds:KeyInfo>...\</ds:KeyInfo>?</span><span class="sxs-lookup"><span data-stu-id="f1553-262">\<ds:KeyInfo>...\</ds:KeyInfo>?</span></span>  
  
 <span data-ttu-id="f1553-263">\</SubjectConfirmation>?</span><span class="sxs-lookup"><span data-stu-id="f1553-263">\</SubjectConfirmation>?</span></span>  
  
 \</Subject>  
  
 \</SubjectStatement>*  
  
 -->  
  
 <span data-ttu-id="f1553-264">\<AuthenticationStatement</span><span class="sxs-lookup"><span data-stu-id="f1553-264">\<AuthenticationStatement</span></span>  
  
 <span data-ttu-id="f1553-265">Wartość uwierzytelniania = "[URI]"</span><span class="sxs-lookup"><span data-stu-id="f1553-265">AuthenticationMethod="[uri]"</span></span>  
  
 <span data-ttu-id="f1553-266">AuthenticationInstant = "[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="f1553-266">AuthenticationInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="f1553-267">Dawane</span><span class="sxs-lookup"><span data-stu-id="f1553-267">[Subject]</span></span>  
  
 `<SubjectLocality`  
  
 `IPAddress="[string]"?`  
  
 `DNSAddress="[string]"?`  
  
 `/>?`  
  
 <span data-ttu-id="f1553-268"><AuthorityBinding</span><span class="sxs-lookup"><span data-stu-id="f1553-268"><AuthorityBinding</span></span>  
  
 <span data-ttu-id="f1553-269">AuthorityKind = "[QName]"</span><span class="sxs-lookup"><span data-stu-id="f1553-269">AuthorityKind="[QName]"</span></span>  
  
 <span data-ttu-id="f1553-270">Location = "[URI]"</span><span class="sxs-lookup"><span data-stu-id="f1553-270">Location="[uri]"</span></span>  
  
 <span data-ttu-id="f1553-271">Binding = "[URI]"</span><span class="sxs-lookup"><span data-stu-id="f1553-271">Binding="[uri]"</span></span>  
  
 />*  
  
 \</AuthenticationStatement>*  
  
 \<AttributeStatement>  
  
 <span data-ttu-id="f1553-272">Dawane</span><span class="sxs-lookup"><span data-stu-id="f1553-272">[Subject]</span></span>  
  
 <span data-ttu-id="f1553-273">\<Atrybut</span><span class="sxs-lookup"><span data-stu-id="f1553-273">\<Attribute</span></span>  
  
 <span data-ttu-id="f1553-274">AttributeName = "[ciąg]"</span><span class="sxs-lookup"><span data-stu-id="f1553-274">AttributeName="[string]"</span></span>  
  
 <span data-ttu-id="f1553-275">AttributeNamespace = "[URI]"</span><span class="sxs-lookup"><span data-stu-id="f1553-275">AttributeNamespace="[uri]"</span></span>  
  
 >  
  
 `<AttributeValue>[any]</AttributeValue>+`  
  
 \</Attribute>+  
  
 \</AttributeStatement>*  
  
 <span data-ttu-id="f1553-276">\<AuthorizationDecisionStatement</span><span class="sxs-lookup"><span data-stu-id="f1553-276">\<AuthorizationDecisionStatement</span></span>  
  
 <span data-ttu-id="f1553-277">Zasób = "[URI]"</span><span class="sxs-lookup"><span data-stu-id="f1553-277">Resource="[uri]"</span></span>  
  
 <span data-ttu-id="f1553-278">Decyzja = "[Zezwalaj&#124;Odmów&#124;nieokreślone]"</span><span class="sxs-lookup"><span data-stu-id="f1553-278">Decision="[Permit&#124;Deny&#124;Indeterminate]"</span></span>  
  
 >  
  
 <span data-ttu-id="f1553-279">Dawane</span><span class="sxs-lookup"><span data-stu-id="f1553-279">[Subject]</span></span>  
  
 <span data-ttu-id="f1553-280">\<Action Namespace="[uri]">parametry\</Action>+</span><span class="sxs-lookup"><span data-stu-id="f1553-280">\<Action Namespace="[uri]">[string]\</Action>+</span></span>  
  
 \<Evidence>  
  
 <span data-ttu-id="f1553-281">\<AssertionIDReference>#C1\</AssertionIDReference>+</span><span class="sxs-lookup"><span data-stu-id="f1553-281">\<AssertionIDReference>[ID]\</AssertionIDReference>+</span></span>  
  
 <span data-ttu-id="f1553-282">\<Assertion>twierdz\</Assertion>+</span><span class="sxs-lookup"><span data-stu-id="f1553-282">\<Assertion>[assertion]\</Assertion>+</span></span>  
  
 <span data-ttu-id="f1553-283">\</Evidence>?</span><span class="sxs-lookup"><span data-stu-id="f1553-283">\</Evidence>?</span></span>  
  
 \</AuthorizationDecisionStatement>*  
  
 \</Assertion>  
  
#### <a name="information-removed-from-message-bodies-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="f1553-284">Informacje usunięte z treści komunikatów podczas rejestrowania odszyfrowanych/nieszyfrowanych wiadomości</span><span class="sxs-lookup"><span data-stu-id="f1553-284">Information Removed from Message Bodies When Logging Decrypted/Unencrypted Messages</span></span>  

 <span data-ttu-id="f1553-285">Jak opisano wcześniej, usługa WCF usuwa klucze i znane potencjalnie dane osobowe z nagłówków komunikatów dla rejestrowanych, odszyfrowanych/nieszyfrowanych wiadomości.</span><span class="sxs-lookup"><span data-stu-id="f1553-285">As previously described, WCF removes keys and known potentially personal information from message headers for logged decrypted/unencrypted messages.</span></span> <span data-ttu-id="f1553-286">Ponadto WCF usuwa klucze i znane potencjalnie dane osobowe z treści wiadomości dla elementów treści i działań na poniższej liście, które opisują komunikaty zabezpieczeń związane z wymianą kluczy.</span><span class="sxs-lookup"><span data-stu-id="f1553-286">In addition, WCF removes keys and known potentially personal information from message bodies for the body elements and actions in the following list, which describe security messages involved in key exchange.</span></span>  
  
 <span data-ttu-id="f1553-287">Dla następujących przestrzeni nazw:</span><span class="sxs-lookup"><span data-stu-id="f1553-287">For the following namespaces:</span></span>  
  
 <span data-ttu-id="f1553-288">xmlns: wst = " http://schemas.xmlsoap.org/ws/2004/04/trust " i xmlns: wst = " http://schemas.xmlsoap.org/ws/2005/02/trust " (na przykład jeśli żadna akcja nie jest dostępna)</span><span class="sxs-lookup"><span data-stu-id="f1553-288">xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" (for example, if no action available)</span></span>  
  
 <span data-ttu-id="f1553-289">Informacje są usuwane dla tych elementów treści, które obejmują wymianę kluczy:</span><span class="sxs-lookup"><span data-stu-id="f1553-289">Information is removed for these body elements, which involve key exchange:</span></span>  
  
 <span data-ttu-id="f1553-290">wst: RequestSecurityToken</span><span class="sxs-lookup"><span data-stu-id="f1553-290">wst:RequestSecurityToken</span></span>  
  
 <span data-ttu-id="f1553-291">wst: RequestSecurityTokenResponse</span><span class="sxs-lookup"><span data-stu-id="f1553-291">wst:RequestSecurityTokenResponse</span></span>  
  
 <span data-ttu-id="f1553-292">wst: RequestSecurityTokenResponsecollection</span><span class="sxs-lookup"><span data-stu-id="f1553-292">wst:RequestSecurityTokenResponseCollection</span></span>  
  
 <span data-ttu-id="f1553-293">Informacje są również usuwane dla każdej z następujących akcji:</span><span class="sxs-lookup"><span data-stu-id="f1553-293">Information is also removed for each of the following Actions:</span></span>  
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT-Amend`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT-Amend`
  
#### <a name="no-information-is-removed-from-application-specific-headers-and-body-data"></a><span data-ttu-id="f1553-294">Żadne informacje nie są usuwane z nagłówków i danych treści specyficznych dla aplikacji</span><span class="sxs-lookup"><span data-stu-id="f1553-294">No Information Is Removed from Application-specific Headers and Body Data</span></span>  

 <span data-ttu-id="f1553-295">Funkcja WCF nie śledzi informacji osobistych w nagłówkach specyficznych dla aplikacji (na przykład ciągi zapytań) ani danych treści (na przykład numeru karty kredytowej).</span><span class="sxs-lookup"><span data-stu-id="f1553-295">WCF does not track personal information in application-specific headers (for example, query strings) or body data (for example, credit card number).</span></span>  
  
 <span data-ttu-id="f1553-296">Po włączeniu rejestrowania komunikatów informacje osobiste w nagłówkach i informacjach o treściach specyficznych dla aplikacji mogą być widoczne w dziennikach.</span><span class="sxs-lookup"><span data-stu-id="f1553-296">When message logging is on, personal information in application-specific headers and body information may be visible in the logs.</span></span> <span data-ttu-id="f1553-297">Ponownie program wdrażania aplikacji jest odpowiedzialny za ustawianie list kontroli dostępu w plikach konfiguracji i dziennika.</span><span class="sxs-lookup"><span data-stu-id="f1553-297">Again, the application deployer is responsible for setting the ACLs on the configuration and log files.</span></span> <span data-ttu-id="f1553-298">Mogą oni również wyłączyć rejestrowanie, jeśli nie chcą, aby te informacje były widoczne, lub odfiltrować te informacje z plików dziennika po ich zarejestrowaniu.</span><span class="sxs-lookup"><span data-stu-id="f1553-298">They also can turn off logging if they don't want this information to be visible, or filter out this information from the log files after it is logged.</span></span>  
  
### <a name="service-model-tracing"></a><span data-ttu-id="f1553-299">Śledzenie modelu usług</span><span class="sxs-lookup"><span data-stu-id="f1553-299">Service Model Tracing</span></span>  

 <span data-ttu-id="f1553-300">Źródło śledzenia modelu usług ( <xref:System.ServiceModel> ) umożliwia śledzenie działań i zdarzeń związanych z przetwarzaniem komunikatów.</span><span class="sxs-lookup"><span data-stu-id="f1553-300">The Service Model trace source (<xref:System.ServiceModel>) enables tracing of activities and events related to message processing.</span></span> <span data-ttu-id="f1553-301">Ta funkcja używa funkcji diagnostyki .NET Framework z programu <xref:System.Diagnostics> .</span><span class="sxs-lookup"><span data-stu-id="f1553-301">This feature uses the .NET Framework diagnostic functionality from <xref:System.Diagnostics>.</span></span> <span data-ttu-id="f1553-302">Podobnie jak w przypadku <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> właściwości, lokalizacja i jej lista kontroli dostępu są konfigurowane przez użytkownika przy użyciu .NET Framework plików konfiguracji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f1553-302">As with the <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> property, the location and its ACL are user-configurable using .NET Framework application configuration files.</span></span> <span data-ttu-id="f1553-303">Podobnie jak w przypadku rejestrowania komunikatów, lokalizacja pliku jest zawsze konfigurowana, gdy administrator włączy śledzenie; w tym celu administrator kontroluje listę ACL.</span><span class="sxs-lookup"><span data-stu-id="f1553-303">As with message logging, the file location is always configured when the administrator enables tracing; thus, the administrator controls the ACL.</span></span>  
  
 <span data-ttu-id="f1553-304">Ślady zawierają nagłówki wiadomości, gdy komunikat jest w zakresie.</span><span class="sxs-lookup"><span data-stu-id="f1553-304">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="f1553-305">Te same reguły ukrywania potencjalnie osobistych informacji w nagłówkach wiadomości w poprzedniej sekcji dotyczą: informacje osobiste zidentyfikowane wcześniej są usuwane domyślnie z nagłówków śledzenia.</span><span class="sxs-lookup"><span data-stu-id="f1553-305">The same rules for hiding potentially personal information in message headers in the previous section apply: the personal information previously identified is removed by default from the headers in traces.</span></span> <span data-ttu-id="f1553-306">Zarówno administrator komputera, jak i narzędzie wdrażania aplikacji muszą zmodyfikować konfigurację, aby rejestrować potencjalnie dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="f1553-306">Both the machine administrator and the application deployer must modify the configuration in order to log potentially personal information.</span></span> <span data-ttu-id="f1553-307">Jednak dane osobowe zawarte w nagłówkach specyficznych dla aplikacji są rejestrowane w śladach.</span><span class="sxs-lookup"><span data-stu-id="f1553-307">However, personal information contained in application-specific headers is logged in traces.</span></span> <span data-ttu-id="f1553-308">Narzędzie wdrażania aplikacji jest odpowiedzialne za ustawianie list kontroli dostępu dla plików konfiguracji i śledzenia.</span><span class="sxs-lookup"><span data-stu-id="f1553-308">The application deployer is responsible for setting the ACLs on the configuration and trace files.</span></span> <span data-ttu-id="f1553-309">Mogą również wyłączyć śledzenie, aby ukryć te informacje lub odfiltrować te informacje z plików śledzenia po ich zarejestrowaniu.</span><span class="sxs-lookup"><span data-stu-id="f1553-309">They can also turn off tracing to hide this information or filter out this information from the trace files after it's logged.</span></span>  
  
 <span data-ttu-id="f1553-310">W ramach śledzenia ServiceModel, unikatowe identyfikatory (nazywane identyfikatorami aktywności i zazwyczaj identyfikator GUID) łączą różne działania wraz z przepływem komunikatów przez różne części infrastruktury.</span><span class="sxs-lookup"><span data-stu-id="f1553-310">As part of ServiceModel Tracing, Unique IDs (called Activity IDs, and typically a GUID) link different activities together as a message flows through different parts of the infrastructure.</span></span>  
  
#### <a name="custom-trace-listeners"></a><span data-ttu-id="f1553-311">Niestandardowa odbiorniki śledzenia</span><span class="sxs-lookup"><span data-stu-id="f1553-311">Custom Trace Listeners</span></span>  

 <span data-ttu-id="f1553-312">W przypadku rejestrowania i śledzenia komunikatów można skonfigurować odbiornik niestandardowego śledzenia, który może wysyłać ślady i komunikaty w sieci (na przykład do zdalnej bazy danych).</span><span class="sxs-lookup"><span data-stu-id="f1553-312">For both message logging and tracing, a custom trace listener can be configured, which can send traces and messages on the wire (for example, to a remote database).</span></span> <span data-ttu-id="f1553-313">Narzędzie wdrażania aplikacji jest odpowiedzialne za konfigurowanie odbiorników niestandardowych lub umożliwienie użytkownikom wykonania tej czynności.</span><span class="sxs-lookup"><span data-stu-id="f1553-313">The application deployer is responsible for configuring custom listeners or enabling users to do so.</span></span> <span data-ttu-id="f1553-314">Są one również odpowiedzialne za wszystkie dane osobowe ujawniane w lokalizacji zdalnej oraz odpowiednie stosowanie list ACL do tej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="f1553-314">They are also responsible for any personal information exposed at the remote location and for properly applying ACLs to this location.</span></span>  
  
### <a name="other-features-for-it-professionals"></a><span data-ttu-id="f1553-315">Inne funkcje dla specjalistów IT</span><span class="sxs-lookup"><span data-stu-id="f1553-315">Other features for IT Professionals</span></span>  

 <span data-ttu-id="f1553-316">Program WCF ma dostawcę WMI, który uwidacznia informacje o konfiguracji infrastruktury WCF za pomocą usługi WMI (dostarczanej z systemem Windows).</span><span class="sxs-lookup"><span data-stu-id="f1553-316">WCF has a WMI provider that exposes the WCF infrastructure configuration information through WMI (shipped with Windows).</span></span> <span data-ttu-id="f1553-317">Domyślnie interfejs usługi WMI jest dostępny dla administratorów.</span><span class="sxs-lookup"><span data-stu-id="f1553-317">By default, the WMI interface is available to administrators.</span></span>  
  
 <span data-ttu-id="f1553-318">Konfiguracja usługi WCF używa mechanizmu konfiguracji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f1553-318">WCF configuration uses the .NET Framework configuration mechanism.</span></span> <span data-ttu-id="f1553-319">Pliki konfiguracji są przechowywane na komputerze.</span><span class="sxs-lookup"><span data-stu-id="f1553-319">The configuration files are stored on the machine.</span></span> <span data-ttu-id="f1553-320">Deweloper aplikacji i administrator tworzą pliki konfiguracji i listę ACL dla każdej z wymagań aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f1553-320">The application developer and the administrator create the configuration files and ACL for each of the application's requirements.</span></span> <span data-ttu-id="f1553-321">Plik konfiguracji może zawierać adresy punktów końcowych i linki do certyfikatów w magazynie certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="f1553-321">A configuration file can contain endpoint addresses and links to certificates in the certificate store.</span></span> <span data-ttu-id="f1553-322">Certyfikaty mogą służyć do dostarczania danych aplikacji w celu skonfigurowania różnych właściwości funkcji używanych przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="f1553-322">The certificates can be used to provide application data to configure various properties of the features used by the application.</span></span>  
  
 <span data-ttu-id="f1553-323">Funkcja WCF używa również funkcji zrzutów procesów .NET Framework, wywołując <xref:System.Environment.FailFast%2A> metodę.</span><span class="sxs-lookup"><span data-stu-id="f1553-323">WCF also uses the .NET Framework process dump functionality by calling the <xref:System.Environment.FailFast%2A> method.</span></span>  
  
### <a name="it-pro-tools"></a><span data-ttu-id="f1553-324">Narzędzia Pro IT</span><span class="sxs-lookup"><span data-stu-id="f1553-324">IT Pro Tools</span></span>  

 <span data-ttu-id="f1553-325">Usługa WCF udostępnia również następujące narzędzia profesjonalne, które są dostarczane w Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="f1553-325">WCF also provides the following IT professional tools, which ship in the Windows SDK.</span></span>  
  
#### <a name="svctraceviewerexe"></a><span data-ttu-id="f1553-326">SvcTraceViewer.exe</span><span class="sxs-lookup"><span data-stu-id="f1553-326">SvcTraceViewer.exe</span></span>  

 <span data-ttu-id="f1553-327">W podglądzie są wyświetlane pliki śledzenia WCF.</span><span class="sxs-lookup"><span data-stu-id="f1553-327">The viewer displays WCF trace files.</span></span> <span data-ttu-id="f1553-328">Podgląd pokazuje, jakie informacje są zawarte w śladach.</span><span class="sxs-lookup"><span data-stu-id="f1553-328">The viewer shows whatever information is contained in the traces.</span></span>  
  
#### <a name="svcconfigeditorexe"></a><span data-ttu-id="f1553-329">SvcConfigEditor.exe</span><span class="sxs-lookup"><span data-stu-id="f1553-329">SvcConfigEditor.exe</span></span>  

 <span data-ttu-id="f1553-330">Edytor umożliwia użytkownikowi tworzenie i edytowanie plików konfiguracji WCF.</span><span class="sxs-lookup"><span data-stu-id="f1553-330">The editor allows the user to create and edit WCF configuration files.</span></span> <span data-ttu-id="f1553-331">Edytor pokazuje, jakie informacje są zawarte w plikach konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="f1553-331">The editor shows whatever information is contained in the configuration files.</span></span> <span data-ttu-id="f1553-332">To samo zadanie można wykonać za pomocą edytora tekstu.</span><span class="sxs-lookup"><span data-stu-id="f1553-332">The same task can be accomplished with a text editor.</span></span>  
  
#### <a name="servicemodel_reg"></a><span data-ttu-id="f1553-333">ServiceModel_Reg</span><span class="sxs-lookup"><span data-stu-id="f1553-333">ServiceModel_Reg</span></span>  

 <span data-ttu-id="f1553-334">To narzędzie umożliwia użytkownikowi zarządzanie instalacjami ServiceModel na komputerze.</span><span class="sxs-lookup"><span data-stu-id="f1553-334">This tool allows the user to manage ServiceModel installs on a machine.</span></span> <span data-ttu-id="f1553-335">Narzędzie wyświetla komunikaty o stanie w oknie konsoli, gdy jest ono uruchomione, a w procesie może wyświetlać informacje o konfiguracji instalacji programu WCF.</span><span class="sxs-lookup"><span data-stu-id="f1553-335">The tool displays status messages in a console window when it runs and, in the process, may display information about the configuration of the WCF installation.</span></span>  
  
#### <a name="wsatconfigexe-and-wsatuidll"></a><span data-ttu-id="f1553-336">WSATConfig.exe i WSATUI.dll</span><span class="sxs-lookup"><span data-stu-id="f1553-336">WSATConfig.exe and WSATUI.dll</span></span>  

 <span data-ttu-id="f1553-337">Te narzędzia umożliwiają specjalistom IT konfigurowanie obsługi sieci WS-AtomicTransaction międzyoperacyjnych w programie WCF.</span><span class="sxs-lookup"><span data-stu-id="f1553-337">These tools allow IT Professionals to configure interoperable WS-AtomicTransaction network support in WCF.</span></span> <span data-ttu-id="f1553-338">Narzędzia wyświetlają i umożliwiają użytkownikowi zmianę wartości najczęściej używanych ustawień WS-AtomicTransaction przechowywanych w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="f1553-338">The tools display and allow the user to change the values of the most commonly used WS-AtomicTransaction settings stored in the registry.</span></span>  
  
## <a name="cross-cutting-features"></a><span data-ttu-id="f1553-339">Funkcje wycinania krzyżowego</span><span class="sxs-lookup"><span data-stu-id="f1553-339">Cross-cutting Features</span></span>  

 <span data-ttu-id="f1553-340">Następujące funkcje są krzyżowe.</span><span class="sxs-lookup"><span data-stu-id="f1553-340">The following features are cross-cutting.</span></span> <span data-ttu-id="f1553-341">Oznacza to, że mogą one składać się z dowolnej z powyższych funkcji.</span><span class="sxs-lookup"><span data-stu-id="f1553-341">That is, they can be composed with any of the preceding features.</span></span>  
  
### <a name="service-framework"></a><span data-ttu-id="f1553-342">Struktura usługi</span><span class="sxs-lookup"><span data-stu-id="f1553-342">Service Framework</span></span>  

 <span data-ttu-id="f1553-343">Nagłówki mogą zawierać identyfikator wystąpienia, który jest identyfikatorem GUID, który kojarzy komunikat z wystąpieniem klasy CLR.</span><span class="sxs-lookup"><span data-stu-id="f1553-343">Headers can contain an instance ID, which is a GUID that associates a message with an instance of a CLR class.</span></span>  
  
 <span data-ttu-id="f1553-344">Web Services Description Language (WSDL) zawiera definicję portu.</span><span class="sxs-lookup"><span data-stu-id="f1553-344">The Web Services Description Language (WSDL) contains a definition of the port.</span></span> <span data-ttu-id="f1553-345">Każdy port ma adres punktu końcowego i powiązanie, które reprezentuje usługi używane przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="f1553-345">Each port has an endpoint address and a binding that represents the services used by the application.</span></span> <span data-ttu-id="f1553-346">Uwidacznianie WSDL można wyłączyć za pomocą konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="f1553-346">Exposing WSDL can be turned off using configuration.</span></span> <span data-ttu-id="f1553-347">Na maszynie nie są przechowywane żadne informacje.</span><span class="sxs-lookup"><span data-stu-id="f1553-347">No information is retained on the machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1553-348">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f1553-348">See also</span></span>

- [<span data-ttu-id="f1553-349">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="f1553-349">Windows Communication Foundation</span></span>](index.md)
- [<span data-ttu-id="f1553-350">Bezpieczeństwo</span><span class="sxs-lookup"><span data-stu-id="f1553-350">Security</span></span>](./feature-details/security.md)
