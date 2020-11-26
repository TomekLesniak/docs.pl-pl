---
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.date: 03/30/2017
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
ms.openlocfilehash: 23a0113488b1b1ef0bc161d4134b9325ef81406c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236718"
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a><span data-ttu-id="879f6-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span><span class="sxs-lookup"><span data-stu-id="879f6-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span></span>

<span data-ttu-id="879f6-103">Do koordynatora, który nie odpowiada, wysłano ponowną próbę komunikatu powtórzenia.</span><span class="sxs-lookup"><span data-stu-id="879f6-103">A replay message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="879f6-104">Opis</span><span class="sxs-lookup"><span data-stu-id="879f6-104">Description</span></span>  

 <span data-ttu-id="879f6-105">Śledzony, jeśli lokalny Menedżer transakcji jest wymagany do ponownego wysłania komunikatu powtarzania do koordynatora wyższego, ponieważ nie otrzymał odpowiedzi w danym czasie.</span><span class="sxs-lookup"><span data-stu-id="879f6-105">Traced if the local Transaction Manager needed to resend a Replay message to a superior coordinator because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="879f6-106">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="879f6-106">Troubleshooting</span></span>  

 <span data-ttu-id="879f6-107">Zbadaj potencjalne problemy z siecią lub produktem, które uniemożliwiają dostarczenie odpowiedzi na czas.</span><span class="sxs-lookup"><span data-stu-id="879f6-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="879f6-108">Jeśli jest widocznych wiele z tych komunikatów, może to oznaczać problemy z infrastrukturą lub czasy nietypowej odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="879f6-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="879f6-109">Oba problemy znacząco zmniejszają przepływność transakcji w ramach systemu.</span><span class="sxs-lookup"><span data-stu-id="879f6-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="879f6-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="879f6-110">See also</span></span>

- [<span data-ttu-id="879f6-111">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="879f6-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="879f6-112">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="879f6-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="879f6-113">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="879f6-113">Administration and Diagnostics</span></span>](../index.md)
