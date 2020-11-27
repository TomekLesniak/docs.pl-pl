---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 6590c5188e4e1758987a75fbd007099703ea6bc5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250427"
---
# <a name="msmqtransportbindingelement"></a>MsmqTransportBindingElement

MsmqTransportBindingElement  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa MsmqTransportBindingElement nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa MsmqTransportBindingElement ma następujące właściwości:  
  
### <a name="maxpoolsize"></a>MaxPoolSize  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalny rozmiar puli zawierającej wewnętrzne obiekty wiadomości MSMQ.  
  
### <a name="queuetransferprotocol"></a>QueueTransferProtocol  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość wyliczenia wskazująca transport kanału komunikacyjnego znajdującego się w kolejce, który jest wykorzystywany przez to powiązanie.  
  
### <a name="useactivedirectory"></a>UseActiveDirectory  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Zwraca wartość logiczną wskazującą, czy adresy kolejek mają być konwertowane przy użyciu Active Directory.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
