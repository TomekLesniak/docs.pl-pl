---
title: Zabezpieczenia komunikatów — Windows
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: d2221d1c-c9cb-48d1-b044-a3b4445c7f05
ms.openlocfilehash: 0c5cbb0962407ea6ee9a32e35f65103d1def880f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294346"
---
# <a name="message-security-windows"></a>Zabezpieczenia komunikatów — Windows

Ten przykład pokazuje, jak skonfigurować <xref:System.ServiceModel.WSHttpBinding> powiązanie do używania zabezpieczeń na poziomie komunikatów z uwierzytelnianiem systemu Windows. Ten przykład jest oparty na [wprowadzenie](getting-started-sample.md). W tym przykładzie usługa jest hostowana w Internet Information Services (IIS), a klient jest aplikacją konsolową (. exe).  
  
> [!NOTE]
> Procedura instalacji i instrukcje dotyczące kompilacji dla tego przykładu znajdują się na końcu tego tematu.  
  
 Domyślne zabezpieczenia [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) wiadomości są zabezpieczane przy użyciu uwierzytelniania systemu Windows. Pliki konfiguracji w tym przykładzie jawnie ustawiają `mode` atrybut [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) do `Message` i `clientCredentialType` atrybut na `Windows` . Te wartości są wartościami domyślnymi tego powiązania, ale zostały one jawnie skonfigurowane, jak pokazano w poniższej konfiguracji przykładowej w celu zademonstrowania ich użycia.  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding>  
            <security mode="Message">  
                <message clientCredentialType="Windows"/>  
            </security>  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 Konfiguracja punktu końcowego klienta składa się z adresu bezwzględnego dla punktu końcowego usługi, powiązania i kontraktu. Powiązanie klienta jest skonfigurowane z odpowiednimi `securityMode` i `authenticationMode` .  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address=  
            "http://localhost/servicemodelsamples/service.svc"
            binding="wsHttpBinding"
            bindingConfiguration="Binding1"
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- The default security for the WSHttpBinding is -->  
      <!-- Message security using Windows authentication. -->  
      <!-- This configuration explicitly defines the security mode -->  
      <!-- as Message and the clientCredentialType as Windows -->  
      <!-- for demonstration purposes. -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="Windows"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 Kod źródłowy usługi został zmodyfikowany, aby zademonstrować, jak <xref:System.ServiceModel.OperationContext.ServiceSecurityContext%2A> można go użyć w celu uzyskania dostępu do tożsamości obiektu wywołującego.  

```csharp
public string GetCallerIdentity()  
{  
    // The Windows identity of the caller can be accessed on the ServiceSecurityContext.WindowsIdentity.  
    return OperationContext.Current.ServiceSecurityContext.WindowsIdentity.Name;  
}  
```

 Po uruchomieniu przykładu żądania operacji i odpowiedzi są wyświetlane w oknie konsoli klienta. Pierwsza wywoływana metoda- `GetCallerIdentity` -zwraca nazwę tożsamości obiektu wywołującego z powrotem do klienta. Naciśnij klawisz ENTER w oknie konsoli, aby zamknąć klienta programu.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Aby skonfigurować, skompilować i uruchomić przykład  
  
1. Upewnij się, że została wykonana [Procedura konfiguracji jednorazowej dla przykładów Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Aby skompilować wersję rozwiązania w języku C# lub Visual Basic .NET, postępuj zgodnie z instrukcjami w temacie [Tworzenie przykładów Windows Communication Foundation](building-the-samples.md).  
  
3. Aby uruchomić przykład w konfiguracji na jednym lub wielu komputerach, postępuj zgodnie z instrukcjami w temacie [Uruchamianie przykładów Windows Communication Foundation](running-the-samples.md).  
