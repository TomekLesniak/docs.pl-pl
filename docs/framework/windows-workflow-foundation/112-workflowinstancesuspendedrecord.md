---
title: 112 — WorkflowInstanceSuspendedRecord
ms.date: 03/30/2017
ms.assetid: bc825c7c-8c90-48f7-9336-9a978a8246c6
ms.openlocfilehash: 697dfe18fdb4ae6c05ae758077c1c2d9198e053c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265820"
---
# <a name="112---workflowinstancesuspendedrecord"></a>112 — WorkflowInstanceSuspendedRecord

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|Id|112|  
|Słowa kluczowe|EndToEndMonitoring, rozwiązywanie problemów, HealthMonitoring, WFTracking|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane przez uczestnika śledzenia ETW, gdy wystąpienie przepływu pracy emituje rekord WorkflowInstanceSuspended.  
  
## <a name="message"></a>Wiadomość  

 TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, powód = %5, adnotacje = %6, ProfileName = %7  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|InstanceId|XS: GUID|Identyfikator wystąpienia przepływu pracy|  
|RecordNumber|XS: Long|Numer sekwencji emitowanego rekordu|  
|EventTime|XS: dateTime|Czas w formacie UTC, gdy zdarzenie zostało wyemitowane|  
|ActivityDefinitionId|XS: ciąg|Nazwa działania głównego w przepływie pracy|  
|Przyczyna|XS: ciąg|Przyczyna zawieszenia przepływu pracy|  
|Adnotacje|XS: ciąg|Adnotacje, które zostały dodane do tego zdarzenia.  Wartości są przechowywane w elemencie XML w formacie \<items> \< item  name = "annotationName" type="System.String"> annotationValue \</item> \</items> .  Jeśli adnotacje nie są określone, ciąg zawiera \<items/> . Rozmiar zdarzenia ETW jest ograniczony przez rozmiar buforu ETW lub maksymalny ładunek dla zdarzenia ETW. Jeśli rozmiar zdarzenia przekracza limity ETW, zdarzenie jest obcinane przez upuszczenie adnotacji i zamianę wartości adnotacji na \<items> ... \</items>|  
|ProfileName|XS: ciąg|Nazwa lub profil śledzenia, który spowodował wyemitowanie tego zdarzenia|  
|HostReference|XS: ciąg|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.  Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName ' przykład: ' domyślna witryna sieci Web/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
