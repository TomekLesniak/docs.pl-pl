---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: c5bb7813a680c89eb90f4ccf4ed6f09a831c8095
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262206"
---
# <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas

XmlDictionaryReaderQuotas  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa XmlDictionaryReaderQuotas nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa XmlDictionaryReaderQuotas ma następujące właściwości:  
  
### <a name="maxarraylength"></a>MaxArrayLength  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna dozwolona długość tablicy.  
  
### <a name="maxbytesperread"></a>MaxBytesPerRead  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna dozwolona liczba bajtów zwracana dla każdego odczytu.  
  
### <a name="maxdepth"></a>MaxDepth  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna głębokość zagnieżdżenia węzłów dla każdego odczytu.  
  
### <a name="maxnametablecharcount"></a>MaxNameTableCharCount  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna dozwolona liczba znaków w nazwie tabeli.  
  
### <a name="maxstringcontentlength"></a>MaxStringContentLength  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna dozwolona liczba znaków w zawartości elementu XML.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
