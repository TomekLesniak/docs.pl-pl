---
title: Niestandardowy dyspozytor kanału
ms.date: 03/30/2017
ms.assetid: 813acf03-9661-4d57-a3c7-eeab497321c6
ms.openlocfilehash: 38d39cbba15c95a43444108d634d3c30524c70f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241775"
---
# <a name="custom-channel-dispatcher"></a>Niestandardowy dyspozytor kanału

Ten przykład pokazuje, jak zbudować stos kanałów w niestandardowy sposób, wdrażając <xref:System.ServiceModel.ServiceHostBase> bezpośrednio i jak utworzyć niestandardowy Dyspozytor kanału w środowisku hosta sieci Web. Dyspozytor kanału współdziała z <xref:System.ServiceModel.Channels.IChannelListener> programem w celu akceptowania kanałów i pobierania komunikatów ze stosu kanału. Ten przykład zawiera również podstawowy przykład pokazujący sposób tworzenia stosu kanału w środowisku hosta sieci Web za pomocą programu <xref:System.ServiceModel.Activation.VirtualPathExtension> .  
  
## <a name="custom-servicehostbase"></a>Niestandardowy obiektu ServiceHostBase  

 Ten przykład implementuje typ podstawowy <xref:System.ServiceModel.ServiceHostBase> zamiast nie <xref:System.ServiceModel.ServiceHost> pokazuje, jak zastąpić implementację stosu Windows Communication Foundation (WCF) za pomocą niestandardowej warstwy obsługi komunikatów na stosie kanału. Można zastąpić metodę wirtualną, <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A> Aby kompilować odbiorniki kanału i Dyspozytor kanału.  
  
 Aby zaimplementować usługę hostowaną w sieci Web, Pobierz rozszerzenie usługi <xref:System.ServiceModel.Activation.VirtualPathExtension> z <xref:System.ServiceModel.ServiceHostBase.Extensions%2A> kolekcji i Dodaj je do <xref:System.ServiceModel.Channels.BindingParameterCollection> tak, aby warstwa transportu wie, jak skonfigurować odbiornik kanału w oparciu o ustawienia środowiska macierzystego, czyli Internet Information Services (IIS) ustawienia usługi aktywacji procesów/Windows (was).  
  
## <a name="custom-channel-dispatcher"></a>Niestandardowy dyspozytor kanału  

 Niestandardowy Dyspozytor kanału rozszerza typ <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase> . Ten typ implementuje logikę programowania warstwy kanału. W tym przykładzie <xref:System.ServiceModel.Channels.IReplyChannel> obsługiwane są tylko dla wzorca wymiany komunikatów żądanie-odpowiedź, ale niestandardowy Dyspozytor kanału można łatwo rozszerzyć na inne typy kanałów.  
  
 Dyspozytor najpierw otwiera odbiornik kanału, a następnie akceptuje kanał pojedynczej odpowiedzi. Kanał zaczyna wysyłać komunikaty (żądania) w pętli nieskończonej. Dla każdego żądania tworzy komunikat odpowiedzi i wysyła go z powrotem do klienta.  
  
## <a name="creating-a-response-message"></a>Tworzenie komunikatu odpowiedzi  

 Przetwarzanie wiadomości jest zaimplementowane w typie `MyServiceManager` . W `HandleRequest` metodzie `Action` Nagłówek wiadomości jest najpierw sprawdzany w celu sprawdzenia, czy żądanie jest obsługiwane. Zdefiniowano wstępnie zdefiniowaną akcję SOAP " http://tempuri.org/HelloWorld/Hello " w celu zapewnienia filtrowania komunikatów. Jest to podobne do koncepcji kontraktu usług w implementacji programu WCF <xref:System.ServiceModel.ServiceHost> .  
  
 W przypadku poprawnego przypadku działania protokołu SOAP przykład pobiera żądane dane komunikatów i generuje odpowiadające mu odpowiedzi na żądanie podobne do tego, co jest widoczne w <xref:System.ServiceModel.ServiceHost> przypadku.  
  
 Zlecenie HTTP-GET zostało specjalnie obsłużone przez zwrócenie niestandardowego komunikatu HTML, w tym przypadku, aby można było przeglądać usługę z przeglądarki, aby zobaczyć, że została poprawnie skompilowana. Jeśli akcja SOAP nie jest zgodna, Wyślij komunikat o błędzie z powrotem, aby wskazać, że żądanie nie jest obsługiwane.  
  
 Klient tego przykładu jest normalnym klientem WCF, który nie przyjmuje niczego z usługi. W związku z tym usługa jest specjalnie zaprojektowana tak, aby odpowiadała tym, co otrzymujesz z normalnej <xref:System.ServiceModel.ServiceHost> implementacji WCF. W związku z tym tylko kontrakt usługi jest wymagany na kliencie.  
  
## <a name="using-the-sample"></a>Korzystanie z przykładu  

 Uruchomienie aplikacji klienckiej bezpośrednio tworzy następujące dane wyjściowe.  
  
```output  
Client is talking to a request/reply WCF service.
Type what you want to say to the server: Howdy  
Server replied: You said: Howdy. Message id: 1  
Server replied: You said: Howdy. Message id: 2  
Server replied: You said: Howdy. Message id: 3  
Server replied: You said: Howdy. Message id: 4  
Server replied: You said: Howdy. Message id: 5  
```  
  
 Możesz również przeglądać usługę z przeglądarki, aby komunikat HTTP-GET został przetworzony na serwerze. Spowoduje to pobranie dobrze sformatowanego tekstu HTML.  
  
> [!IMPORTANT]
> Przykłady mogą być już zainstalowane na komputerze. Przed kontynuowaniem Wyszukaj następujący katalog (domyślny).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Jeśli ten katalog nie istnieje, przejdź do [przykładów Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) dla .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , aby pobrać wszystkie Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykłady. Ten przykład znajduje się w następującym katalogu.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\CustomChannelDispatcher`
