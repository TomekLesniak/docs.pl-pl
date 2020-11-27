---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ae6a3448896cb206bce8867daf7104c3e484ecc8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269018"
---
# <a name="peertransportbindingelement"></a>PeerTransportBindingElement

PeerTransportBindingElement  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa PeerTransportBindingElement nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa PeerTransportBindingElement ma następujące właściwości:  
  
### <a name="listenipaddress"></a>ListenIPAddress  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Adres IP, na którym węzeł równorzędny nasłuchuje komunikatów.  
  
### <a name="port"></a>Port  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Port interfejsu sieciowego, na którym to powiązanie przetwarza wiadomości kanału równorzędnego.  
  
### <a name="security"></a>Zabezpieczenia  

 Typ danych: PeerSecuritySettings  
  
 Typ dostępu: tylko do odczytu  
  
 Ustawienia zabezpieczeń transportu elementów równorzędnych.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
