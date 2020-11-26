---
title: 107 — BookmarkResumptionRecord
ms.date: 03/30/2017
ms.assetid: aa2d37ed-2bfa-439b-89e8-a9354027f155
ms.openlocfilehash: 14557ef2726a60bcde49d30f9d6168fd831e613c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238863"
---
# <a name="107----bookmarkresumptionrecord"></a>107 — BookmarkResumptionRecord

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|Id|107|  
|Słowa kluczowe|EndToEndMonitoring, rozwiązywanie problemów, HealthMonitoring, WFTracking|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane przez uczestnika śledzenia ETW, gdy wystąpienie przepływu pracy emituje BookmarkResumptionRecord.  
  
## <a name="message"></a>Wiadomość  

 TrackRecord = BookmarkResumptionRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, nazwa = %4, SubInstanceID = %5, OwnerActivityName = %6, OwnerActivityId = %7, OwnerActivityInstanceId = %8, OwnerActivityTypeName = %9, adnotacje = %10, nazwa pliku = %11  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|InstanceId|XS: GUID|Identyfikator wystąpienia przepływu pracy|  
|RecordNumber|XS: Long|Numer sekwencji emitowanego rekordu|  
|EventTime|XS: dateTime|Czas w formacie UTC, gdy zdarzenie zostało wyemitowane|  
|Nazwa|XS: ciąg|Nazwa wznowionej zakładki|  
|Identyfikator InstanceID|XS: GUID|Identyfikator zakresu zakładki|  
|OwnerActivityName|XS: ciąg|Nazwa działania zakładki|  
|OwnerActivityId|XS: ciąg|Identyfikator działania zakładki|  
|OwnerActivityInstanceId|XS: ciąg|Identyfikator wystąpienia działania zakładki|  
|OwnerActivityTypeName|XS: ciąg|Typ działania zakładki|  
|Adnotacje|XS: ciąg|Adnotacje, które zostały dodane do tego zdarzenia.  Wartości są przechowywane w elemencie XML w formacie \<items> \< item  name = "annotationName" type="System.String"> annotationValue \</item> \</items> .  Jeśli adnotacje nie są określone, ciąg zawiera \<items/> . Rozmiar zdarzenia ETW jest ograniczony przez rozmiar buforu ETW lub maksymalny ładunek dla zdarzenia ETW. Jeśli rozmiar zdarzenia przekracza limity ETW, zdarzenie jest obcinane przez upuszczenie adnotacji i zamianę wartości adnotacji na \<items> ... \</items>|  
|ProfileName|XS: ciąg|Nazwa lub profil śledzenia, który spowodował wyemitowanie tego zdarzenia|  
|HostReference|XS: ciąg|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.  Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName ' przykład: ' domyślna witryna sieci Web/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
