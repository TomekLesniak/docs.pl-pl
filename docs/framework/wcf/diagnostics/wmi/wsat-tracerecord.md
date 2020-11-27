---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 0409277821a7cca3f97fcec1bb383aba9583a1f6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262219"
---
# <a name="wsat_tracerecord"></a>WSAT_TraceRecord

WSAT_TraceRecord  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa WSAT_TraceRecord nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa WSAT_TraceRecord ma następujące właściwości:  
  
### <a name="activityid"></a>ActivityID  

 Typ danych: obiekt  
Typ dostępu: tylko do odczytu  
  
 Identyfikator działania rekordu śledzenia.  
  
### <a name="eventid"></a>Identyfikator zdarzenia  

 Typ danych: sint32  
Typ dostępu: tylko do odczytu  
  
 Identyfikator zdarzenia rekordu śledzenia.  
  
### <a name="tracerecord"></a>TraceRecord  

 Typ danych: ciąg  
Typ dostępu: tylko do odczytu  
  
 Rekord śledzenia  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|
