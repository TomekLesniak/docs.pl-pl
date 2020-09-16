---
title: Rekordy śledzenia
ms.date: 03/30/2017
ms.assetid: 51adbda3-bd8b-4892-a8ea-d343186472d2
ms.openlocfilehash: 498d62fb1d3cc1386ea3bf57de431c57b18b7dda
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551304"
---
# <a name="tracking-records"></a>Rekordy śledzenia
Środowisko uruchomieniowe przepływu pracy jest Instrumentacją do emisji rekordów śledzenia w celu wykonania wystąpienia przepływu pracy.  
  
## <a name="tracking-records"></a>Rekordy śledzenia  
 W poniższej tabeli przedstawiono szczegółowe informacje o rekordach śledzenia, które są emitowane przez środowisko uruchomieniowe przepływu pracy.  
  
|Rekord śledzenia|Opis|  
|---------------------|-----------------|  
|Rekordy cyklu życia przepływu pracy|Emitowane na różnych etapach cyklu życia wystąpienia przepływu pracy. Na przykład rekord jest emitowany, gdy przepływ pracy zostanie uruchomiony lub zakończony.|  
|Rekordy cyklu życia aktywności|Szczegóły wykonywania działania. Te rekordy wskazują stan działania przepływu pracy, np. Kiedy działanie zostało zaplanowane, gdy działanie zostało zakończone, lub gdy wystąpi błąd.|  
|Rekordy wznawiania zakładki|Emitowane za każdym razem, gdy zostanie wznowiona Zakładka w wystąpieniu przepływu pracy.|  
|Niestandardowe rekordy śledzenia|Autor przepływu pracy może tworzyć niestandardowe rekordy śledzenia i emitować je w ramach działania niestandardowego.|  
  
 Wszystkie rekordy związane ze śledzeniem emitowane z środowiska uruchomieniowego WF pochodzą od klasy bazowej <xref:System.Activities.Tracking.TrackingRecord> , która zawiera wspólny zestaw danych. Śledzenie rekordów przedstawia cykl życia prostego przepływu pracy. Każdy rekord śledzenia zawiera szczegółowe informacje o skojarzonym zdarzeniu śledzenia, takie jak <xref:System.Activities.Tracking.TrackingRecord.InstanceId%2A> , <xref:System.Activities.Tracking.TrackingRecord.RecordNumber%2A> , i dodatkowych informacjach specyficznych dla typu rekordu śledzenia.  
  
 Następujące typy <xref:System.Activities.Tracking.TrackingRecord> obiektów są emitowane przez środowisko uruchomieniowe przepływu pracy:  
  
- **WorkflowInstanceRecord** — <xref:System.Activities.Tracking.TrackingRecord> opisuje cykl życia wystąpienia przepływu pracy. Na przykład rekord jest emitowany, gdy przepływ pracy zostanie uruchomiony lub zakończony i zawiera stan wystąpienia przepływu pracy. Szczegóły tego rekordu można znaleźć pod adresem <xref:System.Activities.Tracking.WorkflowInstanceRecord> .  
  
- **WorkflowInstanceAbortedRecord** — <xref:System.Activities.Tracking.TrackingRecord> jest emitowany w przypadku przerwania wystąpienia przepływu pracy. Rekord zawiera przyczynę przerwania wystąpienia przepływu pracy. Szczegóły tego rekordu można znaleźć pod adresem <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord> .  
  
- **WorkflowInstanceUnhandledExceptionRecord** — <xref:System.Activities.Tracking.TrackingRecord> jest emitowany, jeśli wystąpi wyjątek w wystąpieniu przepływu pracy i nie jest obsługiwany przez żadne działanie. Rekord zawiera szczegóły wyjątku. Szczegóły tego rekordu można znaleźć pod adresem <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> .  
  
- **WorkflowInstanceSuspendedRecord** — <xref:System.Activities.Tracking.TrackingRecord> jest emitowany za każdym razem, gdy wystąpienie przepływu pracy zostanie zawieszone. Rekord zawiera przyczynę wstrzymania wystąpienia przepływu pracy. Szczegóły tego rekordu można znaleźć pod adresem <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord> .  
  
