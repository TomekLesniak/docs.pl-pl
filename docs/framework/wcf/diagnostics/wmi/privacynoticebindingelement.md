---
title: PrivacyNoticeBindingElement
ms.date: 03/30/2017
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
ms.openlocfilehash: c6ebb585454054ca9a03c46cf738001c58f9b18e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273415"
---
# <a name="privacynoticebindingelement"></a>PrivacyNoticeBindingElement

PrivacyNoticeBindingElement  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class PrivacyNoticeBindingElement : BindingElement  
{  
  sint32 PrivacyNoticeVersion;  
  string Url;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa PrivacyNoticeBindingElement nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa PrivacyNoticeBindingElement ma następujące właściwości:  
  
### <a name="privacynoticeversion"></a>PrivacyNoticeVersion  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Wersja informacji o prywatności.  
  
### <a name="url"></a>Url  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Adres URL, pod którym znajduje się powiadomienie dotyczące zachowania poufności informacji.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
