---
title: ReliableSessionBindingElement
ms.date: 03/30/2017
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
ms.openlocfilehash: f91e38ab88cd9f93e9bec0e3a6ca65254bc49570
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273324"
---
# <a name="reliablesessionbindingelement"></a>ReliableSessionBindingElement

ReliableSessionBindingElement  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa elementu ReliableSessionBindingElement nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa elementu ReliableSessionBindingElement ma następujące właściwości:  
  
### <a name="acknowledgementinterval"></a>AcknowledgementInterval  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Przedział czasu, przez który miejsce docelowe czeka przed wysłaniem potwierdzenia do źródła wiadomości w niezawodnych kanałach, które są tworzone przez fabrykę.  
  
### <a name="flowcontrolenabled"></a>FlowControlEnabled  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość logiczna określająca, czy włączono sterowanie przepływem.  
  
### <a name="inactivitytimeout"></a>InactivityTimeout  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Określa maksymalny czas, przez który kanał zezwoli innemu nadawcy na wysyłanie komunikatów przed awarią kanału.  
  
### <a name="maxpendingchannels"></a>MaxPendingChannels  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba kanałów oczekujących na akceptację odbiornika.  
  
### <a name="maxretrycount"></a>MaxRetryCount  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba prób ponownego wysłania komunikatu przez niezawodny kanał, dla którego nie odebrano potwierdzenia, przez wywołanie `Send` jego podstawowego kanału.  
  
### <a name="maxtransferwindowsize"></a>MaxTransferWindowSize  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalny rozmiar okna transferu dla niezawodnej sesji.  
  
### <a name="ordered"></a>Zamówione  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość logiczna określająca, czy komunikaty są gwarantowane w kolejności, w jakiej zostały wysłane.  
  
### <a name="reliablemessagingversion"></a>ReliableMessagingVersion określająca  

 Typ danych: liczba całkowita  
  
 Typ dostępu: tylko do odczytu  
  
 Liczba całkowita, która określa wersję protokołu WS-ReliableMessaging użytą w niezawodnej sesji.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
