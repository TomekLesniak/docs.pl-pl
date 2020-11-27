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
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Różnice między weryfikacją certyfikatów usług w programach Internet Explorer i WCF

Ze względu na różnice między sposobem, w jaki program Internet Explorer i Windows Communication Foundation (WCF) weryfikują certyfikaty usługi przy użyciu protokołu HTTPS, istnieje możliwość, że program Internet Explorer nie będzie mógł uzyskać dostępu do strony pomocy lub Web Services Description Language (WSDL) usługi, mimo że klient WCF może pomyślnie wysyłać komunikaty do punktów końcowych usługi. Wynika to z faktu, że program Internet Explorer sprawdza, czy certyfikat usługi zawiera `ServerAuthentication` identyfikatory obiektów (OID) w rozszerzonej flagi użycia, natomiast usługa WCF nie wymusza takiego ograniczenia. Jeśli program Internet Explorer nie może uzyskać dostępu do strony pomocy usługi lub WSDL dla usługi, użyj [Narzędzia metadanych ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , aby uzyskać dostęp do metadanych usługi.  
  
## <a name="see-also"></a>Zobacz też

- [Różnice dotyczące weryfikacji certyfikatów w protokołach HTTPS, SSL przez TCP i zabezpieczeniach SOAP](cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [Instrukcje: pobieranie metadanych i implementowanie zgodnej usługi](how-to-retrieve-metadata-and-implement-a-compliant-service.md)
