---
title: 114 — WorkflowInstanceRecordWithId
ms.date: 03/30/2017
ms.assetid: 2bd8b4a1-b210-4c07-8156-f19392318c08
ms.openlocfilehash: ebeff6af6d18d2794723250bceeecd682d0af6df
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261855"
---
# <a name="114---workflowinstancerecordwithid"></a>114 — WorkflowInstanceRecordWithId

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|114|  
|Słowa kluczowe|HealthMonitoring, WFTracking|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane przez uczestnika śledzenia funkcji ETW, gdy wystąpienie przepływu pracy emituje WorkflowInstanceRecord dla stanów przepływu pracy: rozpoczęte, wznowione, utrwalone, bezczynne, usunięte, ukończone, anulowane, zwolnione, niezawieszone.  
  
## <a name="message"></a>Wiadomość  

 TrackRecord = WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, adnotacje = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8  
  
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
