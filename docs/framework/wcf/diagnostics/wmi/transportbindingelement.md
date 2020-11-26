---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: 45bfcd069391156bc85cc4c26f2b172770197a9e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234846"
---
# <a name="transportbindingelement"></a>TransportBindingElement

TransportBindingElement  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa TransportBindingElement nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa TransportBindingElement ma następujące właściwości:  
  
### <a name="manualaddressing"></a>Opcję ManualAddressing  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość logiczna określająca, czy użytkownik chce przejąć kontrolę nad adresowaniem komunikatów.  
  
### <a name="maxbufferpoolsize"></a>MaxBufferPoolSize  

 Typ danych: sint64  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalny rozmiar puli buforów dla powiązania.  
  
### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize  

 Typ danych: sint64  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalny rozmiar wiadomości przetwarzanej przez to powiązanie.  
  
### <a name="scheme"></a>Schemat  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Schemat identyfikatora URI dla transportu.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.TransportBindingElement>
