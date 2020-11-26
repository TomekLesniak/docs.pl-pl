---
title: 101 — WorkflowInstanceUnhandledExceptionRecord
ms.date: 03/30/2017
ms.assetid: ab7d50a0-5347-4390-8445-1def4dfdff6a
ms.openlocfilehash: f62868a09b72ef4fe567fbedc1729cd6bad309f0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239760"
---
# <a name="101---workflowinstanceunhandledexceptionrecord"></a>101 — WorkflowInstanceUnhandledExceptionRecord

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|Id|101|  
|Słowa kluczowe|EndToEndMonitoring, rozwiązywanie problemów, HealthMonitoring, WFTracking|  
|Poziom|Błąd|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane przez uczestnika śledzenia funkcji ETW, gdy wystąpienie przepływu pracy emituje WorkflowInstanceUnhandledExceptionRecord.  
  
## <a name="message"></a>Wiadomość  

 TrackRecord = WorkflowInstanceUnhandledExceptionRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, SourceName = %5, SourceId = %6, SourceInstanceId = %7, SourceTypeName = %8, wyjątek = %9, adnotacje = %10, ProfileName = %11  
  
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
|Adnotacje|XS: ciąg|Adnotacje, które zostały dodane do tego zdarzenia.  Wartości są przechowywane w elemencie XML w formacie \<items> \< item  name = "annotationName" type="System.String"> annotationValue \</item> \</items> .  Jeśli adnotacje nie są określone, ciąg zawiera \<items/> . Rozmiar zdarzenia ETW jest ograniczony przez rozmiar buforu ETW lub maksymalny ładunek dla zdarzenia ETW. Jeśli rozmiar zdarzenia przekracza limity ETW, zdarzenie jest obcinane przez upuszczenie adnotacji i zamianę wartości adnotacji na \<items> ... \</items>|  
|ProfileName|XS: ciąg|Nazwa lub profil śledzenia, który spowodował wyemitowanie tego zdarzenia|  
|HostReference|XS: ciąg|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.  Jego format jest zdefiniowany jako ścieżka&#124;wirtualna aplikacji nazwa witryny sieci Web,&#124;ServiceName "przykład:" domyślna witryna sieci Web/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService "|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
