---
title: 105 — FaultPropagationRecord
ms.date: 03/30/2017
ms.assetid: 168473b1-b1e5-4e9f-8a2a-35bbdb2ef531
ms.openlocfilehash: 3390a77f16cc52e52ea1b3e4c1a34d0f44795abb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238915"
---
# <a name="105---faultpropagationrecord"></a>105 — FaultPropagationRecord

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|Id|105|  
|Słowa kluczowe|EndToEndMonitoring, rozwiązywanie problemów, HealthMonitoring, WFTracking|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane przez uczestnika śledzenia funkcji ETW, gdy działanie z wystąpieniem przepływu pracy emituje FaultPropagationRecord.  
  
## <a name="message"></a>Wiadomość  

 TrackRecord = FaultPropagationRecord, identyfikator wystąpienia = %1, RecordNumber = %2, EventTime = %3, FaultSourceActivityName = %4, FaultSourceActivityId = %5, FaultSourceActivityInstanceId = %6, FaultSourceActivityTypeName = %7, FaultHandlerActivityName = %8, FaultHandlerActivityId = %9, FaultHandlerActivityInstanceId = %10, FaultHandlerActivityTypeName = %11, błąd = %12, IsFaultSource = %13, adnotacje = %14, ProfileName = %15  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|InstanceId|XS: GUID|Identyfikator wystąpienia przepływu pracy|  
|RecordNumber|XS: Long|Numer sekwencji emitowanego rekordu|  
|EventTime|XS: dateTime|Czas w formacie UTC, gdy zdarzenie zostało wyemitowane|  
|FaultSourceActivityName|XS: ciąg|Nazwa działania, które emituje błąd|  
|FaultSourceActivityId|XS: ciąg|Identyfikator działania, które emituje błąd|  
|FaultSourceActivityInstanceId|XS: ciąg|Identyfikator wystąpienia działania, które emituje błąd|  
|FaultSourceActivityTypeName|XS: ciąg|Typ działania, które emituje błąd|  
|FaultHandlerActivityName|XS: ciąg|Nazwa wyświetlana działania procedury obsługi błędów|  
|FaultHandlerActivityId|XS: ciąg|Identyfikator działania programu obsługi błędów|  
|FaultHandlerActivityInstanceId|XS: ciąg|Identyfikator wystąpienia działania programu obsługi błędów|  
|FaultHandlerActivityTypeName|XS: ciąg|Typ działania programu obsługi błędów|  
|Powodu|XS: ciąg|Szczegóły błędu|  
|IsFaultSource|XS: unsignedByte|Wskazuje, czy zdarzenie zostało wyemitowane ze źródła błędu|  
|Adnotacje|XS: ciąg|Adnotacje, które zostały dodane do tego zdarzenia.  Wartości są przechowywane w elemencie XML w formacie \<items> \< item  name = "annotationName" type="System.String"> annotationValue \</item> \</items> .  Jeśli adnotacje nie są określone, ciąg zawiera \<items/> . Rozmiar zdarzenia ETW jest ograniczony przez rozmiar buforu ETW lub maksymalny ładunek dla zdarzenia ETW. Jeśli rozmiar zdarzenia przekracza limity ETW, zdarzenie jest obcinane przez upuszczenie adnotacji i zamianę wartości adnotacji na \<items> ... \</items>|  
|ProfileName|XS: ciąg|Nazwa lub profil śledzenia, który spowodował wyemitowanie tego zdarzenia|  
|HostReference|XS: ciąg|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.  Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName ' przykład: ' domyślna witryna sieci Web/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
