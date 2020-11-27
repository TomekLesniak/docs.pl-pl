---
title: Usługa routera odnajdywania
ms.date: 03/30/2017
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
ms.openlocfilehash: f3ea32d10e27eceb3edcee8b6aeacbf9c5ebc6f1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96292652"
---
# <a name="discovery-router-service"></a>Usługa routera odnajdywania

Ten przykład pokazuje, jak przekazywać komunikaty wykrywania do innego punktu końcowego.  
  
## <a name="demonstrates"></a>Demonstracje  

 Routing odnajdowania  
  
## <a name="discussion"></a>Dyskusja  

 Routing odnajdowania jest przydatny w scenariuszu, w którym klient szuka usługi przy użyciu serwera proxy, a serwer proxy nie wie o takiej usłudze, ale wie o innym serwerze proxy. Ten serwer proxy może przekazywać pakiet odnajdywania z tego klienta do drugiego serwera proxy. Drugi serwer proxy może wyszukać usługę i zwrócić odpowiedzi do oryginalnego klienta.  
  
 W tym przykładzie klient wysyła komunikat do składnika routingu odnajdowania. Ta wiadomość jest wysyłana do określonego punktu końcowego routera odnajdywania. Następnie router przekazuje komunikat do punktu końcowego multiemisji UDP. Komunikat sondy przechodzi do punktu końcowego multiemisji, a usługa nasłuchuje na adresie multiemisji UDP odpowiada na ten router odnajdowania. Router odnajdowania zbiera odpowiedzi i wysyła je z powrotem do klienta programu.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Aby skonfigurować, skompilować i uruchomić przykład  
  
1. Skompiluj przykład.  
  
2. Uruchom plik wykonywalny DiscoveryRouter.  
  
3. Uruchom plik wykonywalny usługi z katalogu kompilacji.  
  
4. Uruchom plik wykonywalny klienta. Należy zauważyć, że klient lokalizuje usługę.  
  
> [!IMPORTANT]
> Przykłady mogą być już zainstalowane na komputerze. Przed kontynuowaniem Wyszukaj następujący katalog (domyślny).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Jeśli ten katalog nie istnieje, przejdź do [przykładów Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) dla .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , aby pobrać wszystkie Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykłady. Ten przykład znajduje się w następującym katalogu.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
