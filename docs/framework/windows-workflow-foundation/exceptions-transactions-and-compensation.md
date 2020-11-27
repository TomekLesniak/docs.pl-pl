---
title: Wyjątki, transakcje i kompensacja
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
ms.openlocfilehash: 2d8574c0f0f6bd3f66214367c1ed15292adc24a9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280250"
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="b6f3b-102">Wyjątki, transakcje i kompensacja</span><span class="sxs-lookup"><span data-stu-id="b6f3b-102">Exceptions, Transactions, and Compensation</span></span>

[!INCLUDE[wf1](../../../includes/wf1-md.md)] <span data-ttu-id="b6f3b-103">Program udostępnia kilka różnych mechanizmów obsługi warunków błędów czasu wykonywania w przepływach pracy.</span><span class="sxs-lookup"><span data-stu-id="b6f3b-103">provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="b6f3b-104">Przepływy pracy mogą używać kombinacji obsługi wyjątków, transakcji, anulowania i kompensacji, aby bezpiecznie obsługiwać i odzyskiwać z warunków błędów.</span><span class="sxs-lookup"><span data-stu-id="b6f3b-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6f3b-105">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="b6f3b-105">In This Section</span></span>  

 [<span data-ttu-id="b6f3b-106">Wyjątki</span><span class="sxs-lookup"><span data-stu-id="b6f3b-106">Exceptions</span></span>](exceptions.md)  
 <span data-ttu-id="b6f3b-107">Pokazuje, jak używać <xref:System.Activities.Statements.TryCatch> działania do obsługi wyjątków w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="b6f3b-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="b6f3b-108">Transakcje</span><span class="sxs-lookup"><span data-stu-id="b6f3b-108">Transactions</span></span>](workflow-transactions.md)  
 <span data-ttu-id="b6f3b-109">Pokazuje, jak używać <xref:System.Activities.Statements.TransactionScope> działania do korzystania z transakcji w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="b6f3b-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="b6f3b-110">Kompensacja</span><span class="sxs-lookup"><span data-stu-id="b6f3b-110">Compensation</span></span>](compensation.md)  
 <span data-ttu-id="b6f3b-111">Opisuje kompensację przepływów pracy i pokazuje, jak używać działań związanych z kompensacją, takich jak <xref:System.Activities.Statements.CompensableActivity> , <xref:System.Activities.Statements.Compensate> i <xref:System.Activities.Statements.Confirm> .</span><span class="sxs-lookup"><span data-stu-id="b6f3b-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="b6f3b-112">Anulowanie</span><span class="sxs-lookup"><span data-stu-id="b6f3b-112">Cancellation</span></span>](modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="b6f3b-113">Opisuje, jak przeprowadzić obsługę anulowania w przepływach pracy przy użyciu wbudowanych działań, a także działań niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="b6f3b-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="b6f3b-114">Debugowanie przepływów pracy</span><span class="sxs-lookup"><span data-stu-id="b6f3b-114">Debugging Workflows</span></span>](debugging-workflows.md)  
 <span data-ttu-id="b6f3b-115">Opisuje sposób debugowania przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="b6f3b-115">Describes how to debug workflows.</span></span>
