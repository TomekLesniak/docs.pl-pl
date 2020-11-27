---
title: Lokalny kanał
ms.date: 03/30/2017
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
ms.openlocfilehash: 4c1fcdb3e7a4100677882e64f89776fc6eda23e9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264892"
---
# <a name="local-channel"></a>Lokalny kanał

Local Channel to kanał transportu usługi Windows Communication Foundation (WCF) używany do komunikacji w ramach tej samej domeny aplikacji. Jest to przydatne w scenariuszach, w których klient i usługa działają w tej samej domenie aplikacji, a obciążenie typowym stosem kanału WCF (serializacji i deserializacji komunikatów) musi być nieuniknione.  
  
## <a name="demonstrates"></a>Demonstracje  

 Lokalny kanał  
  
## <a name="discussion"></a>Dyskusja  

 Przykład składa się z dwóch plików projektu:  
  
- **LocalChannel**: programowa reprezentacja kanału lokalnego w bieżącej domenie aplikacji. W tym projekcie składnika wysyłającego umieszcza komunikat w kolejce w pamięci, a składnik odbierający anuluje Kolejkowanie wiadomości do wysłania.  
  
- **ClientAndService**: ten projekt hostuje usługę w aplikacji konsolowej, a następnie uruchamia klienta w celu wywołania usługi z poziomu tej samej domeny aplikacji.  
  
 Projekt lokalnego kanału pomija zarówno stos kanału, jak i proces serializacji, aby zwiększyć szybkość. Lokalny kanał transportu jest implementowany przy użyciu kolejki do transportu wywołań usługi z klienta do usługi i zwracania wartości do klienta. Zamiast serializacji parametrów i zwracanych wartości, przykład kopiuje obiekty.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Aby skonfigurować, skompilować i uruchomić przykład  
  
1. Kompiluj i uruchamiaj rozwiązanie LocalChannel.  
  
2. Host usługi jest uruchomiony, a klient wywołuje usługę przy użyciu kanału lokalnego. Zostanie wyświetlone okno konsoli umożliwiające wyświetlenie wyników wywołania usługi.  
  
> [!IMPORTANT]
> Przykłady mogą być już zainstalowane na komputerze. Przed kontynuowaniem Wyszukaj następujący katalog (domyślny).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Jeśli ten katalog nie istnieje, przejdź do [przykładów Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) dla .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , aby pobrać wszystkie Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykłady. Ten przykład znajduje się w następującym katalogu.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`
