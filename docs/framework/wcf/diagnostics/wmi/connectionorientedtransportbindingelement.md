---
title: ConnectionOrientedTransportBindingElement
ms.date: 03/30/2017
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
ms.openlocfilehash: 3c69b73cc05a56a7556630de0f83675590442293
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274156"
---
# <a name="connectionorientedtransportbindingelement"></a>ConnectionOrientedTransportBindingElement

ConnectionOrientedTransportBindingElement  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa ConnectionOrientedTransportBindingElement nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa ConnectionOrientedTransportBindingElement ma następujące właściwości:  
  
### <a name="channelinitializationtimeout"></a>ChannelInitializationTimeout  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Obiekt TimeSpan określający, jak długo Inicjalizacja kanału ma zostać ukończona przed upływem limitu czasu.  
  
### <a name="connectionbuffersize"></a>ConnectionBufferSize  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Rozmiar buforu używany do przesyłania fragmentu serializowanego komunikatu w sieci z klienta lub usługi.  
  
### <a name="hostnamecomparisonmode"></a>HostNameComparisonMode  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość wskazująca, czy nazwa hosta jest używana do uzyskiwania dostępu do usługi podczas dopasowywania identyfikatora URI.  
  
### <a name="maxbuffersize"></a>MaxBufferSize  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalny rozmiar buforu do użycia.  
  
### <a name="maxoutputdelay"></a>MaxOutputDelay  

 Typ danych: DateTime  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalny przedział czasu, przez który fragment komunikatu lub pełny komunikat może pozostawać w pamięci przed wysłaniem.  
  
### <a name="maxpendingaccepts"></a>MaxPendingAccepts  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba oczekujących asynchronicznych wątków akceptujących, które są dostępne do przetwarzania przychodzących połączeń z usługą.  
  
### <a name="maxpendingconnections"></a>MaxPendingConnections  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba oczekujących połączeń.  
  
### <a name="transfermode"></a>Elementy TransferMode  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość określająca, czy komunikaty są buforowane, czy przesyłane strumieniowo z transportem zorientowanym na połączenia.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
