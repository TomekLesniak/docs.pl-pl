---
title: Zachowanie anulowania modelowania w przepływach pracy
ms.date: 03/30/2017
ms.assetid: d48f6cf3-cdde-4dd3-8265-a665acf32a03
ms.openlocfilehash: 157bff0d24b00f293fd551dd52fe693d36dfad61
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242061"
---
# <a name="modeling-cancellation-behavior-in-workflows"></a>Zachowanie anulowania modelowania w przepływach pracy

Działania mogą być anulowane w przepływie pracy, na przykład przez <xref:System.Activities.Statements.Parallel> działanie anulowania niekompletnych gałęzi <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> , gdy jego wynikiem jest wartość `true` lub spoza przepływu pracy, jeśli jest on wywoływany przez hosta <xref:System.Activities.WorkflowApplication.Cancel%2A> . Aby zapewnić obsługę anulowania, autorzy przepływu pracy mogą korzystać z <xref:System.Activities.Statements.CancellationScope> działania, <xref:System.Activities.Statements.CompensableActivity> działania lub tworzyć niestandardowe działania, które udostępniają logikę anulowania. Ten temat zawiera omówienie anulowania w przepływach pracy.  
  
## <a name="cancellation-compensation-and-transactions"></a>Anulowanie, kompensacja i transakcje  

 Transakcje umożliwiają aplikacji przerwanie (wycofywanie) wszystkich zmian wykonywanych w ramach transakcji w przypadku wystąpienia błędów występujących w ramach procesu transakcji. Jednak nie wszystkie zadania, które mogą wymagać anulowania lub cofania, są odpowiednie dla transakcji, takich jak długotrwałe działanie lub pracy, które nie obejmują zasobów transakcyjnych. Kompensacja zapewnia model wycofywania ukończonych wcześniej zadań nietransakcyjnych, jeśli wystąpi kolejny błąd w przepływie pracy. Anulowanie zapewnia model przepływu pracy i autorów działań do obsługi nietransakcyjnej pracy, która nie została ukończona. Jeśli działanie nie zakończyło wykonywania i zostało anulowane, jego logika anulowania zostanie wywołana, jeśli jest dostępna.  
  
> [!NOTE]
> Aby uzyskać więcej informacji na temat transakcji i kompensacji, zobacz [transakcje](workflow-transactions.md) i [kompensacja](compensation.md).  
  
## <a name="using-cancellationscope"></a>Używanie działania CancellationScope  

 <xref:System.Activities.Statements.CancellationScope>Działanie ma dwie sekcje, które mogą zawierać działania podrzędne: <xref:System.Activities.Statements.CancellationScope.Body%2A> i <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> . <xref:System.Activities.Statements.CancellationScope.Body%2A>Jest to miejsce, w którym są umieszczane działania wchodzące w skład logiki działania, a <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> to miejsce, w którym są umieszczane działania, które zapewniają logikę anulowania działania. Działanie można anulować tylko wtedy, gdy nie zostało ukończone. W przypadku <xref:System.Activities.Statements.CancellationScope> działania, uzupełnianie odnosi się do ukończenia działań w <xref:System.Activities.Statements.CancellationScope.Body%2A> . Jeśli zaplanowano żądanie anulowania, a działania w <xref:System.Activities.Statements.CancellationScope.Body%2A> nie zostały ukończone, <xref:System.Activities.Statements.CancellationScope> zostanie oznaczone jako <xref:System.Activities.ActivityInstanceState.Canceled> i <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> działania zostaną wykonane.  
  
