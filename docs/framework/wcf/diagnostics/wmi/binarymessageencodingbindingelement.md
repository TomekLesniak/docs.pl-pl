---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: eb174d12731d7f1bc78f4d709cf043daf2346bd2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269798"
---
# <a name="binarymessageencodingbindingelement"></a>BinaryMessageEncodingBindingElement

BinaryMessageEncodingBindingElement  
  
## <a name="syntax"></a>Składnia  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa BinaryMessageEncodingBindingElement nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa BinaryMessageEncodingBindingElement ma następujące właściwości.  
  
## <a name="maxreadpoolsize"></a>MaxReadPoolSize  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Liczba całkowita, która określa, ile komunikatów można jednocześnie odczytać bez przydziału nowych czytników.  
  
## <a name="maxsessionsize"></a>MaxSessionSize  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość określająca wyrażony w bajtach rozmiar buforu używany do kodowania.  
  
## <a name="maxwritepoolsize"></a>MaxWritePoolSize  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Liczba całkowita, która określa, ile komunikatów można jednocześnie wysłać bez przydziału nowych modułów zapisujących.  
  
## <a name="readerquotas"></a>ReaderQuotas  

 Typ danych: XmlDictionaryReaderQuotas  
  
 Typ dostępu: tylko do odczytu  
  
 Przydziały czytelników.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
