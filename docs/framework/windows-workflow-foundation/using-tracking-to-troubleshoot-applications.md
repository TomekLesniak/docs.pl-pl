---
title: Używanie śledzenia do rozwiązywania problemów z aplikacjami
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: fc9427d0c06ed67ea69669cab2aae64f39f7c10c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551291"
---
# <a name="using-tracking-to-troubleshoot-applications"></a><span data-ttu-id="0fc83-102">Używanie śledzenia do rozwiązywania problemów z aplikacjami</span><span class="sxs-lookup"><span data-stu-id="0fc83-102">Using Tracking to Troubleshoot Applications</span></span>
<span data-ttu-id="0fc83-103">Funkcja Windows Workflow Foundation (WF) umożliwia śledzenie informacji związanych z przepływem pracy w celu uzyskania szczegółów dotyczących wykonywania Windows Workflow Foundation aplikacji lub usługi.</span><span class="sxs-lookup"><span data-stu-id="0fc83-103">Windows Workflow Foundation (WF) enables you to track workflow-related information to give details into the execution of a Windows Workflow Foundation application or service.</span></span> <span data-ttu-id="0fc83-104">Hosty Windows Workflow Foundation mogą przechwytywać zdarzenia przepływu pracy podczas wykonywania wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="0fc83-104">Windows Workflow Foundation hosts are able to capture workflow events during the execution of a workflow instance.</span></span> <span data-ttu-id="0fc83-105">Jeśli przepływ pracy generuje błędy lub wyjątki, można użyć szczegółów śledzenia Windows Workflow Foundation do rozwiązywania problemów z przetwarzaniem.</span><span class="sxs-lookup"><span data-stu-id="0fc83-105">If your workflow generates faults or exceptions, you can use the Windows Workflow Foundation tracking details to troubleshooting its processing.</span></span>  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a><span data-ttu-id="0fc83-106">Rozwiązywanie problemów z usługą WF przy użyciu śledzenia WF</span><span class="sxs-lookup"><span data-stu-id="0fc83-106">Troubleshooting a WF using WF Tracking</span></span>  
 <span data-ttu-id="0fc83-107">Aby wykryć błędy w trakcie przetwarzania działania Windows Workflow Foundation, można włączyć śledzenie z profilem śledzenia, który wysyła zapytanie o <xref:System.Activities.Tracking.ActivityStateRecord> stan błędu.</span><span class="sxs-lookup"><span data-stu-id="0fc83-107">To detect faults within the processing of a Windows Workflow Foundation activity, you can enable tracking with a tracking profile that queries for an <xref:System.Activities.Tracking.ActivityStateRecord> with the state of Faulted.</span></span> <span data-ttu-id="0fc83-108">Odpowiednie zapytanie jest określone w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="0fc83-108">The corresponding query is specified in the following code.</span></span>  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 <span data-ttu-id="0fc83-109">Jeśli błąd jest propagowany i obsługiwany w ramach procedury obsługi błędów (na przykład <xref:System.Activities.Statements.TryCatch> działania), można go wykryć przy użyciu <xref:System.Activities.Tracking.FaultPropagationRecord> .</span><span class="sxs-lookup"><span data-stu-id="0fc83-109">If a fault is propagated and handled within a fault handler (such as a <xref:System.Activities.Statements.TryCatch> activity) this can be detected using a <xref:System.Activities.Tracking.FaultPropagationRecord>.</span></span> <span data-ttu-id="0fc83-110"><xref:System.Activities.Tracking.FaultPropagationRecord>Wskazuje aktywność źródłową błędu i nazwę programu obsługi błędów.</span><span class="sxs-lookup"><span data-stu-id="0fc83-110">The <xref:System.Activities.Tracking.FaultPropagationRecord> indicates the source activity of the fault and the name of the fault handler.</span></span> <span data-ttu-id="0fc83-111"><xref:System.Activities.Tracking.FaultPropagationRecord>Zawiera szczegóły błędu w formie stosu wyjątków dla błędu.</span><span class="sxs-lookup"><span data-stu-id="0fc83-111">The <xref:System.Activities.Tracking.FaultPropagationRecord> contains fault details in form of the exception stack for the fault.</span></span> <span data-ttu-id="0fc83-112">Zapytanie w celu subskrybowania elementu <xref:System.Activities.Tracking.FaultPropagationRecord> jest pokazane w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="0fc83-112">The query to subscribe for a <xref:System.Activities.Tracking.FaultPropagationRecord> is shown in the following example.</span></span>  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 <span data-ttu-id="0fc83-113">Jeśli błąd nie jest obsługiwany w przepływie pracy, powoduje to nieobsłużony wyjątek w wystąpieniu przepływu pracy, a wystąpienie przepływu pracy zostało przerwane.</span><span class="sxs-lookup"><span data-stu-id="0fc83-113">If a fault is not handled within the workflow it results in an unhandled exception at the workflow instance and the workflow instance is aborted.</span></span> <span data-ttu-id="0fc83-114">Aby zrozumieć szczegóły nieobsługiwanego wyjątku, profil śledzenia musi wysyłać zapytania do rekordu wystąpienia przepływu pracy w `state name="UnhandledException"` sposób określony w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="0fc83-114">To understand the details of the unhandled exception, the tracking profile must query the workflow instance record with `state name="UnhandledException"` as specified in the following example.</span></span>  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 <span data-ttu-id="0fc83-115">Gdy wystąpienie przepływu pracy napotka nieobsłużony wyjątek, <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> obiekt jest emitowany, jeśli śledzenie Windows Workflow Foundation zostało włączone.</span><span class="sxs-lookup"><span data-stu-id="0fc83-115">When a workflow instance encounters an unhandled exception, a <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> object is emitted if Windows Workflow Foundation tracking has been enabled.</span></span>  
  
 <span data-ttu-id="0fc83-116">Ten rekord śledzenia zawiera szczegóły błędu w formie stosu wyjątków.</span><span class="sxs-lookup"><span data-stu-id="0fc83-116">This tracking record contains the fault details in the form of the exception stack.</span></span> <span data-ttu-id="0fc83-117">Ma szczegóły dotyczące źródła błędu (na przykład działania), które uległy awarii i spowodowały nieobsłużony wyjątek. Aby subskrybować zdarzenia błędów z Windows Workflow Foundation, Włącz śledzenie przez dodanie uczestnika śledzenia.</span><span class="sxs-lookup"><span data-stu-id="0fc83-117">It has details of the source of the fault (for example, the activity) that faulted and resulted in the unhandled exception.To subscribe to fault events from a Windows Workflow Foundation, enable tracking by adding a tracking participant.</span></span> <span data-ttu-id="0fc83-118">Skonfiguruj tego uczestnika przy użyciu profilu śledzenia, który wysyła zapytania o `ActivityStateQuery (state="Faulted")` , <xref:System.Activities.Tracking.FaultPropagationRecord> i `WorkflowInstanceQuery (state="UnhandledException")` .</span><span class="sxs-lookup"><span data-stu-id="0fc83-118">Configure this participant with a tracking profile that queries for `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>, and `WorkflowInstanceQuery (state="UnhandledException")`.</span></span>  
  
 <span data-ttu-id="0fc83-119">Jeśli śledzenie jest włączone przy użyciu uczestnika śledzenia funkcji ETW, zdarzenia błędów są emitowane do sesji ETW.</span><span class="sxs-lookup"><span data-stu-id="0fc83-119">If tracking is enabled using the ETW tracking participant, the fault events are emitted to an ETW session.</span></span> <span data-ttu-id="0fc83-120">Zdarzenia można wyświetlić za pomocą Podgląd zdarzeń Podgląd zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="0fc83-120">The events can be viewed using the Event Viewer event viewer.</span></span> <span data-ttu-id="0fc83-121">Można to znaleźć w węźle **Podgląd zdarzeń->Dzienniki aplikacji i usług — >Microsoft->Windows->Application Server-Applications** w kanale analitycznym.</span><span class="sxs-lookup"><span data-stu-id="0fc83-121">This can be found under the node **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications** in the analytic channel.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fc83-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0fc83-122">See also</span></span>

- <span data-ttu-id="0fc83-123">[Monitorowanie aplikacji sieci szkieletowej systemu Windows Server](/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="0fc83-123">[Windows Server App Fabric Monitoring](/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="0fc83-124">[Monitorowanie aplikacji przy użyciu sieci szkieletowej aplikacji](/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="0fc83-124">[Monitoring Applications with App Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
