---
title: Wyjątki
ms.date: 03/30/2017
ms.assetid: 065205cc-52dd-4f30-9578-b17d8d113136
ms.openlocfilehash: 53cc8e3e27e131c5c2a9f8271851a0d8d7e0cbd7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280211"
---
# <a name="exceptions"></a>Wyjątki

Przepływy pracy mogą używać <xref:System.Activities.Statements.TryCatch> działania do obsługi wyjątków, które są wywoływane podczas wykonywania przepływu pracy. Te wyjątki mogą być obsługiwane lub mogą być ponownie zgłaszane przy użyciu <xref:System.Activities.Statements.Rethrow> działania. Działania w <xref:System.Activities.Statements.TryCatch.Finally%2A> sekcji są wykonywane <xref:System.Activities.Statements.TryCatch.Try%2A> , gdy sekcja lub <xref:System.Activities.Statements.TryCatch.Catches%2A> sekcja zostanie ukończona. Przepływy pracy hostowane przez <xref:System.Activities.WorkflowApplication> wystąpienie mogą również używać <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> programu obsługi zdarzeń do obsługi wyjątków, które nie są obsługiwane przez <xref:System.Activities.Statements.TryCatch> działanie.  
  
## <a name="causes-of-exceptions"></a>Przyczyny wyjątków  

 W przepływie pracy wyjątki mogą być generowane w następujący sposób:  
  
- Limit czasu transakcji w <xref:System.Activities.Statements.TransactionScope> .  
  
- Jawny wyjątek zgłoszony przez przepływ pracy przy użyciu <xref:System.Activities.Statements.Throw> działania.  
  
- [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]Zgłoszono wyjątek z działania.  
  
- Wyjątek zgłoszony przez kod zewnętrzny, taki jak biblioteki, składniki lub usługi, które są używane w przepływie pracy.  
  
## <a name="handling-exceptions"></a>Obsługa wyjątków  

 Jeśli wyjątek jest zgłaszany przez działanie i jest nieobsługiwany, domyślnym zachowaniem jest zakończenie wystąpienia przepływu pracy. Jeśli istnieje niestandardowa <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> obsługa, może ona zastąpić to zachowanie domyślne. Ta procedura obsługi umożliwia tworzenie przez hosta przepływu pracy odpowiedniej obsługi, takiej jak rejestrowanie niestandardowe, przerywanie przepływu pracy, Anulowanie przepływu pracy lub kończenie przepływu pracy.  Jeśli przepływ pracy zgłasza wyjątek, który nie jest obsługiwany, <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> zostanie wywołana procedura obsługi. Istnieją trzy możliwe akcje, które zostały zwrócone przez <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> określenie końcowego wyniku przepływu pracy.  
  
- **Anuluj** — anulowane wystąpienie przepływu pracy to bezpieczne zakończenie wykonywania gałęzi. Można modelować zachowanie anulowania (na przykład przy użyciu działania CancellationScope). Zakończona procedura obsługi jest wywoływana, gdy zakończy się proces anulowania. Anulowany przepływ pracy jest w stanie anulowania.  
  
- **Zakończenie** — nie można wznowić ani uruchomić przerwanego wystąpienia przepływu pracy.  Powoduje to wyzwolenie zdarzenia zakończonego, w którym można podać wyjątek jako powód przerwania. Zakończona procedura obsługi jest wywoływana po zakończeniu procesu kończenia. Przerwany przepływ pracy jest w stanie awarii.  
  
- **Przerwanie** — przerwane wystąpienia przepływu pracy można wznowić tylko wtedy, gdy zostało skonfigurowane jako trwałe.  Bez trwałości przepływ pracy nie może zostać wznowiony.  W momencie przerwania przepływu pracy wszystkie wykonane prace (w pamięci) od momentu ostatniego punktu trwałości zostaną utracone. W przypadku przerwanego przepływu pracy procedura obsługi przerwana jest wywoływana przy użyciu wyjątku jako przyczyny zakończenia procesu przerywania. Jednak, w przeciwieństwie do anulowanych i zakończonych, ukończona procedura obsługi nie zostanie wywołana. Przerwany przepływ pracy jest w stanie przerwania.  
  
 Poniższy przykład wywołuje przepływ pracy, który zgłasza wyjątek. Wyjątek jest nieobsługiwany przez przepływ pracy i <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> wywoływany jest program obsługi. <xref:System.Activities.WorkflowApplicationUnhandledExceptionEventArgs>Są one sprawdzane w celu podania informacji o wyjątku, a przepływ pracy zostaje zakończony.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#1)]  
  
