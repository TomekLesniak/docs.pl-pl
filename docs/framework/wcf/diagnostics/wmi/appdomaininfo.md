---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: c5c44f4d8f6d93443802d5e1950c4d850976c5b6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291131"
---
# <a name="appdomaininfo"></a>AppDomainInfo

Informacje o domenie aplikacji  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa AppDomainInfo nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa AppDomainInfo ma następujące właściwości:  
  
### <a name="appdomainid"></a>AppDomainId  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Identyfikator domeny aplikacji.  
  
### <a name="isdefault"></a>IsDefault  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wskazuje, czy domena aplikacji jest domyślną domeną aplikacji.  
  
### <a name="logmalformedmessages"></a>LogMalformedMessages  

 Typ danych: wartość logiczna  
  
 Typ dostępu: odczyt/zapis  
  
 Wartość określająca, czy źle sformułowane komunikaty są rejestrowane.  
  
### <a name="logmessagesatservicelevel"></a>LogMessagesAtServiceLevel  

 Typ danych: wartość logiczna  
  
 Typ dostępu: odczyt/zapis  
  
 Wartość określająca, czy komunikaty są śledzone na poziomie usługi (przed szyfrowaniem i transformacjemi związanymi z transportem).  
  
### <a name="logmessagesattransportlevel"></a>LogMessagesAtTransportLevel  

 Typ danych: wartość logiczna  
  
 Typ dostępu: odczyt/zapis  
  
 Wartość określająca, czy komunikaty są śledzone na poziomie transportu.  
  
### <a name="messageloggingtracelisteners"></a>MessageLoggingTraceListeners  

 Typ danych: tablica TraceListener  
  
 Typ dostępu: tylko do odczytu  
  
 Detektory śledzenia kolekcji, które nasłuchują źródła śledzenia system. WMI. MessageLogging.  
  
### <a name="name"></a>Nazwa  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Nazwa domeny aplikacji.  
  
### <a name="performancecounters"></a>Liczniki wydajności  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Zakres aktywnych liczników wydajności w domenie aplikacji.  
  
### <a name="processid"></a>Identyfikator procesu  

 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Identyfikator procesu.  
  
### <a name="serviceconfigpath"></a>ServiceConfigPath  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Ścieżka do konfiguracji usługi.  
  
### <a name="tracelevel"></a>TraceLevel  

 Typ danych: ciąg  
  
 Typ dostępu: odczyt/zapis  
  
 Poziom śledzenia źródła śledzenia system. WMI.  
  
### <a name="servicemodeltracelisteners"></a>ServiceModelTraceListeners  

 Typ danych: tablica TraceListener  
  
 Typ dostępu: tylko do odczytu  
  
 Kolekcja odbiorników ze źródła śledzenia system. ServiceModel.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|
