---
title: Formaty metadanych
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: 01f0d7a2212b2af7e2d3a959ed91624edec46ce8
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720468"
---
# <a name="metadata-formats"></a>Formaty metadanych

Windows Communication Foundation (WCF) obsługuje formaty metadanych w poniższej tabeli.  
  
## <a name="metadata-specifications-and-usage"></a>Specyfikacje i użycie metadanych  
  
|Protokół|Specyfikacja i użycie|  
|--------------|-----------------------------|  
|WSDL 1,1|[Web Services Description Language (WSDL) 1,1](https://www.w3.org/TR/wsdl/)<br /><br /> Program WCF używa Web Services Description Language (WSDL) do opisywania usług.|  
|schemat XML|[Schemat XML — część 2: typy DataTypes Second Edition](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/) i [XML schematu część 1: Structures Second Edition](https://www.w3.org/TR/2004/REC-xmlschema-1-20041028/)<br /><br /> Funkcja WCF używa schematu XML do opisywania typów danych używanych w komunikatach.|  
|Zasady WS|[Zasady usług sieci Web 1,2 — Framework (WS-Policy)](https://www.w3.org/Submission/WS-Policy/)<br /><br /> [Zasady usług sieci Web 1,5 — architektura](https://www.w3.org/TR/ws-policy/)<br /><br /> Funkcja WCF używa specyfikacji WS-Policy 1,2 lub 1,5 z potwierdzeniami specyficznymi dla domeny w celu opisywania wymagań i możliwości usługi.|  
|Załączniki zasad WS|[Zasady usług sieci Web 1,2 — załącznik (WS-PolicyAttachment)](https://www.w3.org/Submission/WS-PolicyAttachment/)<br /><br /> W programie WCF Zaimplementowane są załączniki WS-Policy, które umożliwiają dołączanie wyrażeń zasad w różnych zakresach w języku WSDL.|  
|Wymiana metadanych WS|[Wymiana metadanych usług sieci Web (WS-MetadataExchange) w wersji 1,1](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> Funkcja WCF implementuje usługę WS-MetadataExchange, aby pobrać schemat XML, WSDL i WS-Policy.|  
|Powiązanie adresów WS dla języka WSDL|[Usługi sieci Web adresowanie 1,0 — Powiązanie WSDL](https://www.w3.org/TR/ws-addr-wsdl/)<br /><br /> Funkcja WCF implementuje powiązanie WS-Addressing dla języka WSDL w celu dołączenia informacji dotyczących adresów w języku WSDL.|  
  
## <a name="see-also"></a>Zobacz też

- [Protokoły usług sieci Web obsługiwane przez wiązania współdziałania udostępnione przez system](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL i zasady](wsdl-and-policy.md)
