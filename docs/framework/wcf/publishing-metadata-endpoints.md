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
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="cb7a7-102">Publikowanie punktów końcowych metadanych</span><span class="sxs-lookup"><span data-stu-id="cb7a7-102">Publishing Metadata Endpoints</span></span>

<span data-ttu-id="cb7a7-103">Usługi Windows Communication Foundation (WCF) publikują metadane, publikując co najmniej jeden punkt końcowy metadanych.</span><span class="sxs-lookup"><span data-stu-id="cb7a7-103">Windows Communication Foundation (WCF) services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="cb7a7-104">Publikowanie metadanych usługi sprawia, że metadane są dostępne przy użyciu standardowych protokołów, takich jak WS-MetadataExchange (MEX) i HTTP/GET.</span><span class="sxs-lookup"><span data-stu-id="cb7a7-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="cb7a7-105">Punkty końcowe metadanych są podobne do innych punktów końcowych usługi, które mają adres, powiązanie i kontrakt oraz mogą być dodawane do hosta usługi za pomocą konfiguracji lub w kodzie.</span><span class="sxs-lookup"><span data-stu-id="cb7a7-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="cb7a7-106">Aby włączyć Publikowanie punktów końcowych metadanych, należy dodać <xref:System.ServiceModel.Description.ServiceMetadataBehavior> zachowanie usługi do usługi.</span><span class="sxs-lookup"><span data-stu-id="cb7a7-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cb7a7-107">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="cb7a7-107">In This Section</span></span>  

 [<span data-ttu-id="cb7a7-108">Instrukcje: publikowanie metadanych dla usługi za pomocą pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="cb7a7-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="cb7a7-109">Pokazuje, jak skonfigurować usługę WCF do publikowania metadanych, aby klienci mogli pobrać metadane przy użyciu WS-MetadataExchange lub żądania HTTP/GET przy użyciu `?wsdl` ciągu zapytania.</span><span class="sxs-lookup"><span data-stu-id="cb7a7-109">Demonstrates how to configure a WCF service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="cb7a7-110">Instrukcje: publikowanie metadanych dla usługi przy użyciu kodu</span><span class="sxs-lookup"><span data-stu-id="cb7a7-110">How to: Publish Metadata for a Service Using Code</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="cb7a7-111">Pokazuje, jak włączyć Publikowanie metadanych dla usługi WCF w kodzie, aby klienci mogli pobrać metadane przy użyciu WS-MetadataExchange lub żądania HTTP/GET przy użyciu `?wsdl` ciągu zapytania.</span><span class="sxs-lookup"><span data-stu-id="cb7a7-111">Demonstrates how to enable metadata publishing for a WCF service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb7a7-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cb7a7-112">See also</span></span>

- [<span data-ttu-id="cb7a7-113">Publikowanie metadanych</span><span class="sxs-lookup"><span data-stu-id="cb7a7-113">Publishing Metadata</span></span>](./feature-details/publishing-metadata.md)
