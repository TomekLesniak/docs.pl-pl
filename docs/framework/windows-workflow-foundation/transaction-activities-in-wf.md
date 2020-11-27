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
# <a name="transaction-activities-in-wf"></a><span data-ttu-id="904c9-102">Działania transakcji w WF</span><span class="sxs-lookup"><span data-stu-id="904c9-102">Transaction Activities in WF</span></span>

<span data-ttu-id="904c9-103">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]Zawiera kilka działań dostarczonych przez system do modelowania transakcji, kompensacji i anulowania.</span><span class="sxs-lookup"><span data-stu-id="904c9-103">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] has several system-provided activities for modeling transactions, compensation, and cancellation.</span></span> <span data-ttu-id="904c9-104">Dzięki tym modelom programistycznym przepływ pracy będzie kontynuował postęp w przypadku zmian w logice biznesowej i obsłudze błędów.</span><span class="sxs-lookup"><span data-stu-id="904c9-104">These programming models allow the workflow to continue forward progress in the event of changes in business logic and error handling.</span></span> <span data-ttu-id="904c9-105">Aby uzyskać więcej informacji na temat transakcji, kompensacji i anulowania, zobacz [transakcje](workflow-transactions.md), [wynagrodzenie](compensation.md)i [Anulowanie](modeling-cancellation-behavior-in-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="904c9-105">For more information about transactions, compensation, and cancellation, see [Transactions](workflow-transactions.md), [Compensation](compensation.md), and [Cancellation](modeling-cancellation-behavior-in-workflows.md).</span></span>  
  
## <a name="transaction-activities"></a><span data-ttu-id="904c9-106">Działania transakcji</span><span class="sxs-lookup"><span data-stu-id="904c9-106">Transaction Activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|<span data-ttu-id="904c9-107">Kojarzy logikę anulowania w formie działania z główną ścieżką wykonywania, również wyrażoną jako działanie.</span><span class="sxs-lookup"><span data-stu-id="904c9-107">Associates cancellation logic, in the form of an activity, with a main path of execution, also expressed as an activity.</span></span>|  
|<xref:System.Activities.Statements.CompensableActivity>|<span data-ttu-id="904c9-108">Obsługuje kompensację działań podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="904c9-108">Supports compensation of its child activities.</span></span>|  
|<xref:System.Activities.Statements.Compensate>|<span data-ttu-id="904c9-109">Jawnie wywołuje procedurę obsługi kompensacji elementu <xref:System.Activities.Statements.CompensableActivity> .</span><span class="sxs-lookup"><span data-stu-id="904c9-109">Explicitly invokes the compensation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.Confirm>|<span data-ttu-id="904c9-110">Jawnie wywołuje procedurę obsługi potwierdzenia elementu <xref:System.Activities.Statements.CompensableActivity> .</span><span class="sxs-lookup"><span data-stu-id="904c9-110">Explicitly invokes the confirmation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.TransactionScope>|<span data-ttu-id="904c9-111">Rozgranicza granicę transakcji.</span><span class="sxs-lookup"><span data-stu-id="904c9-111">Demarcates a transaction boundary.</span></span>|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|<span data-ttu-id="904c9-112">Zakresy okresy istnienia transakcji inicjowanej przez odebraną wiadomość.</span><span class="sxs-lookup"><span data-stu-id="904c9-112">Scopes the lifetime of a transaction that is initiated by a received message.</span></span> <span data-ttu-id="904c9-113">Transakcja może zostać przepływana do przepływu pracy w komunikacie inicjującym lub utworzona przez dyspozytora po odebraniu wiadomości.</span><span class="sxs-lookup"><span data-stu-id="904c9-113">The transaction may be flowed into the workflow on the initiating message, or created by the dispatcher when the message is received.</span></span> <span data-ttu-id="904c9-114">**Uwaga:**  Znajduje się <xref:System.ServiceModel.Activities.TransactedReceiveScope> w sekcji **komunikaty** w **przyborniku**.</span><span class="sxs-lookup"><span data-stu-id="904c9-114">**Note:**  The <xref:System.ServiceModel.Activities.TransactedReceiveScope> is located in the **Messaging** section of the **Toolbox**.</span></span>|
