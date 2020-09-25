---
title: <authentication><clientCertificate>elementu
ms.date: 03/30/2017
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
ms.openlocfilehash: 13296dbc2b3bc8836770197a1549586c841b4635
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201606"
---
# <a name="authentication-of-clientcertificate-element"></a>\<authentication>\<clientCertificate>elementu

Określa zachowania uwierzytelniania dla certyfikatów klienta używanych przez usługę.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<authentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                includeWindowsGroups="Boolean"
                mapClientCertificateToWindowsAccount="Boolean"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|customCertificateValidatorType|Opcjonalny ciąg. Typ i zestaw używany do walidacji typu niestandardowego. Ten atrybut musi być ustawiony `certificateValidationMode` , gdy jest ustawiony na `Custom` .|  
|certificateValidationMode|Opcjonalne Wyliczenie. Określa jeden z trybów używanych do walidacji poświadczeń. Ten atrybut jest <xref:System.ServiceModel.Security.X509CertificateValidationMode> typu. Jeśli jest ustawiona na <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType> , `customCertificateValidator` należy również podać wartość. Wartość domyślna to <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.|  
|includeWindowsGroups|Opcjonalna wartość logiczna. Określa, czy grupy systemu Windows znajdują się w kontekście zabezpieczeń. Ustawienie tego atrybutu na `true` ma wpływ na wydajność, ponieważ powoduje pełne rozszerzanie grupy. Ustaw ten atrybut na `false` , jeśli nie ma potrzeby ustanawiania listy grup, do których należy użytkownik.|  
|mapClientCertificateToWindowsAccount|Typu. Określa, czy klient może być zamapowany na tożsamość systemu Windows przy użyciu certyfikatu. Aby to zrobić, należy włączyć Active Directory.|  
|odwołaniemode|Opcjonalne Wyliczenie. Jeden z trybów użytych do sprawdzenia odwołanych list certyfikatów (RCL). Wartość domyślna to `Online`. Ta wartość jest ignorowana w przypadku korzystania z zabezpieczeń transportu HTTP.|  
|trustedStoreLocation|Opcjonalne Wyliczenie. Jedna z dwóch lokalizacji magazynu systemowego: `LocalMachine` lub `CurrentUser` . Ta wartość jest używana podczas negocjowania certyfikatu usługi z klientem. Sprawdzanie poprawności jest wykonywane względem magazynu **osób zaufanych** w określonej lokalizacji magazynu. Wartość domyślna to `CurrentUser`.|  
  
## <a name="customcertificatevalidatortype-attribute"></a>customCertificateValidatorType — atrybut  
  
|Wartość|Opis|  
|-----------|-----------------|  
|String|Określa nazwę typu i zestaw oraz inne dane używane do znajdowania typu.|  
  
## <a name="certificatevalidationmode-attribute"></a>certificateValidationMode — atrybut  
  
|Wartość|Opis|  
|-----------|-----------------|  
|Wyliczenie|Jedna z następujących wartości: None, zaufania elementów równorzędnych, ChainTrust, PeerOrChainTrust, Custom.<br /><br /> Aby uzyskać więcej informacji, zobacz [Praca z certyfikatami](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="revocationmode-attribute"></a>Atrybut odwołania  
  
|Wartość|Opis|  
|-----------|-----------------|  
|Wyliczenie|Jedna z następujących wartości: NOCHECK, online i offline. Aby uzyskać więcej informacji, zobacz [Praca z certyfikatami](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="trustedstorelocation-attribute"></a>trustedStoreLocation — atrybut  
  
|Wartość|Opis|  
|-----------|-----------------|  
|Wyliczenie|Jedna z następujących wartości: `LocalMachine` lub `CurrentUser` . Wartość domyślna to `CurrentUser`. Jeśli aplikacja kliencka jest uruchomiona na koncie systemowym, zwykle jest to certyfikat `LocalMachine` . Jeśli aplikacja kliencka jest uruchomiona w ramach konta użytkownika, certyfikat zazwyczaj znajduje się w temacie `CurrentUser` .|  
  
### <a name="child-elements"></a>Elementy podrzędne  

 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|Definiuje certyfikat X. 509 używany do uwierzytelniania klienta w usłudze.|  
  
## <a name="remarks"></a>Uwagi  

 `<authentication>`Element odnosi się do <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> klasy. Umożliwia dostosowanie sposobu uwierzytelniania klientów. Można ustawić `certificateValidationMode` atrybut na `None` , `ChainTrust` ,,, `PeerOrChainTrust` `PeerTrust` lub `Custom` . Domyślnie poziom jest ustawiony na `ChainTrust` , który określa, że każdy certyfikat musi znajdować się w hierarchii certyfikatów kończących się w *urzędzie głównym* w górnej części łańcucha. Jest to najbardziej bezpieczny tryb. Można również ustawić wartość na `PeerOrChainTrust` , która określa, że certyfikaty samodzielne (relacja równorzędna) są akceptowane, a także certyfikaty, które znajdują się w zaufanym łańcuchu. Ta wartość jest używana podczas tworzenia i debugowania klientów i usług, ponieważ certyfikaty wystawione przez siebie nie muszą zostać zakupione z zaufanego urzędu. Podczas wdrażania klienta należy `ChainTrust` zamiast tego użyć wartości.  
  
 Możesz również ustawić wartość na `Custom` . W przypadku ustawienia `Custom` wartości należy również ustawić `customCertificateValidatorType` atrybut na zestaw i typ używany do weryfikacji certyfikatu. Aby utworzyć własny niestandardowy moduł sprawdzania poprawności, należy dziedziczyć z klasy abstrakcyjnej <xref:System.IdentityModel.Selectors.X509CertificateValidator> . Aby uzyskać więcej informacji, zobacz [How to: Create a Service, która korzysta z niestandardowego modułu weryfikacji certyfikatu](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
## <a name="example"></a>Przykład  

 Poniższy kod określa certyfikat X. 509 i niestandardowy typ walidacji w `<authentication>` elemencie.  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>
- <xref:System.ServiceModel.Security.X509CertificateValidationMode>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>
- [Zachowania zabezpieczeń](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Instrukcje: tworzenie usługi korzystającej z niestandardowego modułu weryfikacji certyfikatów](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [Praca z certyfikatami](../../../wcf/feature-details/working-with-certificates.md)
