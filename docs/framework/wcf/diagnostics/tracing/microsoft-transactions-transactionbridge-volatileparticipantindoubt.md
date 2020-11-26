---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: 9ad9dc9fd078f7ad4c0934c8bf9bb73feb935014
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236653"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="82955-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="82955-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>

<span data-ttu-id="82955-103">Usługa protokołu WS-AT odebrała przygotowany lub powtarzający się komunikat od nierozpoznanego uczestnika trwałego.</span><span class="sxs-lookup"><span data-stu-id="82955-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="82955-104">Do uczestnika został zwrócony błąd, deklaruje, że wynik transakcji jest wątpliwy.</span><span class="sxs-lookup"><span data-stu-id="82955-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="82955-105">Opis</span><span class="sxs-lookup"><span data-stu-id="82955-105">Description</span></span>  

 <span data-ttu-id="82955-106">Śledzony, gdy lokalny Menedżer transakcji odbiera przygotowany lub powtarzający się komunikat z nietrwałej rejestracji, że już został zapomniany.</span><span class="sxs-lookup"><span data-stu-id="82955-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="82955-107">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="82955-107">Troubleshooting</span></span>  

 <span data-ttu-id="82955-108">Zbadaj potencjalne przyczyny późnych komunikatów pochodzących od uczestnika nietrwałego.</span><span class="sxs-lookup"><span data-stu-id="82955-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82955-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="82955-109">See also</span></span>

- [<span data-ttu-id="82955-110">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="82955-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="82955-111">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="82955-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="82955-112">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="82955-112">Administration and Diagnostics</span></span>](../index.md)
