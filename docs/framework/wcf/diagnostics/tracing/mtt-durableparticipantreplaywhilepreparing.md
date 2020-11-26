---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: bfa279887339f025e4cb7c9c455fd25098684073
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236614"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="0c2df-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="0c2df-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>

<span data-ttu-id="0c2df-103">Usługa protokołu WS-AT otrzymała komunikat powtarzania od trwałego uczestnika, który nie odpowiedział na przygotowanie.</span><span class="sxs-lookup"><span data-stu-id="0c2df-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="0c2df-104">W związku z tym transakcja została przerwana.</span><span class="sxs-lookup"><span data-stu-id="0c2df-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0c2df-105">Opis</span><span class="sxs-lookup"><span data-stu-id="0c2df-105">Description</span></span>  

 <span data-ttu-id="0c2df-106">Śledzone w przypadku odebrania komunikatu powtarzania, gdy trwały uczestnik nadal trwa przygotowywanie.</span><span class="sxs-lookup"><span data-stu-id="0c2df-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="0c2df-107">Jest to niedozwolony komunikat dla tego stanu i transakcja zostanie przerwana.</span><span class="sxs-lookup"><span data-stu-id="0c2df-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="0c2df-108">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="0c2df-108">Troubleshooting</span></span>

<span data-ttu-id="0c2df-109">Otrzymanie tego błędu może wskazywać, że trwały uczestnik (w tym podrzędny TransactionManagers) odzyskał sprawność po awarii; nie należy jednak pamiętać o wyniku transakcji i żądania jego stanu.</span><span class="sxs-lookup"><span data-stu-id="0c2df-109">Receiving this error can indicate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure; however, it is unsure of the transaction outcome and requests its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c2df-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0c2df-110">See also</span></span>

- [<span data-ttu-id="0c2df-111">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="0c2df-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="0c2df-112">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="0c2df-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="0c2df-113">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="0c2df-113">Administration and Diagnostics</span></span>](../index.md)
