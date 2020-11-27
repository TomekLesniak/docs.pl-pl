---
title: 103 — ActivityStateRecord
ms.date: 03/30/2017
ms.assetid: 57636a9a-561e-44aa-aef9-1f1894aaa6dd
ms.openlocfilehash: 02c33f02b7650c9f9b7527c319de3b58980fdd6c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275079"
---
# <a name="103---activitystaterecord"></a>103 — ActivityStateRecord

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|Id|103|  
|Słowa kluczowe|EndToEndMonitoring, rozwiązywanie problemów, HealthMonitoring, WFTracking|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane przez uczestnika śledzenia funkcji ETW, gdy działanie w wystąpieniu przepływu pracy emituje ActivityStateRecord  
  
## <a name="message"></a>Wiadomość  

 TrackRecord = ActivityStateRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, State = %4, Name = %5, ActivityId = %6, ActivityInstanceId = %7, ActivityTypeName = %8, argumenty = %9, zmienne = %10, adnotacje = %11, ProfileName = %12  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|InstanceId|XS: GUID|Identyfikator wystąpienia przepływu pracy|  
|RecordNumber|XS: Long|Numer sekwencji emitowanego rekordu|  
|EventTime|XS: dateTime|Czas w formacie UTC, gdy zdarzenie zostało wyemitowane|  
|Stan|XS: ciąg|Stan działania|  
|Nazwa|XS: ciąg|Nazwa wyświetlana działania, które emituje zdarzenie|  
|ActivityId|XS: ciąg|Identyfikator działania emitowania działania|  
|ActivityInstanceId|XS: ciąg|Identyfikator wystąpienia działania emitującego działanie|  
|ActivityTypeName|XS: ciąg|Nazwa typu emitowanego działania|  
|Argumenty|XS: ciąg|Argumenty, które były śledzone przy użyciu tego zdarzenia.  Wartości są przechowywane w elemencie XML w formacie \<items> \< item  name = "argumentName" type="System.String"> ArgumentValue \</item> \</items> .  Jeśli żadne argumenty nie zostały śledzone, ciąg zawiera \<items/> . Rozmiar zdarzenia ETW jest ograniczony przez rozmiar buforu ETW lub maksymalny ładunek dla zdarzenia ETW. Jeśli rozmiar zdarzenia przekracza limity ETW, zdarzenie jest obcinane przez upuszczenie adnotacji i zamianę wartości adnotacji na \<items> ... \</items>  Następujące typy są przechowywane jako ich wartości zwracane przez ToString (); ciąg, char, bool, int, Short, Long, uint, UShort, ULONG, system. Single, float, Double, system. GUID, system. DateTimeOffset, system. DateTime.  Wszystkie inne typy są serializowane przy użyciu funkcji system. Runtime. Serialization. NetDataContractSerializer.|  
|Zmienne|XS: ciąg|Zmienne, które były śledzone przy użyciu tego zdarzenia.  Wartości są przechowywane w elemencie XML w formacie \<items> \< item  name = "variableName" type="System.String"> VariableValue \</item> \</items> .  Jeśli żadne zmienne nie zostały śledzone, ciąg zawiera \<items/> . Rozmiar zdarzenia ETW jest ograniczony przez rozmiar buforu ETW lub maksymalny ładunek dla zdarzenia ETW. Jeśli rozmiar zdarzenia przekracza limity ETW, zdarzenie jest obcinane przez upuszczenie adnotacji i zamianę wartości zmiennych na \<items> ... \</items>  Następujące typy są przechowywane jako ich wartości zwracane przez ToString (); ciąg, char, bool, int, Short, Long, uint, UShort, ULONG, system. Single, float, Double, system. GUID, system. DateTimeOffset, system. DateTime.  Wszystkie inne typy są serializowane przy użyciu funkcji system. Runtime. Serialization. NetDataContractSerializer.|  
|Adnotacje|XS: ciąg|Adnotacje, które zostały dodane do tego zdarzenia.  Wartości są przechowywane w elemencie XML w formacie \<items> \< item  name = "annotationName" type="System.String"> annotationValue \</item> \</items> .  Jeśli adnotacje nie są określone, ciąg zawiera \<items/> . Rozmiar zdarzenia ETW jest ograniczony przez rozmiar buforu ETW lub maksymalny ładunek dla zdarzenia ETW. Jeśli rozmiar zdarzenia przekracza limity ETW, zdarzenie jest obcinane przez upuszczenie adnotacji i zamianę wartości adnotacji na \<items> ... \</items>|  
|ProfileName|XS: ciąg|Nazwa lub profil śledzenia, który spowodował wyemitowanie tego zdarzenia|  
|HostReference|XS: ciąg|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.  Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName ' przykład: ' domyślna witryna sieci Web/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
