---
title: 119 — WorkflowInstanceUpdatedRecord
ms.date: 03/30/2017
ms.assetid: 32485d0a-dcdb-45bc-b1e3-79fa9ad9439b
ms.openlocfilehash: c76ce2ffcd25ebe09463e6d704787f321baa2cb3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278664"
---
# <a name="119---workflowinstanceupdatedrecord"></a>119 — WorkflowInstanceUpdatedRecord

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|119|  
|Słowa kluczowe|HealthMonitoring, WFTracking|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane przez uczestnika śledzenia funkcji ETW podczas aktualizowania wystąpienia przepływu pracy.  
  
## <a name="message"></a>Wiadomość  

 TrackRecord = WorkflowInstanceUpdatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, adnotacje = %8, ProfileName = %9  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|InstanceId|XS: GUID|Identyfikator wystąpienia przepływu pracy|  
|RecordNumber|XS: Long|Numer sekwencji emitowanego rekordu|  
|EventTime|XS: dateTime|Czas w formacie UTC, gdy zdarzenie zostało wyemitowane|  
|ActivityDefinitionId|XS: ciąg|Nazwa działania głównego w przepływie pracy|  
|Stan|XS: ciąg|Bieżący stan przepływu pracy.|  
|OriginalDefinitionIdentity|XS: ciąg|Identyfikator definicji oryginalnego przepływu pracy|  
|UpdatedDefinitionIdentity|XS: ciąg|Zaktualizowany identyfikator definicji przepływu pracy|  
|Adnotacje|XS: ciąg|Adnotacje, które zostały dodane do tego zdarzenia. Wartości są przechowywane w elemencie XML w formacie \<items> \< item name = "annotationName" type="System.String"> annotationValue \</item> \</items> . Jeśli adnotacje nie są określone, ciąg zawiera \<items/> . Rozmiar zdarzenia ETW jest ograniczony przez rozmiar buforu ETW lub maksymalny ładunek dla zdarzenia ETW. Jeśli rozmiar zdarzenia przekracza limity ETW, zdarzenie jest obcinane przez upuszczenie adnotacji i zamianę wartości adnotacji na \<items> ... \</items>|  
|ProfileName|XS: ciąg|Nazwa lub profil śledzenia, który spowodował wyemitowanie tego zdarzenia|  
|WorkflowDefinitionIdentity|XS: ciąg|Identyfikator definicji przepływu pracy|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
