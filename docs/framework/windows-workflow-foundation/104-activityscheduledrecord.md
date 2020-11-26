---
title: 104 — ActivityScheduledRecord
ms.date: 03/30/2017
ms.assetid: ae202178-8fb1-4646-a3aa-18beeda8ff93
ms.openlocfilehash: b2c7cbd169053188d5e84a0b8afd87c4916c87cb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238967"
---
# <a name="104---activityscheduledrecord"></a>104 — ActivityScheduledRecord

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|Id|104|  
|Słowa kluczowe|EndToEndMonitoring, rozwiązywanie problemów, HealthMonitoring, WFTracking|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane przez uczestnika śledzenia funkcji ETW, gdy działanie w wystąpieniu przepływu pracy emituje ActivityScheduledRecord  
  
## <a name="message"></a>Wiadomość  

 TrackRecord = ActivityScheduledRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, Name = %4, ActivityId = %5, ActivityInstanceId = %6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName = %11, adnotacje = %12, ProfileName = %13  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|InstanceId|XS: GUID|Identyfikator wystąpienia przepływu pracy|  
|RecordNumber|XS: Long|Numer sekwencji emitowanego rekordu|  
|EventTime|XS: dateTime|Czas w formacie UTC, gdy zdarzenie zostało wyemitowane|  
|Nazwa|XS: ciąg|Nazwa działania, które zaplanował działanie podrzędne|  
|ActivityId|XS: ciąg|Identyfikator działania, które zaplanował działanie podrzędne|  
|ActivityInstanceId|XS: ciąg|Identyfikator wystąpienia działania, które zaplanował działanie podrzędne|  
|ActivityTypeName|XS: ciąg|Typ działania, które zażądało operacji anulowania.|  
|ChildActivityName|XS: ciąg|Nazwa zaplanowanego działania|  
|ChildActivityId|XS: ciąg|Identyfikator zaplanowanego działania|  
|ChildActivityInstanceId|XS: ciąg|Identyfikator wystąpienia zaplanowanego działania|  
|ChildActivityTypeName|XS: ciąg|Typ zaplanowanego działania|  
|Adnotacje|XS: ciąg|Adnotacje, które zostały dodane do tego zdarzenia.  Wartości są przechowywane w elemencie XML w formacie \<items> \< item  name = "annotationName" type="System.String"> annotationValue \</item> \</items> .  Jeśli adnotacje nie są określone, ciąg zawiera \<items/> . Rozmiar zdarzenia ETW jest ograniczony przez rozmiar buforu ETW lub maksymalny ładunek dla zdarzenia ETW. Jeśli rozmiar zdarzenia przekracza limity ETW, zdarzenie jest obcinane przez upuszczenie adnotacji i zamianę wartości adnotacji na \<items> ... \</items>|  
|ProfileName|XS: ciąg|Nazwa lub profil śledzenia, który spowodował wyemitowanie tego zdarzenia|  
|HostReference|XS: ciąg|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.  Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName ' przykład: ' domyślna witryna sieci Web/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
