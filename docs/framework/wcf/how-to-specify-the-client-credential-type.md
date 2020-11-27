---
title: 'Instrukcje: Określanie typu poświadczeń klienta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: b45d7b58d8a1fe79f9d7a8cff6e328b46633985c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293679"
---
# <a name="how-to-specify-the-client-credential-type"></a>Instrukcje: Określanie typu poświadczeń klienta

Po ustawieniu trybu zabezpieczeń (transport lub wiadomość) można ustawić typ poświadczeń klienta. Ta właściwość określa typ poświadczeń, które klient musi przekazać do usługi w celu uwierzytelnienia. Aby uzyskać więcej informacji na temat ustawiania trybu zabezpieczeń (wymaganego kroku przed ustawieniem typu poświadczeń klienta), zobacz [How to: Set a Security Mode](how-to-set-the-security-mode.md).  
  
### <a name="to-set-the-client-credential-type-in-code"></a>Aby ustawić typ poświadczeń klienta w kodzie  
  
1. Utwórz wystąpienie powiązania, które będzie używane przez usługę. Ten przykład używa <xref:System.ServiceModel.WSHttpBinding> powiązania.  
  
2. Ustaw <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> Właściwość na odpowiednią wartość. W tym przykładzie jest stosowany tryb wiadomości.  
  
3. Ustaw <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> Właściwość na odpowiednią wartość. Ten przykład służy do ustawiania uwierzytelniania systemu Windows ( <xref:System.ServiceModel.MessageCredentialType.Windows> ).  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a>Aby ustawić typ poświadczeń klienta w konfiguracji  
  
1. Dodaj [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) element do pliku konfiguracji.  
  
2. Jako element podrzędny Dodaj [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element.  
  
3. Dodaj odpowiednie powiązanie. W tym przykładzie używa [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) elementu.  
  
4. Dodaj [\<binding>](../configure-apps/file-schema/wcf/bindings.md) element i ustaw `name` odpowiednią wartość atrybutu. Ten przykład używa nazwy "SecureBinding".  
  
5. Dodaj `<security>` powiązanie. Ustaw `mode` odpowiednią wartość atrybutu. Ten przykład ustawia go na `"Message"` .  
  
6. Dodaj `<message>` `<transport>` element lub, zgodnie z trybem zabezpieczeń. Ustaw `clientCredentialType` odpowiednią wartość atrybutu. Ten przykład używa `"Windows"` .  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a>Zobacz też

- [Zabezpieczanie usług](securing-services.md)
- [Instrukcje: Ustawianie trybu zabezpieczeń](how-to-set-the-security-mode.md)
