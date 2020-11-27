---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: dba4abd74cdddeb2b641feec5902413fe0704b1f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262297"
---
# <a name="servicedebugbehavior"></a>ServiceDebugBehavior

ServiceDebugBehavior  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa ServiceDebugBehavior nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa ServiceDebugBehavior ma następujące właściwości:  
  
### <a name="httphelppageenabled"></a>HttpHelpPageEnabled  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, czy usługa publikuje swoje WSDL pod adresem kontrolowanym przez `HttpGetUrl` atrybut.  
  
### <a name="httphelppageurl"></a>HttpHelpPageUrl  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Określa lokalizację, w której publikowana jest WSDL usługi do pobrania przy użyciu protokołu HTTP.  
  
### <a name="httpshelppageenabled"></a>HttpsHelpPageEnabled  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, czy usługa publikuje swoje WSDL za pośrednictwem protokołu HTTPS pod adresem kontrolowanym przez `HttpsGetUrl` atrybut.  
  
### <a name="httpshelppageurl"></a>HttpsHelpPageUrl  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Określa lokalizację, w której publikowana jest WSDL usługi do pobrania przy użyciu protokołu HTTPS.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, czy informacje o zarządzanych wyjątkach mają być dołączane do szczegółowych informacji o błędach SOAP zwracanych do klientów na potrzeby debugowania.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
