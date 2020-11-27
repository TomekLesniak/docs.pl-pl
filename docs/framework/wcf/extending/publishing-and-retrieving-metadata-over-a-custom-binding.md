---
title: Publikowanie i pobieranie metadanych za pośrednictwem powiązania niestandardowego
ms.date: 03/30/2017
ms.assetid: 904e11b4-d90e-45c6-9ee5-c3472c90008c
ms.openlocfilehash: 2c88ab92bb9cbe2fc07240d0934d246fa4de5cc0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262765"
---
# <a name="publishing-and-retrieving-metadata-over-a-custom-binding"></a>Publikowanie i pobieranie metadanych za pośrednictwem powiązania niestandardowego

<xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>Zapewnia obsługę dodawania punktu końcowego metadanych do usługi. Te punkty końcowe metadanych mogą odpowiadać na żądania HTTP GET pod adresem URL, który ma ciąg `?wsdl` QueryString i aby WS-Transfer żądania GET zgodnie ze specyfikacją WS-MetadataExchange (Mex). Punkty końcowe MEX implementują <xref:System.ServiceModel.Description.IMetadataExchange?displayProperty=nameWithType> kontrakt.  
  
## <a name="publishing-metadata-over-a-custom-binding"></a>Publikowanie metadanych za pośrednictwem niestandardowego powiązania  

 Punkty końcowe metadanych GET HTTP i HTTPS GET metadanych są włączane przez ustawienie <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A?displayProperty=nameWithType> właściwości lub <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A?displayProperty=nameWithType> `true` . Nie można skonfigurować powiązań dla tych punktów końcowych.  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>Umowy, ale mogą być używane z dowolnym punktem końcowym, łącznie z tymi, które używają niestandardowych powiązań, ponieważ <xref:System.ServiceModel.Description.IMetadataExchange> punkty końcowe są identyczne z jakimkolwiek innym punktem końcowym usługi Windows Communication Foundation (WCF). Jeśli wiesz, jak zmodyfikować konfigurację powiązania dostarczonego przez system lub wiesz, jak skonfigurować <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> program, możesz skonfigurować powiązanie do użycia z <xref:System.ServiceModel.Description.IMetadataExchange> punktem końcowym.  
  
## <a name="retrieving-metadata-over-a-custom-binding"></a>Pobieranie metadanych za pośrednictwem niestandardowego powiązania  

 Metadane można pobrać z punktów końcowych HTTP GET i HTTPS GET metadanych przy użyciu standardowych żądań HTTP lub HTTPS GET.  
  
 Aby pobrać metadane z punktu końcowego metadanych MEX, można na ogół użyć jednej ze standardowych powiązań MEX obsługiwanych przez program WCF. Aby uzyskać więcej informacji, zobacz <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>. <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>Typ i narzędzie Svcutil.exe automatycznie wybierają jedno z tych standardowych powiązań MEX na podstawie adresu określonego punktu końcowego metadanych.  
  
 Jeśli punkt końcowy metadanych MEX używa innego powiązania niż jedno ze standardowych powiązań MEX, można skonfigurować powiązanie używane przez <xref:System.ServiceModel.Description.MetadataExchangeClient> kod przy użyciu lub podając <xref:System.ServiceModel.Description.IMetadataExchange> konfigurację punktu końcowego klienta. Narzędzie Svcutil.exe automatycznie ładuje się z pliku konfiguracji, a <xref:System.ServiceModel.Description.IMetadataExchange> Konfiguracja punktu końcowego klienta ma taką samą nazwę jak schemat identyfikatora URI dla adresu punktu końcowego metadanych.  
  
## <a name="security"></a>Zabezpieczenia  

 Podczas publikowania metadanych za pośrednictwem niestandardowego powiązania upewnij się, że powiązanie zapewnia obsługę zabezpieczeń wymaganą przez Twoje metadane. Na przykład aby zapobiec ujawnieniu informacji i upewnić się, że klient ma uprawnienia do uzyskiwania metadanych, można zwiększyć bezpieczeństwo metadanych i aplikacji przez skonfigurowanie <xref:System.ServiceModel.Description.IMetadataExchange> punktu końcowego, aby wymagał uwierzytelniania i szyfrowania. Przykładowy [punkt końcowy niestandardowej bezpiecznej metadanych](../samples/custom-secure-metadata-endpoint.md) demonstruje ten scenariusz.  
  
## <a name="see-also"></a>Zobacz też

- [Zabezpieczanie usług](../securing-services.md)
- [Powiązania elementu WS-MetadataExchange](ws-metadataexchange-bindings.md)
- [Instrukcje: konfigurowanie niestandardowego wiązania WS-Metadata Exchange](how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [Instrukcje: pobieranie metadanych przez wiązanie inne niż wymiany metadanych](how-to-retrieve-metadata-over-a-non-mex-binding.md)