### <a name="canceling-a-workflow-from-the-host"></a>Anulowanie przepływu pracy z hosta  

 Host może anulować przepływ pracy, wywołując <xref:System.Activities.WorkflowApplication.Cancel%2A> metodę <xref:System.Activities.WorkflowApplication> wystąpienia, które obsługuje przepływ pracy. W poniższym przykładzie jest tworzony przepływ pracy, który ma <xref:System.Activities.Statements.CancellationScope> . Przepływ pracy jest wywoływany, a następnie Host wykonuje wywołanie <xref:System.Activities.WorkflowApplication.Cancel%2A> . Główne wykonywanie przepływu pracy zostanie zatrzymane, <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> <xref:System.Activities.Statements.CancellationScope> zostanie wywołane, a następnie przepływ pracy zostanie ukończony ze stanem <xref:System.Activities.ActivityInstanceState.Canceled> .  
  
 [!code-csharp[CFX_WorkflowApplicationExample#35](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#35)]  
  
 Po wywołaniu tego przepływu pracy następujące dane wyjściowe są wyświetlane w konsoli programu.  
  
 **Uruchamianie przepływu pracy.**  
**CancellationHandler wywołana.** 
 **Anulowano przepływ pracy b30ebb30-df46-4d90-a211-e31c38d8db3c.**
> [!NOTE]
> Gdy <xref:System.Activities.Statements.CancellationScope> działanie zostało anulowane i <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> wywołane, odpowiada autorowi przepływu pracy, aby określić postęp anulowania działania anulowanego przed jego anulowaniem w celu zapewnienia odpowiedniej logiki anulowania. Nie <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> zawiera żadnych informacji o postępie anulowanych działań.  
  
 Przepływ pracy można również anulować z hosta, jeśli wystąpił nieobsługiwany wyjątek, który znajduje się poza katalogiem głównym przepływu pracy, a <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> procedura obsługi zwraca wartość <xref:System.Activities.UnhandledExceptionAction.Cancel> . W tym przykładzie przepływ pracy zostanie uruchomiony, a następnie wygeneruje <xref:System.ApplicationException> . Ten wyjątek jest nieobsługiwany przez przepływ pracy i dlatego <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> jest wywoływany program obsługi. Program obsługi instruuje środowisko uruchomieniowe, aby anulował przepływ pracy, a <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> aktualnie wykonywane <xref:System.Activities.Statements.CancellationScope> działanie jest wywoływane.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#36](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#36)]  
  
 Po wywołaniu tego przepływu pracy następujące dane wyjściowe są wyświetlane w konsoli programu.  
  
 **Uruchamianie przepływu pracy.**  
**OnUnhandledException w przepływie pracy 6bb2d5d6-f49a-4c6d-a988-478afb86dbe9** 
 **Zgłoszono wyjątek ApplicationException.** 
 **CancellationHandler wywołana.** 
 **Anulowano przepływ pracy 6bb2d5d6-f49a-4c6d-a988-478afb86dbe9.**

### <a name="canceling-an-activity-from-inside-a-workflow"></a>Anulowanie działania z wewnątrz przepływu pracy  

 Działanie może być również anulowane przez jego element nadrzędny. Jeśli na przykład <xref:System.Activities.Statements.Parallel> działanie ma wiele wykonanych gałęzi, a jego <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> wartość zostanie wyznaczona, `true` jego niekompletne gałęzie zostaną anulowane. W tym przykładzie <xref:System.Activities.Statements.Parallel> tworzone jest działanie, które ma dwie gałęzie. <xref:System.Activities.Statements.Parallel.CompletionCondition%2A>Jest ustawiona na tak, aby zakończyć `true` <xref:System.Activities.Statements.Parallel> działanie zaraz po zakończeniu jednego z jego gałęzi. W tym przykładzie rozgałęzienie 2 kończy działanie, a gałąź 1 została anulowana.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#37](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#37)]  
  
 Po wywołaniu tego przepływu pracy następujące dane wyjściowe są wyświetlane w konsoli programu.  
  
 **Początek gałęzi 1.**  
**Ukończono rozgałęzienie 2.** 
 **Anulowano rozgałęzienie 1.** 
 **Ukończono E0685e24-18ef-4a47-acf3-5c638732f3be przepływu pracy.**  Działania są również anulowane, jeśli wyjątek występuje w górę od elementu głównego działania, ale jest obsługiwany na wyższym poziomie w przepływie pracy. W tym przykładzie główna logika przepływu pracy składa się z <xref:System.Activities.Statements.Sequence> działania. <xref:System.Activities.Statements.Sequence>Jest określony jako działanie, <xref:System.Activities.Statements.CancellationScope.Body%2A> <xref:System.Activities.Statements.CancellationScope> które jest zawarte w <xref:System.Activities.Statements.TryCatch> działaniu. Wyjątek jest generowany z treści <xref:System.Activities.Statements.Sequence> , jest obsługiwany przez działanie nadrzędne <xref:System.Activities.Statements.TryCatch> i <xref:System.Activities.Statements.Sequence> jest anulowany.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#39](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#39)]  
  
 Po wywołaniu tego przepływu pracy następujące dane wyjściowe są wyświetlane w konsoli programu.  
  
 **Rozpoczynanie sekwencji.**  
**Anulowano sekwencję.** 
 **Przechwycono wyjątek.** 
 **Ukończono E3c18939-121e-4c43-af1c-ba1ce977ce55 przepływu pracy.**

### <a name="throwing-exceptions-from-a-cancellationhandler"></a>Zgłaszanie wyjątków z CancellationHandler  

 Wszystkie wyjątki zgłoszone z elementu <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> <xref:System.Activities.Statements.CancellationScope> są krytyczne dla przepływu pracy. Jeśli istnieje możliwość występowania wyjątków ucieczki z <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> , należy użyć instrukcji <xref:System.Activities.Statements.TryCatch> w <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> celu przechwycenia i obsłużenia tych wyjątków.  
  
### <a name="cancellation-using-compensableactivity"></a>Anulowanie przy użyciu działanie CompensableActivity  

 Podobnie jak w przypadku <xref:System.Activities.Statements.CancellationScope> działania, <xref:System.Activities.Statements.CompensableActivity> ma <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> . Jeśli element <xref:System.Activities.Statements.CompensableActivity> zostanie anulowany, wszystkie działania w nim <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> są wywoływane. Może to być przydatne do cofania pracy częściowo ukończonej kompensacyjne. Aby uzyskać informacje o sposobach korzystania z <xref:System.Activities.Statements.CompensableActivity> kompensacji i anulowania, zobacz [kompensacja](compensation.md).  
  
## <a name="cancellation-using-custom-activities"></a>Anulowanie przy użyciu działań niestandardowych  

 Autorzy działań niestandardowych mogą implementować logikę anulowania w swoich działaniach niestandardowych na kilka różnych sposobów. Działania niestandardowe, które pochodzą od <xref:System.Activities.Activity> mogą implementować logikę anulowania przez umieszczenie <xref:System.Activities.Statements.CancellationScope> lub inne niestandardowe działanie, które zawiera logikę anulowania w treści działania. <xref:System.Activities.AsyncCodeActivity> i <xref:System.Activities.NativeActivity> działania pochodne mogą przesłonić odpowiednią <xref:System.Activities.NativeActivity.Cancel%2A> metodę i zapewnić logikę anulowania. <xref:System.Activities.CodeActivity> działania pochodne nie zapewniają żadnych prowizji do anulowania, ponieważ cała ich praca odbywa się w ramach jednej serii wykonywania, gdy środowisko uruchomieniowe wywołuje <xref:System.Activities.CodeActivity.Execute%2A> metodę. Jeśli metoda EXECUTE nie została jeszcze wywołana <xref:System.Activities.CodeActivity> , a działanie na podstawie zostało anulowane, działanie zostanie zamknięte ze stanem <xref:System.Activities.ActivityInstanceState.Canceled> i <xref:System.Activities.CodeActivity.Execute%2A> Metoda nie jest wywoływana.  
  
### <a name="cancellation-using-nativeactivity"></a>Anulowanie przy użyciu natywnego  

 <xref:System.Activities.NativeActivity> działania pochodne mogą przesłonić <xref:System.Activities.NativeActivity.Cancel%2A> metodę, aby zapewnić niestandardową logikę anulowania. Jeśli ta metoda nie zostanie zastąpiona, zostanie zastosowana domyślna logika anulowania przepływu pracy. Domyślne anulowanie to proces, który występuje dla elementu <xref:System.Activities.NativeActivity> , który nie przesłania <xref:System.Activities.NativeActivity.Cancel%2A> metody lub którego <xref:System.Activities.NativeActivity.Cancel%2A> Metoda wywołuje metodę bazową <xref:System.Activities.NativeActivity> <xref:System.Activities.NativeActivity.Cancel%2A> . Gdy działanie zostanie anulowane, środowisko uruchomieniowe flaguje działanie anulowania i automatycznie obsługuje określone czyszczenie. Jeśli działanie zawiera tylko zakładki oczekujące, zakładki zostaną usunięte, a działanie zostanie oznaczone jako <xref:System.Activities.ActivityInstanceState.Canceled> . Wszystkie zaległe działania podrzędne anulowanego działania zostaną anulowane. Każda próba zaplanowania dodatkowych działań podrzędnych spowoduje zignorowanie próby, a działanie zostanie oznaczone jako <xref:System.Activities.ActivityInstanceState.Canceled> . Jeśli wszystkie zaległe działania podrzędne zostaną zakończone <xref:System.Activities.ActivityInstanceState.Canceled> w <xref:System.Activities.ActivityInstanceState.Faulted> stanie lub, działanie zostanie oznaczone jako <xref:System.Activities.ActivityInstanceState.Canceled> . Zwróć uwagę, że można zignorować żądanie anulowania. Jeśli działanie nie zawiera żadnych zaległych zakładek lub wykonuje działania podrzędne i nie planuje żadnych dodatkowych elementów roboczych po oflagowaniu do anulowania, zakończy się pomyślnie. To domyślne anulowanie jest wystarczające dla wielu scenariuszy, ale jeśli jest wymagana dodatkowa logika anulowania, można użyć wbudowanych działań anulowania lub działań niestandardowych.  
  
 W poniższym przykładzie <xref:System.Activities.NativeActivity.Cancel%2A> zdefiniowano przesłonięcie <xref:System.Activities.NativeActivity> działania niestandardowego opartego na elemencie `ParallelForEach` . Gdy działanie zostanie anulowane, to przesłonięcie obsługuje logikę anulowania działania. Ten przykład jest częścią [nieogólnego](./samples/non-generic-parallelforeach.md) przykładu ParallelForEach.  
  
```csharp  
protected override void Cancel(NativeActivityContext context)  
{  
    // If we do not have a completion condition then we can just  
    // use default logic.  
    if (this.CompletionCondition == null)  
    {  
        base.Cancel(context);  
    }  
    else  
    {  
        context.CancelChildren();  
    }  
}  
```  
  
 <xref:System.Activities.NativeActivity> działania pochodne mogą określić, czy żądanie anulowania zostało zażądane, sprawdzając <xref:System.Activities.NativeActivityContext.IsCancellationRequested%2A> Właściwość i Oznacz jako anulowane przez wywołanie <xref:System.Activities.NativeActivityContext.MarkCanceled%2A> metody. Wywołanie nie <xref:System.Activities.NativeActivityContext.MarkCanceled%2A> powoduje natychmiastowego wykonania działania. Jak zwykle, środowisko uruchomieniowe ukończy działanie, gdy nie będzie więcej zaległych zadań, ale jeśli <xref:System.Activities.NativeActivityContext.MarkCanceled%2A> jest wywoływana, <xref:System.Activities.ActivityInstanceState.Canceled> zamiast <xref:System.Activities.ActivityInstanceState.Closed> .  
  
### <a name="cancellation-using-asynccodeactivity"></a>Anulowanie przy użyciu metoda AsyncCodeActivity  

 <xref:System.Activities.AsyncCodeActivity> działania bazujące mogą również dostarczyć niestandardowe logike anulowania, zastępując <xref:System.Activities.AsyncCodeActivity.Cancel%2A> metodę. Jeśli ta metoda nie zostanie przesłonięta, obsługa anulowania nie zostanie wykonana, jeśli działanie zostało anulowane. W poniższym przykładzie <xref:System.Activities.AsyncCodeActivity.Cancel%2A> zdefiniowano przesłonięcie <xref:System.Activities.AsyncCodeActivity> działania niestandardowego opartego na elemencie `ExecutePowerShell` . Gdy działanie zostanie anulowane, wykonuje żądane zachowanie anulowania.
  
 [!code-csharp[CFX_WorkflowApplicationExample#1020](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#1020)]  
  
 <xref:System.Activities.AsyncCodeActivity> działania pochodne mogą określić, czy żądanie anulowania zostało zażądane, sprawdzając <xref:System.Activities.AsyncCodeActivityContext.IsCancellationRequested%2A> Właściwość i Oznacz jako anulowane przez wywołanie <xref:System.Activities.AsyncCodeActivityContext.MarkCanceled%2A> metody.
