---
title: 106 — CancelRequestRecord
ms.date: 03/30/2017
ms.assetid: f72a59aa-8093-4a8e-94df-40acaffb1ffb
ms.openlocfilehash: e7b736d78486b0de7c108e6212d2aa1857e01cc4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238902"
---
# <a name="106---cancelrequestrecord"></a>106 — CancelRequestRecord

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|Id|106|  
|Słowa kluczowe|EndToEndMonitoring, rozwiązywanie problemów, HealthMonitoring, WFTracking|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane przez uczestnika śledzenia funkcji ETW, gdy działanie w wystąpieniu przepływu pracy emituje CancelRequestedRecord.  
  
## <a name="message"></a>Wiadomość  

 TrackRecord = CancelRequestedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, Name = %4, ActivityId = %5, ActivityInstanceId = %6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName = %11, adnotacje = %12, ProfileName = %13  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|InstanceId|XS: GUID|Identyfikator wystąpienia przepływu pracy|  
|RecordNumber|XS: Long|Numer sekwencji emitowanego rekordu|  
|EventTime|XS: dateTime|Czas w formacie UTC, gdy zdarzenie zostało wyemitowane|  
|Nazwa|XS: ciąg|Nazwa działania, które zażądało operacji anulowania.|  
|ActivityId|XS: ciąg|Identyfikator działania, które zażądało operacji anulowania.|  
|ActivityInstanceId|XS: ciąg|Identyfikator wystąpienia działania, które zażądało operacji anulowania.|  
|ActivityTypeName|XS: ciąg|Typ działania, które zażądało operacji anulowania.|  
|ChildActivityName|XS: ciąg|Nazwa anulowanego działania|  
|ChildActivityId|XS: ciąg|Identyfikator anulowanego działania|  
|ChildActivityInstanceId|XS: ciąg|Identyfikator wystąpienia działania, które zostało anulowane|  
|ChildActivityTypeName|XS: ciąg|Typ działania, które zostało anulowane|  
|Adnotacje|XS: ciąg|Adnotacje, które zostały dodane do tego zdarzenia.  Wartości są przechowywane w elemencie XML w formacie \<items> \< item  name = "annotationName" type="System.String"> annotationValue \</item> \</items> .  Jeśli adnotacje nie są określone, ciąg zawiera \<items/> . Rozmiar zdarzenia ETW jest ograniczony przez rozmiar buforu ETW lub maksymalny ładunek dla zdarzenia ETW. Jeśli rozmiar zdarzenia przekracza limity ETW, zdarzenie jest obcinane przez upuszczenie adnotacji i zamianę wartości adnotacji na \<items> ... \</items>|  
|ProfileName|XS: ciąg|Nazwa lub profil śledzenia, który spowodował wyemitowanie tego zdarzenia|  
|HostReference|XS: ciąg|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.  Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName ' przykład: ' domyślna witryna sieci Web/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
