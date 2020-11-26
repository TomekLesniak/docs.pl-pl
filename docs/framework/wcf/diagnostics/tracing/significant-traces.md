---
title: Ważne ślady
ms.date: 03/30/2017
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
ms.openlocfilehash: 9ad7c217b528cb2ad22169c1aea6391462bab1ae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248673"
---
# <a name="significant-traces"></a>Ważne ślady

Ten temat zawiera listę głównych śladów emitowanych przez Windows Communication Foundation (WCF).  
  
## <a name="significant-traces"></a>Ważne ślady  
  
|Ślad|Opis|  
|-----------|-----------------|  
|Śledzenie dziennika komunikatów|Ślad jest emitowany, gdy komunikat WCF jest rejestrowany przez funkcję rejestrowania komunikatów, gdy `System.ServiceModel.MessageLogging` Źródło śledzenia jest włączone. Kliknięcie tego śladu spowoduje wyświetlenie komunikatu. Istnieją cztery konfigurowalne punkty rejestrowania dla komunikatu:,,,, `ServiceLevelSendRequest` `TransportSend` `TransportReceive` `ServiceLevelReceiveRequest` również wskazywane przez atrybut źródła wiadomości w śladie dziennika komunikatów.|  
|Śledzenie odebrało komunikat|Ślad jest emitowany po odebraniu komunikatu WCF, gdy `System.ServiceModel` Źródło śledzenia jest włączone na poziomie informacji lub szczegółowości. Ten ślad jest niezbędny do wyświetlenia strzałki korelacji komunikatów w widoku wykresu aktywności.|  
|Komunikat wysłany do śledzenia|Ślad jest emitowany, gdy jest wysyłany komunikat WCF, jeśli `System.ServiceModel` Źródło śledzenia jest włączone na poziomie informacji lub szczegółowości. Ten ślad jest niezbędny do wyświetlenia strzałki korelacji komunikatów w widoku wykresu aktywności.|  
|Pobierz ChannelEndpointElement|Ten ślad jest emitowany w fabryce kanału konstruowania, na poziomie informacji. Zawiera opis punktu końcowego, z którym rozmawia klient (adres zdalny, powiązanie, nazwa kontraktu).|  
|Pobierzelement usługi|Ten ślad jest emitowany w ramach konstrukcji hosta usługi na poziomie informacji. Zawiera opis kontraktu i powiązania usługi.|  
|SocketConnection Utwórz|Ten ślad jest emitowany podczas pierwszej akcji procesu wykonywanej przez klienta i w działaniu odbierania bajtów w usłudze. Zapewnia lokalne i zdalne adresy IP. Jest emitowany na poziomie informacji.|
