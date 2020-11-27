---
title: Zmienianie nazwy usługi WCF
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 25f9201253f02f368ccf95ddf1f7a7d78d2e1b2f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249725"
---
# <a name="renaming-a-wcf-service"></a>Zmienianie nazwy usługi WCF

W tym temacie opisano, jak można zmienić nazwę usługi Windows Communication Foundation (WCF).  
  
## <a name="renaming-a-wcf-service"></a>Zmienianie nazwy usługi WCF  

 Aby zmienić nazwę usługi w szablonie Windows Communication Foundation (WCF), wykonaj następujące czynności:  
  
- Zmień nazwę klasy implementującej usługę.  
  
- W pliku konfiguracji usługi Zmień nazwę usługi na nową wybraną nazwę, jak pokazano w poniższym przykładzie. Plik konfiguracji może być app.config lub web.config pliku w zależności od modelu hostingu.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- Jeśli usługa jest hostowana w sieci, używa pliku *\* SVC* . Otwórz plik SVC i zmodyfikuj nazwę usługi, jak pokazano w poniższym przykładzie. Ten krok nie jest konieczny w przypadku aplikacji samodzielnych, ponieważ nie ma pliku SVC.  
  
```aspx-csharp
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a>Zmiana nazwy kontraktu usługi WCF  
  
- Aby zmienić nazwę kontraktu usługi, wykonaj następujące kroki:  
  
- Zmień nazwę kontraktu usługi.  
  
- W pliku konfiguracji usługi Zmień nazwę kontraktu usługi na nową wybraną nazwę, jak pokazano w poniższym przykładzie. Plik konfiguracji może być app.config lub web.config pliku w zależności od modelu hostingu.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
