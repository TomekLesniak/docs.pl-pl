---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 8422e1adf9a8914b631431eba5c9c0ed058cd0f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258026"
---
# <a name="namedpipeconnectionpoolsettings"></a>NamedPipeConnectionPoolSettings

NamedPipeConnectionPoolSettings  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa NamedPipeConnectionPoolSettings nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa NamedPipeConnectionPoolSettings ma następujące właściwości:  
  
### <a name="groupname"></a>GroupName  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Nazwa grupy puli połączeń używanej przez element powiązania.  
  
### <a name="idletimeout"></a>Czynności  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalny czas bezczynności połączenia przed jego rozłączeniem.  
  
### <a name="maxoutboundconnectionsperendpoint"></a>MaxOutboundConnectionsPerEndpoint  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba połączeń wychodzących dla każdego punktu końcowego na komputerze klienckim.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
