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
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>Konwertowanie aplikacji NetTcpBinding na aplikację kanału równorzędnego

Można tworzyć połączenia między klientami przy użyciu programu WinFX przy użyciu powiązań, które opisują parametry połączenia. Konwersja aplikacji .NET Framework na używanie połączeń równorzędnych wymaga powiązania, które obsługuje tę technologię podczas tworzenia połączeń z klientami. Kanał równorzędny udostępnia powiązanie o nazwie <xref:System.ServiceModel.NetPeerTcpBinding> , którego można użyć w podobny sposób do <xref:System.ServiceModel.NetTcpBinding> . Kluczowe różnice obejmują określenie usługi rozpoznawania nazw i Definiowanie ustawień zabezpieczeń.  
  
 Jeśli aplikacja używa domyślnych ustawień programu rozpoznawania nazw i zabezpieczeń, przekonwertowanie normalnej aplikacji opartej na kliencie/serwerze na korzystanie z kanału równorzędnego powoduje zmianę nazwy powiązania z "NetTcpBinding" na "NetPeerTcpBinding" w pliku konfiguracyjnym aplikacji — nie trzeba zmieniać bazy kodu aplikacji.  
  
## <a name="see-also"></a>Zobacz też

- [Tworzenie aplikacji kanału równorzędnego](building-a-peer-channel-application.md)
- [Wiązania dostarczane przez system](../system-provided-bindings.md)
