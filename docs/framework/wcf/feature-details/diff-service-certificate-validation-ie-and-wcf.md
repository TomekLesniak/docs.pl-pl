---
title: Różnice między weryfikacją certyfikatów usług w programach Internet Explorer i WCF
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 574a6fa5411bcb662514982923e5c51200f98ae2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272205"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="77efb-102">Różnice między weryfikacją certyfikatów usług w programach Internet Explorer i WCF</span><span class="sxs-lookup"><span data-stu-id="77efb-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>

<span data-ttu-id="77efb-103">Ze względu na różnice między sposobem, w jaki program Internet Explorer i Windows Communication Foundation (WCF) weryfikują certyfikaty usługi przy użyciu protokołu HTTPS, istnieje możliwość, że program Internet Explorer nie będzie mógł uzyskać dostępu do strony pomocy lub Web Services Description Language (WSDL) usługi, mimo że klient WCF może pomyślnie wysyłać komunikaty do punktów końcowych usługi.</span><span class="sxs-lookup"><span data-stu-id="77efb-103">Because of difference between the way Internet Explorer and Windows Communication Foundation (WCF) validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a WCF client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="77efb-104">Wynika to z faktu, że program Internet Explorer sprawdza, czy certyfikat usługi zawiera `ServerAuthentication` identyfikatory obiektów (OID) w rozszerzonej flagi użycia, natomiast usługa WCF nie wymusza takiego ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="77efb-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas WCF does not enforce such a constraint.</span></span> <span data-ttu-id="77efb-105">Jeśli program Internet Explorer nie może uzyskać dostępu do strony pomocy usługi lub WSDL dla usługi, użyj [Narzędzia metadanych ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , aby uzyskać dostęp do metadanych usługi.</span><span class="sxs-lookup"><span data-stu-id="77efb-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77efb-106">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="77efb-106">See also</span></span>

- [<span data-ttu-id="77efb-107">Różnice dotyczące weryfikacji certyfikatów w protokołach HTTPS, SSL przez TCP i zabezpieczeniach SOAP</span><span class="sxs-lookup"><span data-stu-id="77efb-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [<span data-ttu-id="77efb-108">Instrukcje: pobieranie metadanych i implementowanie zgodnej usługi</span><span class="sxs-lookup"><span data-stu-id="77efb-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](how-to-retrieve-metadata-and-implement-a-compliant-service.md)
