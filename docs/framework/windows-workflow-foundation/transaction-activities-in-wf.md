---
title: Działania transakcji w WF
ms.date: 03/30/2017
ms.assetid: fb33378e-82c6-4ea0-870f-76dc77e7f0fe
ms.openlocfilehash: c40799f7f0456a13ab975a766a36e9425a2144df
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293341"
---
# <a name="transaction-activities-in-wf"></a>Działania transakcji w WF

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]Zawiera kilka działań dostarczonych przez system do modelowania transakcji, kompensacji i anulowania. Dzięki tym modelom programistycznym przepływ pracy będzie kontynuował postęp w przypadku zmian w logice biznesowej i obsłudze błędów. Aby uzyskać więcej informacji na temat transakcji, kompensacji i anulowania, zobacz [transakcje](workflow-transactions.md), [wynagrodzenie](compensation.md)i [Anulowanie](modeling-cancellation-behavior-in-workflows.md).  
  
## <a name="transaction-activities"></a>Działania transakcji  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|Kojarzy logikę anulowania w formie działania z główną ścieżką wykonywania, również wyrażoną jako działanie.|  
|<xref:System.Activities.Statements.CompensableActivity>|Obsługuje kompensację działań podrzędnych.|  
|<xref:System.Activities.Statements.Compensate>|Jawnie wywołuje procedurę obsługi kompensacji elementu <xref:System.Activities.Statements.CompensableActivity> .|  
|<xref:System.Activities.Statements.Confirm>|Jawnie wywołuje procedurę obsługi potwierdzenia elementu <xref:System.Activities.Statements.CompensableActivity> .|  
|<xref:System.Activities.Statements.TransactionScope>|Rozgranicza granicę transakcji.|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|Zakresy okresy istnienia transakcji inicjowanej przez odebraną wiadomość. Transakcja może zostać przepływana do przepływu pracy w komunikacie inicjującym lub utworzona przez dyspozytora po odebraniu wiadomości. **Uwaga:**  Znajduje się <xref:System.ServiceModel.Activities.TransactedReceiveScope> w sekcji **komunikaty** w **przyborniku**.|
