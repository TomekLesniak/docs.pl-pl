---
title: 115 — WorkflowInstanceAbortedRecordWithId
ms.date: 03/30/2017
ms.assetid: 0293dd4e-e6ae-473a-b3d6-c2d38f9bd875
ms.openlocfilehash: 69c0c58de36a7fff916b11deba888b7cef7c626e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285151"
---
# <a name="115---workflowinstanceabortedrecordwithid"></a>115 — WorkflowInstanceAbortedRecordWithId

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|115|  
|Słowa kluczowe|HealthMonitoring, WFTracking|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane przez uczestnika śledzenia funkcji ETW, gdy wystąpienie przepływu pracy emituje WorkflowInstanceAbortedRecord.  
  
## <a name="message"></a>Wiadomość  

 TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, powód = %5, adnotacje = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|InstanceId|XS: GUID|Identyfikator wystąpienia przepływu pracy|  
|RecordNumber|XS: Long|Numer sekwencji emitowanego rekordu|  
|EventTime|XS: dateTime|Czas w formacie UTC, gdy zdarzenie zostało wyemitowane|  
|ActivityDefinitionId|XS: ciąg|Nazwa działania głównego w przepływie pracy|  
|Stan|XS: ciąg|Bieżący stan przepływu pracy.|  
|Adnotacje|XS: ciąg|Adnotacje, które zostały dodane do tego zdarzenia. Wartości są przechowywane w elemencie XML w formacie \<items> \< item name = "annotationName" type="System.String"> annotationValue \</item> \</items> . Jeśli adnotacje nie są określone, ciąg zawiera \<items/> . Rozmiar zdarzenia ETW jest ograniczony przez rozmiar buforu ETW lub maksymalny ładunek dla zdarzenia ETW. Jeśli rozmiar zdarzenia przekracza limity ETW, zdarzenie jest obcinane przez upuszczenie adnotacji i zamianę wartości adnotacji na \<items> ... \</items>|  
|ProfileName|XS: ciąg|Nazwa lub profil śledzenia, który spowodował wyemitowanie tego zdarzenia|  
|WorkflowDefinitionIdentity|XS: ciąg|Identyfikator definicji przepływu pracy|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
