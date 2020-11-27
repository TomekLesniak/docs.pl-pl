---
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: 551761af255681dd2c2dbb9e40b7103c95cd2e0a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267224"
---
# <a name="textmessageencodingbindingelement"></a>TextMessageEncodingBindingElement

TextMessageEncodingBindingElement  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa TextMessageEncodingBindingElement nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa TextMessageEncodingBindingElement ma następujące właściwości:  
  
### <a name="encoding"></a>Encoding  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Kodowanie zestawu znaków, które ma być używane do emitowania komunikatów w powiązaniu.  
  
### <a name="maxreadpoolsize"></a>MaxReadPoolSize  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Liczba całkowita, która określa, ile komunikatów można jednocześnie odczytać bez przydziału nowych czytników.  
  
### <a name="maxwritepoolsize"></a>MaxWritePoolSize  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Liczba całkowita, która określa, ile komunikatów można jednocześnie wysłać bez przydziału nowych modułów zapisujących.  
  
### <a name="readerquotas"></a>ReaderQuotas  

 Typ danych: XmlDictionaryReaderQuotas  
  
 Typ dostępu: tylko do odczytu  
  
 Przydziały czytelników.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
