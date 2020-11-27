---
title: Program WCF i technologia WebSockets
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: 2ee27eef015ee8c2fbee8360b444343a1c757097
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281589"
---
# <a name="wcf-and-websockets"></a>Program WCF i technologia WebSockets

.NET Framework 4,5 wprowadza obsługę obiektów WebSockets w Windows Communication Foundation.  Obiekty WebSockets to wydajna technologia oparta na standardach, która umożliwia komunikację dwukierunkową za pośrednictwem standardowych portów HTTP 80 i 443. Użycie standardowych portów HTTP umożliwia komunikację między składnikami sieci Web za pośrednictwem pośredników.  Dodano dwa nowe powiązania standardowe do obsługi komunikacji przy użyciu protokołu WebSocket. <xref:System.ServiceModel.NetHttpBinding> i <xref:System.ServiceModel.NetHttpsBinding> . Ustawienia specyficzne dla obiektów WebSockets można skonfigurować w <xref:System.ServiceModel.Channels.HttpTransportBindingElement> programie, uzyskując dostęp do <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> właściwości.
  
## <a name="in-this-section"></a>W tej sekcji  

 [Używanie elementu NetHttpBinding](using-the-nethttpbinding.md)  
 W tym artykule omówiono <xref:System.ServiceModel.NetHttpBinding> i sposób konfigurowania tego programu.  
  
 [Instrukcje: tworzenie usługi WCF komunikującej się przez protokół WebSockets](how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 Opisuje sposób tworzenia usługi WCF, która komunikuje się za pośrednictwem obiektów WebSockets.  
  
## <a name="reference"></a>Dokumentacja  
  
## <a name="related-sections"></a>Sekcje pokrewne
