---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 806066a8845068413d2a52c78878f76b5f5fa34f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250375"
---
# <a name="onewaybindingelement"></a>OneWayBindingElement

OneWayBindingElement  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa OneWayBindingElement nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa OneWayBindingElement ma następujące właściwości:  
  
### <a name="channelpoolsettings"></a>ChannelPoolSettings  

 Typ danych: ChannelPoolSettings  
  
 Typ dostępu: tylko do odczytu  
  
 Ustawienia puli kanałów.  
  
### <a name="maxacceptedchannels"></a>MaxAcceptedChannels  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba zaakceptowanych kanałów.  
  
### <a name="packetroutable"></a>PacketRoutable  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość wskazująca, czy pakiet jest w trakcie routingu.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
