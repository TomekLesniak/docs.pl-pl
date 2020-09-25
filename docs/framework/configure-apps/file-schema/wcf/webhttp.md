---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 716d960e2d5f896976c22a60d419d9b165b36178
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202464"
---
# \<webHttp>

Ten element określa <xref:System.ServiceModel.Description.WebHttpBehavior> punkt końcowy za pomocą konfiguracji. Takie zachowanie, które jest używane w połączeniu ze [\<webHttpBinding>](webhttpbinding.md) standardowym powiązaniem, umożliwia model programowania sieci Web dla usługi Windows Communication Foundation (WCF).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttp>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|automaticFormatSelectionEnabled|Jeśli ta właściwość jest ustawiona na `true` , Infrastruktura WCF określa najlepszy format do użycia. Automatyczne wybieranie formatu jest domyślnie wyłączone w celu zapewnienia zgodności z poprzednimi wersjami. Automatyczne wybieranie formatu można włączyć programowo lub za pomocą konfiguracji.|  
|defaultBodyStyle|Określa domyślny styl treści zwróconych komunikatów. Aby uzyskać więcej informacji, zobacz <xref:System.ServiceModel.Web.WebMessageBodyStyle> i [Formatowanie http sieci Web](../../../wcf/feature-details/wcf-web-http-formatting.md)w programie WCF.|  
|defaultOutgoingResponseFormat|Określa domyślny format odpowiedzi wychodzącej dla komunikatów. Aby uzyskać więcej informacji, zobacz temat [Formatowanie http sieci Web](../../../wcf/feature-details/wcf-web-http-formatting.md)w programie WCF.|  
|faultExceptionEnabled|Pobiera lub ustawia flagę określającą, czy wyjątek FaultException występuje w przypadku wewnętrznego błędu serwera (kod stanu HTTP: 500).|  
|helpEnabled|Pobiera lub ustawia wartość określającą, czy strona pomocy jest włączona.|  
  
### <a name="child-elements"></a>Elementy podrzędne  

 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Określa zestaw zachowań punktów końcowych.|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [Obsługa integracji AJAX i notacji JSON](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttpBinding>](webhttpbinding.md)
