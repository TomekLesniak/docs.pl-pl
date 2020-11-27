---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: 2d874cebe96b9caa99032e2881e19ec9cd34d047
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259014"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="e0dc9-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="e0dc9-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>

<span data-ttu-id="e0dc9-103">Komputer stanu dla rejestracji koordynatora przeszedł w stan zakończenia.</span><span class="sxs-lookup"><span data-stu-id="e0dc9-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e0dc9-104">Opis</span><span class="sxs-lookup"><span data-stu-id="e0dc9-104">Description</span></span>  

 <span data-ttu-id="e0dc9-105">Śledzenie, gdy lokalny Menedżer transakcji uważa, że funkcja rejestracji wyższej koordynatora zakończyła przetwarzanie 2PC.</span><span class="sxs-lookup"><span data-stu-id="e0dc9-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="e0dc9-106">Wynik rejestracji można zatwierdzić lub przerwać lub zazapominać.</span><span class="sxs-lookup"><span data-stu-id="e0dc9-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="e0dc9-107">Jest on także śledzony, jeśli lokalny Menedżer transakcji odnosi wartość ReadOnly podczas przygotowywania.</span><span class="sxs-lookup"><span data-stu-id="e0dc9-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0dc9-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e0dc9-108">See also</span></span>

- [<span data-ttu-id="e0dc9-109">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="e0dc9-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="e0dc9-110">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="e0dc9-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e0dc9-111">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="e0dc9-111">Administration and Diagnostics</span></span>](../index.md)
