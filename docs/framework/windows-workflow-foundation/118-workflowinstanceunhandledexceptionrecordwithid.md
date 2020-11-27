---
title: 118 — WorkflowInstanceUnhandledExceptionRecordWithId
ms.date: 03/30/2017
ms.assetid: 2ce4b193-e141-4cc4-86a3-2e8c984c110d
ms.openlocfilehash: 54bbb267902fe547821d4a5580f86da944ae70cd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278690"
---
# <a name="118---workflowinstanceunhandledexceptionrecordwithid"></a>118 — WorkflowInstanceUnhandledExceptionRecordWithId

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|118|  
|Słowa kluczowe|HealthMonitoring, WFTracking|  
|Poziom|Błąd|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane przez uczestnika śledzenia funkcji ETW, gdy wystąpienie przepływu pracy emituje WorkflowInstanceUnhandledExceptionRecord.  
  
## <a name="message"></a>Wiadomość  

 TrackRecord = WorkflowInstanceUnhandledExceptionRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, SourceName = %5, SourceId = %6, SourceInstanceId = %7, SourceTypeName = %8, wyjątek = %9, adnotacje = %10, ProfileName = %11, WorkflowDefinitionIdentity = %12  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|InstanceId|XS: GUID|Identyfikator wystąpienia przepływu pracy|  
|RecordNumber|XS: Long|Numer sekwencji emitowanego rekordu|  
|EventTime|XS: dateTime|Czas w formacie UTC, gdy zdarzenie zostało wyemitowane|  
|ActivityDefinitionId|XS: ciąg|Nazwa działania głównego w przepływie pracy|  
|SourceName|XS: ciąg|Nazwa działania źródłowego, która spowodowała błędy w unhandledException|  
|Identyfikator|XS: ciąg|Identyfikator działania dla działania źródła błędu|  
|SourceInstanceId|XS: ciąg|Identyfikator wystąpienia działania źródła błędu|  
|SourceTypeName|XS: ciąg|Nazwa typu działania źródłowego, która spowodowała błąd w unhandledException|  
|Wyjątek|XS: ciąg|Szczegóły wyjątku nieobsłużonego wyjątku|  
|Stan|XS: ciąg|Bieżący stan przepływu pracy.|  
|Adnotacje|XS: ciąg|Adnotacje, które zostały dodane do tego zdarzenia. Wartości są przechowywane w elemencie XML w formacie \<items> \< item name = "annotationName" type="System.String"> annotationValue \</item> \</items> . Jeśli adnotacje nie są określone, ciąg zawiera \<items/> . Rozmiar zdarzenia ETW jest ograniczony przez rozmiar buforu ETW lub maksymalny ładunek dla zdarzenia ETW. Jeśli rozmiar zdarzenia przekracza limity ETW, zdarzenie jest obcinane przez upuszczenie adnotacji i zamianę wartości adnotacji na \<items> ... \</items>|  
|ProfileName|XS: ciąg|Nazwa lub profil śledzenia, który spowodował wyemitowanie tego zdarzenia|  
|WorkflowDefinitionIdentity|XS: ciąg|Identyfikator definicji przepływu pracy|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
