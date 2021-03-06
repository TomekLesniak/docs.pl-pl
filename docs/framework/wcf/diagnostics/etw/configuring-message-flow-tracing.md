---
title: Konfigurowanie śledzenia przepływu komunikatów
ms.date: 03/30/2017
ms.assetid: 15571ca2-bee2-47fb-ba10-fcbc09152ad0
ms.openlocfilehash: 6c271c26eb4e57014b3aaebf306b283bd06c7119
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254886"
---
# <a name="configuring-message-flow-tracing"></a>Konfigurowanie śledzenia przepływu komunikatów

Po włączeniu śledzenia działań Windows Communication Foundation (WCF) identyfikatory działań end-to-end są przypisywane do działań logicznych w ramach stosu WCF. W systemie [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] jest teraz dostępna wyższa wersja wydajności tej funkcji, która działa ze śledzeniem zdarzeń systemu Windows (ETW) o nazwie śledzenie przepływu wiadomości. Gdy ta wartość jest włączona, identyfikatory działań end-to-end są pobierane z (lub przypisane do, jeśli są puste) komunikaty przychodzące i są propagowane do wszystkich zdarzeń śledzenia, które są emitowane po zdekodowaniu komunikatu przez kanał. Klienci mogą używać tej funkcji do odbudowy przepływów komunikatów przy użyciu dzienników śledzenia z różnych usług po dekodowania.  
  
 Śledzenie można włączyć po wykryciu problemu w aplikacji, a następnie wyłączeniu po rozwiązaniu problemu.  
  
## <a name="enabling-tracing"></a>Włączenie debugowania  

 Możesz włączyć śledzenie przepływu komunikatów, ustawiając element konfiguracji .NET Framework 4 `messageFlowTracing` na `true` , jak pokazano w poniższym przykładzie.  
  
```xml  
<system.servicemodel>  
  <diagnostics>  
    <endToEndTracing propagateActivity="true" messageFlowTracing="true" />  
  </diagnostics>  
</system.servicemodel>  
```  
  
> [!NOTE]
> Ponieważ `endToEndTracing` element konfiguracji znajduje się w pliku Web.config, nie można go skonfigurować dynamicznie w taki sam sposób jak ETW. Aby `endToEndTracing` element konfiguracji został uwzględniony, należy ponownie przetworzyć aplikację.  
  
 Działania są skorelowane przez wymianę identyfikatora zwanego IDENTYFIKATORem działania. Ten identyfikator jest identyfikatorem GUID i jest generowany przez klasę System. Diagnostics. korelacji. Jeśli manipulujesz system. Diagnostics. Trace. korelacji. ActivityID, upewnij się, że wartość jest ustawiona na oryginalna, gdy kontrola wykonywania przeniesie z powrotem do kodu WCF.  Ponadto, jeśli używasz asynchronicznego modelu programowania WCF, upewnij się, że element System. Diagnostics. Trace. korelacji. ActivityID jest przekazywany między wątkami.  
  
## <a name="message-flow-tracing-and-rest-services"></a>Śledzenie przepływu komunikatów i usługi REST  

 Funkcja śledzenia przepływu komunikatów umożliwia śledzenie końca żądania.  W przypadku usług opartych na protokole SOAP identyfikator działania jest wysyłany w nagłówku komunikatu protokołu SOAP. Żądania REST nie zawierają tego nagłówka, więc zamiast niego zostanie użyty specjalny nagłówek zdarzenia HTTP. Poniższy fragment kodu pokazuje, jak można programowo pobrać wartość identyfikatora działania:  
  
```csharp
Object output = null;
if (OperationContext.Current.IncomingMessageProperties.TryGetValue(HttpRequestMessageProperty.Name, out output))
{
   HttpRequestMessageProperty httpHeaders = output as HttpRequestMessageProperty;
   // Retrieve the Activity Id from the HTTP header    string e2eId = httpHeaders.Headers["E2EActivity"];
   // ...
}
```

 Można programowo dodać nagłówek przy użyciu następującego kodu:  
  
```csharp  
HttpContent content = new StreamContent(contentStream);  
Guid correlation = Guid.NewGuid();  
content.Headers.Add("E2EActivity", Convert.ToBase64String(correlation.ToByteArray()));  
```
