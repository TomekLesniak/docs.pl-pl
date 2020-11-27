---
title: Klasa kanału
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: a920636e7df9609b12834366b1488c80122f9fca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274234"
---
# <a name="channel-class"></a>Klasa kanału

Kanał  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa kanału nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa kanału ma następujące właściwości.  
  
### <a name="localaddress"></a>Localaddress wynosi  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Lokalny punkt końcowy kanału.  
  
### <a name="ref"></a>ref  

 Typ danych: punkt końcowy  
  
 Typ dostępu: tylko do odczytu  
  
 Odwołanie do punktu końcowego, z którym łączy się kanał.  
  
### <a name="remoteaddress"></a>RemoteAddress  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Adres zdalny skojarzony z kanałem.  
  
### <a name="sessionid"></a>SessionId  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Identyfikator bieżącej sesji (jeśli istnieje).  
  
### <a name="type"></a>Typ  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Typ kanału.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.ChannelBase>
