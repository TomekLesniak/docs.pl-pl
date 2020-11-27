---
title: Publikowanie punktów końcowych metadanych
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 5be27a72c87d95e36a5b283e7930ba0a5191a5a1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249764"
---
# <a name="publishing-metadata-endpoints"></a>Publikowanie punktów końcowych metadanych

Usługi Windows Communication Foundation (WCF) publikują metadane, publikując co najmniej jeden punkt końcowy metadanych. Publikowanie metadanych usługi sprawia, że metadane są dostępne przy użyciu standardowych protokołów, takich jak WS-MetadataExchange (MEX) i HTTP/GET. Punkty końcowe metadanych są podobne do innych punktów końcowych usługi, które mają adres, powiązanie i kontrakt oraz mogą być dodawane do hosta usługi za pomocą konfiguracji lub w kodzie. Aby włączyć Publikowanie punktów końcowych metadanych, należy dodać <xref:System.ServiceModel.Description.ServiceMetadataBehavior> zachowanie usługi do usługi.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Instrukcje: publikowanie metadanych dla usługi za pomocą pliku konfiguracji](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Pokazuje, jak skonfigurować usługę WCF do publikowania metadanych, aby klienci mogli pobrać metadane przy użyciu WS-MetadataExchange lub żądania HTTP/GET przy użyciu `?wsdl` ciągu zapytania.  
  
 [Instrukcje: publikowanie metadanych dla usługi przy użyciu kodu](./feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Pokazuje, jak włączyć Publikowanie metadanych dla usługi WCF w kodzie, aby klienci mogli pobrać metadane przy użyciu WS-MetadataExchange lub żądania HTTP/GET przy użyciu `?wsdl` ciągu zapytania.  
  
## <a name="see-also"></a>Zobacz też

- [Publikowanie metadanych](./feature-details/publishing-metadata.md)
