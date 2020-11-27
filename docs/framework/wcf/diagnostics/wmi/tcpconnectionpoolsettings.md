---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: de00cac851e4c6d0fd6df16f3a01b65bb5f43415
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294680"
---
# <a name="tcpconnectionpoolsettings"></a>TcpConnectionPoolSettings

TcpConnectionPoolSettings  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa TcpConnectionPoolSettings nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa TcpConnectionPoolSettings ma następujące właściwości:  
  
### <a name="groupname"></a>GroupName  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Nazwa grupy puli połączeń używanej przez element powiązania.  
  
### <a name="idletimeout"></a>Czynności  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalny czas bezczynności połączenia przed jego rozłączeniem.  
  
### <a name="leasetimeout"></a>LeaseTimeout  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Limit czasu oczekiwania na zakończenie operacji dzierżawy.  
  
### <a name="maxoutboundconnectionsperendpoint"></a>MaxOutboundConnectionsPerEndpoint  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba połączeń wychodzących dla każdego punktu końcowego.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
