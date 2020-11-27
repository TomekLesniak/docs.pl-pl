---
title: Konwertowanie aplikacji NetTcpBinding na aplikację kanału równorzędnego
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: 5444b53f0373a2f2b06da680a53e8e5fa77d39b7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286737"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a><span data-ttu-id="320f9-102">Konwertowanie aplikacji NetTcpBinding na aplikację kanału równorzędnego</span><span class="sxs-lookup"><span data-stu-id="320f9-102">Converting a NetTcpBinding Application to a Peer Channel Application</span></span>

<span data-ttu-id="320f9-103">Można tworzyć połączenia między klientami przy użyciu programu WinFX przy użyciu powiązań, które opisują parametry połączenia.</span><span class="sxs-lookup"><span data-stu-id="320f9-103">You can create connections between clients using the WinFX by using bindings that describe the parameters of the connection.</span></span> <span data-ttu-id="320f9-104">Konwersja aplikacji .NET Framework na używanie połączeń równorzędnych wymaga powiązania, które obsługuje tę technologię podczas tworzenia połączeń z klientami.</span><span class="sxs-lookup"><span data-stu-id="320f9-104">Converting a .NET Framework application to use peer-to-peer connections requires a binding that supports this technology when making client connections.</span></span> <span data-ttu-id="320f9-105">Kanał równorzędny udostępnia powiązanie o nazwie <xref:System.ServiceModel.NetPeerTcpBinding> , którego można użyć w podobny sposób do <xref:System.ServiceModel.NetTcpBinding> .</span><span class="sxs-lookup"><span data-stu-id="320f9-105">Peer Channel provides a binding called <xref:System.ServiceModel.NetPeerTcpBinding>, which you can use in a similar way to the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="320f9-106">Kluczowe różnice obejmują określenie usługi rozpoznawania nazw i Definiowanie ustawień zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="320f9-106">Key differences include specifying a resolver service and defining security settings.</span></span>  
  
 <span data-ttu-id="320f9-107">Jeśli aplikacja używa domyślnych ustawień programu rozpoznawania nazw i zabezpieczeń, przekonwertowanie normalnej aplikacji opartej na kliencie/serwerze na korzystanie z kanału równorzędnego powoduje zmianę nazwy powiązania z "NetTcpBinding" na "NetPeerTcpBinding" w pliku konfiguracyjnym aplikacji — nie trzeba zmieniać bazy kodu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="320f9-107">If an application is using the default resolver and security settings, converting a normal client/server-based application to use Peer Channel entails changing the name of the binding from "NetTcpBinding" to "NetPeerTcpBinding" in the application’s configuration file—you do not have to change the application code base.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="320f9-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="320f9-108">See also</span></span>

- [<span data-ttu-id="320f9-109">Tworzenie aplikacji kanału równorzędnego</span><span class="sxs-lookup"><span data-stu-id="320f9-109">Building a Peer Channel Application</span></span>](building-a-peer-channel-application.md)
- [<span data-ttu-id="320f9-110">Wiązania dostarczane przez system</span><span class="sxs-lookup"><span data-stu-id="320f9-110">System-Provided Bindings</span></span>](../system-provided-bindings.md)