### <a name="handling-exceptions-with-the-trycatch-activity"></a>Obsługa wyjątków przy użyciu działania TryCatch  

 Obsługa wyjątków w przepływie pracy odbywa się przy użyciu <xref:System.Activities.Statements.TryCatch> działania. <xref:System.Activities.Statements.TryCatch>Działanie zawiera <xref:System.Activities.Statements.TryCatch.Catches%2A> kolekcję <xref:System.Activities.Statements.Catch> działań, które są skojarzone z określonym <xref:System.Exception> typem. Jeśli wyjątek zgłoszony przez działanie zawarte w <xref:System.Activities.Statements.TryCatch.Try%2A> sekcji <xref:System.Activities.Statements.TryCatch> działania jest zgodny z wyjątkiem <xref:System.Activities.Statements.Catch%601> działania w <xref:System.Activities.Statements.TryCatch.Catches%2A> kolekcji, wyjątek jest obsługiwany. Jeśli wyjątek jest jawnie ponownie zgłaszany lub zostanie wygenerowany nowy wyjątek, ten wyjątek przekazuje działanie nadrzędne. Poniższy przykład kodu pokazuje <xref:System.Activities.Statements.TryCatch> działanie, które obsługuje zdarzenie <xref:System.ApplicationException> , które jest zgłaszane w <xref:System.Activities.Statements.TryCatch.Try%2A> sekcji przez <xref:System.Activities.Statements.Throw> działanie. Komunikat wyjątku jest zapisywana w konsoli przez <xref:System.Activities.Statements.Catch%601> działanie, a następnie jest zapisywana w konsoli w <xref:System.Activities.Statements.TryCatch.Finally%2A> sekcji.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#33](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#33)]  
  
 Działania w <xref:System.Activities.Statements.TryCatch.Finally%2A> sekcji są wykonywane, gdy <xref:System.Activities.Statements.TryCatch.Try%2A> sekcja lub <xref:System.Activities.Statements.TryCatch.Catches%2A> sekcja zostanie pomyślnie ukończona. <xref:System.Activities.Statements.TryCatch.Try%2A>Sekcja została zakończona pomyślnie, jeśli nie zgłoszono żadnych wyjątków, a <xref:System.Activities.Statements.TryCatch.Catches%2A> sekcja została pomyślnie ukończona, jeśli nie zostaną zgłoszone lub ponownie zgłoszone wyjątki. Jeśli wyjątek jest zgłaszany w <xref:System.Activities.Statements.TryCatch.Try%2A> sekcji a <xref:System.Activities.Statements.TryCatch> i nie jest obsługiwany przez <xref:System.Activities.Statements.Catch%601> w <xref:System.Activities.Statements.TryCatch.Catches%2A> sekcji lub jest ponownie zgłaszany z <xref:System.Activities.Statements.TryCatch.Catches%2A> , działania w ramach <xref:System.Activities.Statements.TryCatch.Finally%2A> nie zostaną wykonane, chyba że wystąpi jedno z poniższych.  
  
- Wyjątek jest przechwytywany przez działanie wyższego poziomu <xref:System.Activities.Statements.TryCatch> w przepływie pracy, niezależnie od tego, czy jest on ponownie zgłaszany na wyższym poziomie <xref:System.Activities.Statements.TryCatch> .  
  
- Wyjątek nie jest obsługiwany przez wyższy poziom <xref:System.Activities.Statements.TryCatch> , wyprowadza element główny przepływu pracy, a przepływ pracy jest skonfigurowany do anulowania, a nie przerwanie lub przerywanie. Przepływy pracy hostowane przy użyciu programu <xref:System.Activities.WorkflowApplication> mogą konfigurować je przez obsługę <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> i zwracanie <xref:System.Activities.UnhandledExceptionAction.Cancel> . Przykład obsługi <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> jest podany wcześniej w tym temacie. Usługi przepływu pracy można skonfigurować przy użyciu <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> i określania <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction.Cancel> . Przykład konfiguracji można znaleźć w <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> temacie [Rozszerzalność hosta usługi przepływu pracy](../wcf/feature-details/workflow-service-host-extensibility.md).  
  
## <a name="exception-handling-versus-compensation"></a>Obsługa wyjątków w porównaniu z wynagrodzeniem  

 Różnica między obsługą wyjątków a kompensacją polega na tym, że obsługa wyjątków odbywa się podczas wykonywania działania. Kompensacja występuje po pomyślnym ukończeniu działania. Obsługa wyjątków umożliwia wyczyszczenie, gdy działanie podnosi wyjątek, natomiast kompensacja zapewnia mechanizm, za pomocą którego pomyślnie ukończona pracy wykonanego wcześniej działania można cofnąć. Aby uzyskać więcej informacji, zobacz [kompensacja](compensation.md).  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Activities.Statements.TryCatch>
- <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>
- <xref:System.Activities.Statements.CompensableActivity>
