---
title: Obsługa błędów programu WCF
ms.date: 03/30/2017
ms.assetid: 1e4b1e0f-9598-449d-9d73-90bda62305b8
ms.openlocfilehash: 72db5db9f6b4a3cd2ba62fe938fcfeed2dfda1e5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240943"
---
# <a name="wcf-error-handling"></a>Obsługa błędów programu WCF

Błędy napotykane przez aplikację WCF należą do jednej z trzech grup:  
  
1. Błędy komunikacji  
  
2. Błędy serwera proxy/kanału  
  
3. Błędy aplikacji  
  
 Błędy komunikacji występują, gdy sieć jest niedostępna, klient używa nieprawidłowego adresu lub host usługi nie nasłuchuje komunikatów przychodzących. Błędy tego typu są zwracane do klienta jako <xref:System.ServiceModel.CommunicationException> lub <xref:System.ServiceModel.CommunicationException> klasy pochodne.  
  
 Błędy serwera proxy/kanału to błędy występujące w kanale lub serwerze proxy. Błędy tego typu obejmują: próba użycia serwera proxy lub kanału, który został zamknięty, występuje niezgodność kontraktu między klientem a usługą lub poświadczenia klienta są odrzucane przez usługę. W tej kategorii istnieje wiele typów błędów, które są zbyt duże, aby można je było wyświetlić w tym miejscu. Błędy tego typu są zwracane do klienta w taki sam sposób, w jaki jest (nie są wykonywane żadne przekształcenia w obiektach wyjątków).  
  
 Błędy aplikacji występują podczas wykonywania operacji usługi. Błędy tego rodzaju są wysyłane do klienta jako <xref:System.ServiceModel.FaultException> lub <xref:System.ServiceModel.FaultException%601> .  
  
 Obsługa błędów w programie WCF jest wykonywana przez co najmniej jedną z następujących czynności:  
  
- Bezpośrednie obsługiwanie zgłoszonego wyjątku. Jest to wykonywane tylko w przypadku błędów komunikacji i serwera proxy/kanału.  
  
- Korzystanie z umów dotyczących błędów  
  
- Implementowanie <xref:System.ServiceModel.Dispatcher.IErrorHandler> interfejsu  
  
- Obsługa <xref:System.ServiceModel.ServiceHost> zdarzeń  
  
## <a name="fault-contracts"></a>Kontrakty błędów  

 Umowy dotyczące usterek umożliwiają definiowanie błędów, które mogą wystąpić podczas operacji na platformie w niezależny sposób. Domyślnie wszystkie wyjątki zgłoszone w ramach operacji usługi zostaną zwrócone do klienta jako <xref:System.ServiceModel.FaultException> obiekt. <xref:System.ServiceModel.FaultException>Obiekt będzie zawierać bardzo mało informacji. Informacje wysyłane do klienta można kontrolować przez zdefiniowanie kontraktu błędu i zwrócenie błędu jako <xref:System.ServiceModel.FaultException%601> . Aby uzyskać więcej informacji, zobacz [określanie i obsługa błędów w kontraktach i usługach](specifying-and-handling-faults-in-contracts-and-services.md).  
  
## <a name="ierrorhandler"></a>IErrorHandler  

 <xref:System.ServiceModel.Dispatcher.IErrorHandler>Interfejs umożliwia większą kontrolę nad sposobem, w jaki aplikacja WCF reaguje na błędy.  Zapewnia pełną kontrolę nad komunikatem o błędzie, który jest zwracany do klienta i umożliwia wykonywanie niestandardowych operacji przetwarzania, takich jak rejestrowanie.  Aby uzyskać więcej informacji na temat <xref:System.ServiceModel.Dispatcher.IErrorHandler> i [Rozszerzanie kontroli nad obsługą błędów i raportowaniem](./samples/extending-control-over-error-handling-and-reporting.md)  
  
## <a name="servicehost-events"></a>Zdarzenia ServiceHost  

 <xref:System.ServiceModel.ServiceHost>Klasa obsługuje usługi i definiuje kilka zdarzeń, które mogą być odpowiednie do obsługi błędów. Przykład:  
  
1. <xref:System.ServiceModel.Channels.CommunicationObject.Faulted>
  
2. <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived>
  
 Aby uzyskać więcej informacji, zobacz <xref:System.ServiceModel.ServiceHost>.
