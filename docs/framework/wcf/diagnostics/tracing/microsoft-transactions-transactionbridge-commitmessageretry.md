---
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.date: 03/30/2017
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
ms.openlocfilehash: 28b83b293570adf3b1cfdc15c77afd0f0cf768eb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259028"
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a><span data-ttu-id="479a1-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span><span class="sxs-lookup"><span data-stu-id="479a1-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span></span>

<span data-ttu-id="479a1-103">Do uczestnika, który nie odpowiada, wysłano ponowną próbę komunikatu zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="479a1-103">A commit message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="479a1-104">Opis</span><span class="sxs-lookup"><span data-stu-id="479a1-104">Description</span></span>  

 <span data-ttu-id="479a1-105">Śledzony, jeśli lokalny Menedżer transakcji jest wymagany do ponownego wysłania komunikatu zatwierdzenia do uczestnika podrzędnego, ponieważ nie otrzymał odpowiedzi w danym czasie.</span><span class="sxs-lookup"><span data-stu-id="479a1-105">Traced if the local Transaction Manager needed to resend a Commit message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="479a1-106">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="479a1-106">Troubleshooting</span></span>  

 <span data-ttu-id="479a1-107">Zbadaj potencjalne problemy z siecią lub produktem, które uniemożliwiają dostarczenie odpowiedzi na czas.</span><span class="sxs-lookup"><span data-stu-id="479a1-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="479a1-108">Jeśli jest widocznych wiele z tych komunikatów, może to oznaczać problemy z infrastrukturą lub czasy nietypowej odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="479a1-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="479a1-109">Oba problemy znacząco zmniejszają przepływność transakcji w ramach systemu.</span><span class="sxs-lookup"><span data-stu-id="479a1-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="479a1-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="479a1-110">See also</span></span>

- [<span data-ttu-id="479a1-111">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="479a1-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="479a1-112">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="479a1-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="479a1-113">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="479a1-113">Administration and Diagnostics</span></span>](../index.md)
