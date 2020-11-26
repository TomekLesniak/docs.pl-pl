---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: bc2cdc2221ec522b44c36ef3320b77124d61850e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236705"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="3e132-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="3e132-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>

<span data-ttu-id="3e132-103">Przekroczono limit czasu usługi protokołu WS-AT podczas oczekiwania na odpowiedź na komunikat o wyniku z nietrwałego uczestnika.</span><span class="sxs-lookup"><span data-stu-id="3e132-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="3e132-104">Wynik transakcji może być wątpliwy, jeśli uczestnik zwróci wartość.</span><span class="sxs-lookup"><span data-stu-id="3e132-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3e132-105">Opis</span><span class="sxs-lookup"><span data-stu-id="3e132-105">Description</span></span>  

 <span data-ttu-id="3e132-106">Śledzenie, gdy uczestnik trwały zdecydował się zatwierdzić lub przerwać, ale nie odpowiedział na żądanie zatwierdzenia lub wycofania w określonym czasie.</span><span class="sxs-lookup"><span data-stu-id="3e132-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3e132-107">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="3e132-107">Troubleshooting</span></span>  

 <span data-ttu-id="3e132-108">Upewnij się, że wszyscy uczestnicy nietrwałe mogą reagować w danym czasie.</span><span class="sxs-lookup"><span data-stu-id="3e132-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="3e132-109">Domyślny okres to 180 sekund.</span><span class="sxs-lookup"><span data-stu-id="3e132-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="3e132-110">Jeśli jest to niewystarczające, należy zwiększyć `VolatileOutcomeDelay` zasady czasomierza dla usługi WS-AT.</span><span class="sxs-lookup"><span data-stu-id="3e132-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e132-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3e132-111">See also</span></span>

- [<span data-ttu-id="3e132-112">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="3e132-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="3e132-113">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="3e132-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3e132-114">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="3e132-114">Administration and Diagnostics</span></span>](../index.md)
