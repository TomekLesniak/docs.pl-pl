---
title: 'Instrukcje: tworzenie usługi korzystającej z niestandardowego modułu weryfikacji certyfikatów'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
ms.openlocfilehash: 31918ca2d96b63911130d22476a6e5a6d48999ee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249244"
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a>Instrukcje: tworzenie usługi korzystającej z niestandardowego modułu weryfikacji certyfikatów

W tym temacie pokazano, jak zaimplementować niestandardowy moduł sprawdzania poprawności certyfikatu oraz jak skonfigurować poświadczenia klienta lub usługi w celu zastąpienia domyślnej logiki walidacji certyfikatu za pomocą niestandardowego modułu sprawdzania certyfikatu.  
  
 Jeśli certyfikat X. 509 jest używany do uwierzytelniania klienta lub usługi, Windows Communication Foundation (WCF) domyślnie używa magazynu certyfikatów systemu Windows i interfejsu API kryptografii do weryfikacji certyfikatu i upewnienia się, że jest zaufany. Czasami Wbudowana funkcja weryfikacji certyfikatu jest za mała i należy ją zmienić. Funkcja WCF zapewnia łatwy sposób zmiany logiki walidacji przez umożliwienie użytkownikom dodawania niestandardowego modułu weryfikacji certyfikatu. Jeśli jest określony niestandardowy moduł sprawdzania poprawności certyfikatu, funkcja WCF nie korzysta z wbudowanej logiki walidacji certyfikatu, ale zamiast tego używa niestandardowego modułu weryfikacji.  
  
## <a name="procedures"></a>Procedury  
  
#### <a name="to-create-a-custom-certificate-validator"></a>Aby utworzyć niestandardowy moduł sprawdzania poprawności certyfikatu  
  
1. Zdefiniuj nową klasę pochodną <xref:System.IdentityModel.Selectors.X509CertificateValidator> .  
  
2. Zaimplementuj metodę abstrakcyjną <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> . Certyfikat, który musi zostać sprawdzony, jest przenoszona jako argument do metody. Jeśli przesłany certyfikat nie jest prawidłowy zgodnie z logiką walidacji, ta metoda zgłasza <xref:System.IdentityModel.Tokens.SecurityTokenValidationException> . Jeśli certyfikat jest prawidłowy, Metoda powraca do obiektu wywołującego.  
  
    > [!NOTE]
    > Aby przywrócić błędy uwierzytelniania z powrotem do klienta, należy zgłosić <xref:System.ServiceModel.FaultException> <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> metodę.  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a>Aby określić niestandardowy moduł sprawdzania poprawności certyfikatu w konfiguracji usługi  
  
1. Dodaj [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element i [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) do [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elementu.  
  
2. Dodaj [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) a i ustaw `name` odpowiednią wartość atrybutu.  
  
3. Dodaj [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) `<behavior>` element do elementu.  
  
4. Dodaj `<clientCertificate>` element do `<serviceCredentials>` elementu.  
  
5. Dodaj [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) `<clientCertificate>` element do elementu.  
  
6. Ustaw `customCertificateValidatorType` atrybut na typ walidacji. Poniższy przykład ustawia atrybut na przestrzeń nazw i nazwę typu.  
  
7. Ustaw `certificateValidationMode` atrybut na `Custom` .  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="ServiceBehavior">  
         <serviceCredentials>  
          <clientCertificate>  
          <authentication certificateValidationMode="Custom" customCertificateValidatorType="Samples.MyValidator, service" />  
          </clientCertificate>  
         </serviceCredentials>  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a>Aby określić niestandardowy moduł sprawdzania poprawności certyfikatu przy użyciu konfiguracji na kliencie  
  
1. Dodaj [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element i [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) do [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elementu.  
  
2. Dodaj [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) element.  
  
3. Dodaj `<behavior>` element i ustaw `name` odpowiednią wartość atrybutu.  
  
4. Dodaj [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) element.  
  
5. Dodaj [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .  
  
6. Dodaj [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) , jak pokazano w poniższym przykładzie.  
  
7. Ustaw `customCertificateValidatorType` atrybut na typ walidacji.  
  
8. Ustaw `certificateValidationMode` atrybut na `Custom` . Poniższy przykład ustawia atrybut na przestrzeń nazw i nazwę typu.  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <endpointBehaviors>  
        <behavior name="clientBehavior">  
         <clientCredentials>  
          <serviceCertificate>  
           <authentication certificateValidationMode="Custom"
                  customCertificateValidatorType=  
             "Samples.CustomX509CertificateValidator, client"/>  
          </serviceCertificate>  
         </clientCredentials>  
        </behavior>  
       </endpointBehaviors>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a>Aby określić niestandardowy moduł sprawdzania poprawności certyfikatu przy użyciu kodu w usłudze  
  
1. Określ niestandardowy moduł sprawdzania poprawności certyfikatu <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> . Możesz uzyskać dostęp do poświadczeń usługi przy użyciu <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> właściwości.  
  
2. Ustaw <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> Właściwość na wartość <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom> .  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a>Aby określić niestandardowy moduł sprawdzania poprawności certyfikatu przy użyciu kodu na kliencie  
  
1. Określ niestandardowy moduł sprawdzania poprawności certyfikatu przy użyciu <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> właściwości. Możesz uzyskać dostęp do poświadczeń klienta przy użyciu <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> właściwości. (Klasa klienta wygenerowana przez [Narzędzie narzędzia metadanych ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) zawsze pochodzi od <xref:System.ServiceModel.ClientBase%601> klasy.)  
  
2. Ustaw <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> Właściwość na wartość <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom> .  
  
## <a name="example"></a>Przykład  
  
### <a name="description"></a>Opis  

 Poniższy przykład pokazuje implementację niestandardowego modułu weryfikacji certyfikatu i jego użycia w usłudze.  
  
### <a name="code"></a>Kod  

 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.IdentityModel.Selectors.X509CertificateValidator>
