---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 921a880dad0d77558a70dff8a09f75c25a3cbb8a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262284"
---
# <a name="servicemetadatabehavior"></a>ServiceMetadataBehavior

ServiceMetadataBehavior  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa ServiceMetadataBehavior nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa ServiceMetadataBehavior ma następujące właściwości:  
  
### <a name="externalmetadatalocation"></a>ExternalMetadataLocation  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Ustawia lokalizację, w której usługa przekierowuje żądania metadanych.  
  
### <a name="httpgetenabled"></a>HttpGetEnabled  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, czy usługa publikuje swoje WSDL pod adresem kontrolowanym przez `HttpGetUrl` atrybut.  
  
### <a name="httpgeturl"></a>HttpGetUrl  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Określa lokalizację, w której publikowana jest WSDL usługi do pobrania przy użyciu protokołu HTTP.  
  
### <a name="httpsgetenabled"></a>HttpsGetEnabled  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Określa, czy usługa publikuje swoje WSDL za pośrednictwem protokołu HTTPS pod adresem kontrolowanym przez `HttpsGetUrl` atrybut.  
  
### <a name="httpsgeturl"></a>HttpsGetUrl  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Określa lokalizację, w której publikowana jest WSDL usługi do pobrania przy użyciu protokołu HTTPS.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