- **WorkflowInstanceTerminatedRecord** — <xref:System.Activities.Tracking.TrackingRecord> jest emitowany za każdym razem, gdy wystąpienie przepływu pracy zostanie zakończone. Rekord zawiera przyczynę przerwania wystąpienia przepływu pracy. Szczegóły tego rekordu można znaleźć pod adresem <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord> .  
  
- **ActivityStateRecord** — <xref:System.Activities.Tracking.TrackingRecord> jest emitowany, gdy działanie w przepływie pracy jest wykonywane. Te rekordy wskazują stan działania w ramach wystąpienia przepływu pracy. Szczegóły tego rekordu można znaleźć pod adresem <xref:System.Activities.Tracking.ActivityStateRecord> .  
  
- **ActivityScheduledRecord** — <xref:System.Activities.Tracking.TrackingRecord> jest emitowany, gdy działanie powoduje zaplanowanie działania podrzędnego. Ten rekord zawiera szczegółowe informacje dotyczące działania nadrzędnego (działania związane z planowaniem) i zaplanowanego działania podrzędnego. Szczegóły tego rekordu można znaleźć pod adresem <xref:System.Activities.Tracking.ActivityScheduledRecord> .  
  
- **FaultPropagationRecord** — <xref:System.Activities.Tracking.TrackingRecord> jest emitowany dla każdej procedury obsługi, która przegląda rekord, dopóki nie zostanie obsłużony. Służy do oznaczania ścieżki, w której wystąpił błąd w wystąpieniu przepływu pracy. Szczegóły tego rekordu można znaleźć pod adresem <xref:System.Activities.Tracking.FaultPropagationRecord> .  
  
- **CancelRequestedRecord** — <xref:System.Activities.Tracking.TrackingRecord> jest emitowany za każdym razem, gdy działanie próbuje anulować działanie podrzędne. Ten rekord zawiera szczegółowe informacje dotyczące działania nadrzędnego i działania podrzędnego, które zostało anulowane. Szczegóły tego rekordu można znaleźć pod adresem <xref:System.Activities.Tracking.CancelRequestedRecord> .  
  
- **BookmarkResumptionRecord** — <xref:System.Activities.Tracking.TrackingRecord> śledzi wszystkie zakładki, które zostały pomyślnie wznowione. Szczegóły tego rekordu można znaleźć pod adresem <xref:System.Activities.Tracking.BookmarkResumptionRecord> .  
  
- **CustomTrackingRecord** — ten element <xref:System.Activities.Tracking.TrackingRecord> jest tworzony i emitowany przez autora przepływu pracy w ramach niestandardowego działania przepływu pracy. Niestandardowe rekordy śledzenia można wypełnić danymi, które mają być emitowane wraz z rekordami. Szczegóły tego rekordu można znaleźć pod adresem <xref:System.Activities.Tracking.CustomTrackingRecord> .  
  
 Na przykład może istnieć proste <xref:System.Activities.Statements.Sequence> działanie, które zawiera <xref:System.Activities.Statements.WriteLine> operacje z rekordami śledzenia emitowane w następującej kolejności:  
  
1. <xref:System.Activities.Tracking.WorkflowInstanceRecord> wskazuje, że przepływ pracy jest uruchamiany.  
  
2. <xref:System.Activities.Tracking.ActivityScheduledRecord> wskazuje, że działanie zostało zaplanowane. W takim przypadku jest to <xref:System.Activities.Statements.Sequence> działanie.  
  
3. <xref:System.Activities.Tracking.ActivityScheduledRecord> Reprezentuje <xref:System.Activities.Statements.WriteLine> działanie.  
  
4. Istnieją dwa <xref:System.Activities.Tracking.ActivityStateRecord> rekordy, które reprezentują dwie wykonywane działania.  
  
5. <xref:System.Activities.Tracking.WorkflowInstanceRecord> wskazuje, że przepływ pracy został ukończony.  
  
## <a name="see-also"></a>Zobacz także

- [Monitorowanie aplikacji sieci szkieletowej systemu Windows Server](/previous-versions/appfabric/ee677251(v=azure.10))
- [Monitorowanie aplikacji przy użyciu sieci szkieletowej aplikacji](/previous-versions/appfabric/ee677276(v=azure.10))
