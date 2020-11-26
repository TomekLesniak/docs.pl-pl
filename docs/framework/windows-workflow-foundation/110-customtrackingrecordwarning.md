---
title: 110 — CustomTrackingRecordWarning
ms.date: 03/30/2017
ms.assetid: 3bc093de-be47-4ed0-983f-05b4246446fc
ms.openlocfilehash: 8fced5fe4baabac34b25b9a00421c3ded1c83ca6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238772"
---
# <a name="110---customtrackingrecordwarning"></a>110 — CustomTrackingRecordWarning

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|Id|110|  
|Słowa kluczowe|UserEvents, EndToEndMonitoring, rozwiązywanie problemów, HealthMonitoring, WFTracking|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane przez uczestnika śledzenia funkcji ETW, gdy działanie w wystąpieniu przepływu pracy emituje CustomTrackingRecord z ostrzeżeniem na poziomie  
  
## <a name="message"></a>Wiadomość  

 TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, nazwa = %4, ActivityName = %5, ActivityId = %6, ActivityInstanceId = %7, ActivityTypeName = %8, dane = %9, adnotacje = %10, nazwa pliku = %11  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|InstanceId|XS: GUID|Identyfikator wystąpienia przepływu pracy|  
|RecordNumber|XS: Long|Numer sekwencji emitowanego rekordu|  
|EventTime|XS: dateTime|Czas w formacie UTC, gdy zdarzenie zostało wyemitowane|  
|Nazwa|XS: ciąg|Nazwa CustomTrackingRecord|  
|ActivityName|XS: ciąg|Nazwa działania, które emituje CustomTrackingRecord|  
|ActivityId|XS: ciąg|Identyfikator działania, które emituje CustomTrackingRecord|  
|ActivityInstanceId|XS: ciąg|Identyfikator wystąpienia działania, które emituje CustomTrackingRecord|  
|ActivityTypeName|XS: ciąg|Nazwa działania, które emituje CustomTrackingRecord|  
|Dane|XS: ciąg|Dane, które zostały śledzone przy użyciu tego zdarzenia.  Wartości są przechowywane w elemencie XML w formacie \<items> \< item  name = "dataName" type="System.String"> wartość danych \</item> \</items> .  Jeśli żadne dane nie zostały śledzone, ciąg zawiera \<items/> . Rozmiar zdarzenia ETW jest ograniczony przez rozmiar buforu ETW lub maksymalny ładunek dla zdarzenia ETW. Jeśli rozmiar zdarzenia przekracza limity ETW, zdarzenie jest obcinane przez upuszczenie adnotacji i zamianę wartości danych na \<items> ... \</items>  Następujące typy są przechowywane jako ich wartości zwracane przez ToString (); ciąg, char, bool, int, Short, Long, uint, UShort, ULONG, system. Single, float, Double, system. GUID, system. DateTimeOffset, system. DateTime.  Wszystkie inne typy są serializowane przy użyciu funkcji system. Runtime. Serialization. NetDataContractSerializer.|  
|Adnotacje|XS: ciąg|Adnotacje, które zostały dodane do tego zdarzenia.  Wartości są przechowywane w elemencie XML w formacie \<items> \< item  name = "annotationName" type="System.String"> annotationValue \</item> \</items> .  Jeśli adnotacje nie są określone, ciąg zawiera \<items/> . Rozmiar zdarzenia ETW jest ograniczony przez rozmiar buforu ETW lub maksymalny ładunek dla zdarzenia ETW. Jeśli rozmiar zdarzenia przekracza limity ETW, zdarzenie jest obcinane przez upuszczenie adnotacji i zamianę wartości adnotacji na \<items> ... \</items>|  
|ProfileName|XS: ciąg|Nazwa lub profil śledzenia, który spowodował wyemitowanie tego zdarzenia|  
|HostReference|XS: ciąg|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.  Jego format jest zdefiniowany jako ścieżka&#124;wirtualna aplikacji nazwa witryny sieci Web,&#124;ServiceName "przykład:" domyślna witryna sieci Web/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService "|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
