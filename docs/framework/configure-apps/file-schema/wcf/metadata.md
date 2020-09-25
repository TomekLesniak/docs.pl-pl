---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: aad0bbde964644448fbafc6c628c00c9faaad497
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204765"
---
# \<metadata>

Określa sposób przetwarzania metadanych usługi.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<metadata>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<system.serviceModel>
  <client>
    <metadata>
      <policyImporters>
        <policyImporter type="string" />
      </policyImporters>
      <wsdlImporters>
        <wsdlImporter type="string" />
      </wsdlImporters>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  

 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|Określa wszystkich importerów zasad kontrolujących Importowanie potwierdzeń niestandardowych zasad dotyczących powiązań. Importer zasad jest używany do wyszukiwania potwierdzeń niestandardowych zasad dotyczących funkcji powiązania, a także do dołączania niestandardowego elementu powiązania, który implementuje funkcje wymagane przez potwierdzenie.|  
|[\<wsdlImporters>](wsdlimporters.md)|Określa wszystkich importerów WSDL, którzy importują metadane Web Services Description Language (WSDL) 1,1 z załącznikami WS-Policy. Importer WSDL jest używany do importowania metadanych, a także konwertowania tych informacji na różne klasy, które reprezentują informacje o kontrakcie i punkcie końcowym. Umożliwia selektywne importowanie informacji o kontraktach i punktach końcowych oraz właściwości, które uwidaczniają błędy importu i akceptują informacje o typie odpowiednie dla procesu importu i konwersji. Obsługuje ona również importowanie informacji o powiązaniach i właściwości, które zapewniają dostęp do dowolnych dokumentów zasad, dokumentów WSDL, rozszerzeń WSDL i dokumentów schematu XML.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<client>](client.md)|Sekcja klienta definiuje listę punktów końcowych, z którymi klient może się połączyć.|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [Konfiguracja klienta programu WCF](../../../wcf/feature-details/client-configuration.md)
- [Klienci](../../../wcf/feature-details/clients.md)
