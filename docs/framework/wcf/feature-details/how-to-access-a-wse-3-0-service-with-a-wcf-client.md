---
title: 'Instrukcje: Dostęp do usługi WSE 3.0 za pomocą klienta programu WCF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
ms.openlocfilehash: 847146c2025612689f0d69cc0c23d2be14018c0f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556840"
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a>Instrukcje: Dostęp do usługi WSE 3.0 za pomocą klienta programu WCF
Klienci korzystający z programu Windows Communication Foundation (WCF) są zgodną z rozszerzeniami usług sieci Web (WSE) 3,0 dla usług Microsoft .NET, gdy klienci WCF są skonfigurowani do korzystania z wersji z sierpnia 2004 specyfikacji WS-Addressing. Jednak usługi WSE 3,0 nie obsługują protokołu wymiany metadanych (MEX), dlatego w przypadku tworzenia klasy klienta programu WCF za pomocą narzędzia do obsługi [metadanych ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) nie są stosowane ustawienia zabezpieczeń dla wygenerowanego klienta WCF. W związku z tym należy określić ustawienia zabezpieczeń wymagane przez usługę WSE 3,0 po wygenerowaniu klienta WCF.  
  
 Te ustawienia zabezpieczeń można zastosować przy użyciu niestandardowego powiązania, aby wziąć pod uwagę wymagania dotyczące usługi WSE 3,0 i wymagania interoperacyjności między usługą WSE 3,0 a klientem programu WCF. Te wymagania dotyczące współdziałania obejmują wymienione powyżej użycie protokołu WS-Addressing z sierpnia 2004 i domyślną ochronę wiadomości w programie WSE 3.0 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> . Domyślna ochrona komunikatów dla programu WCF to <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature> . W tym temacie opisano sposób tworzenia powiązania WCF, które współdziała z usługą WSE 3,0. Funkcja WCF udostępnia również przykład, który obejmuje to powiązanie. Aby uzyskać więcej informacji na temat tego przykładu, zobacz [współdziałanie z usługami sieci Web ASMX](../samples/interoperating-with-asmx-web-services.md).  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a>Aby uzyskać dostęp do usługi sieci Web WSE 3,0 przy użyciu klienta WCF  
  
1. Uruchom narzędzie do obsługi [metadanych ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , aby utworzyć klienta WCF dla usługi sieci Web WSE 3,0.  
  
     W przypadku usługi sieci Web WSE 3,0 jest tworzony klient WCF. Ponieważ WSE 3,0 nie obsługuje protokołu MEX, nie można użyć narzędzia, aby pobrać wymagania dotyczące zabezpieczeń dla usługi sieci Web. Deweloper aplikacji musi dodać ustawienia zabezpieczeń dla klienta.  
  
     Aby uzyskać więcej informacji na temat tworzenia klienta WCF, zobacz [How to: Create a Client](../how-to-create-a-wcf-client.md).  
  
2. Utwórz klasę, która reprezentuje powiązanie, które może komunikować się z usługami sieci Web WSE 3,0.  
  
     Następująca Klasa jest częścią [współdziałania z](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90)) przykładem WSE:  
  
    1. Utwórz klasę pochodną od klasy <xref:System.ServiceModel.Channels.Binding>.  
  
         Poniższy przykład kodu tworzy klasę o nazwie `WseHttpBinding` , która dziedziczy z <xref:System.ServiceModel.Channels.Binding> klasy.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2. Dodaj właściwości do klasy, która określa potwierdzenie WSE gotowe używane przez usługę WSE, czy klucze pochodne są wymagane, czy są używane bezpieczne sesje, czy potwierdzenia podpisu są wymagane oraz ustawienia ochrony wiadomości. W WSE 3,0, potwierdzenie gotowe określa wymagania dotyczące zabezpieczeń dla klienta lub usługi sieci Web — podobnie jak w przypadku trybu uwierzytelniania powiązania w programie WCF.  
  
         Poniższy przykład kodu definiuje `SecurityAssertion` właściwości,, `RequireDerivedKeys` `EstablishSecurityContext` i, `MessageProtectionOrder` które określają WSE gotowe, niezależnie od tego, czy klucze pochodne są wymagane, czy są używane bezpieczne sesje, czy potwierdzenia podpisu są wymagane oraz odpowiednio ustawienia ochrony wiadomości.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3. Zastąp <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> metodę, aby ustawić właściwości powiązania.  
  
         Poniższy przykład kodu określa ustawienia transportu, kodowania komunikatów i ochrony wiadomości, pobierając wartości `SecurityAssertion` `MessageProtectionOrder` właściwości i.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3. W kodzie aplikacji klienckiej Dodaj kod, aby ustawić właściwości powiązania.  
  
     Poniższy przykład kodu określa, że klient WCF musi używać ochrony komunikatów i uwierzytelniania zgodnie z opisem w `AnonymousForCertificate` potwierdzeniu zabezpieczeń WSE 3,0 gotowe. Dodatkowo wymagane są bezpieczne sesje i klucze pochodne.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu definiuje niestandardowe powiązanie, które uwidacznia właściwości odpowiadające właściwościom WSE 3,0 gotowe Security Assertion. To niestandardowe powiązanie, które nosi nazwę `WseHttpBinding` , służy do określania właściwości powiązań dla klienta WCF, który komunikuje się z przykładem szybkiego startu WSSECURITYANONYMOUS WSE 3,0.  

## <a name="see-also"></a>Zobacz także

- <xref:System.ServiceModel.Channels.Binding>
- [Współdziałanie z WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90))
