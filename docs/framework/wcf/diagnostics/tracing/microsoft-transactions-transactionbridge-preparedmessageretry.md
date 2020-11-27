---
title: Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
ms.date: 03/30/2017
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
ms.openlocfilehash: edab153123ae48702811532df3b5b5bf0849c26a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275921"
---
# <a name="microsofttransactionstransactionbridgepreparedmessageretry"></a><span data-ttu-id="9931e-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span><span class="sxs-lookup"><span data-stu-id="9931e-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span></span>

<span data-ttu-id="9931e-103">Do koordynatora, który nie odpowiada, wysłano ponowną próbę komunikatu.</span><span class="sxs-lookup"><span data-stu-id="9931e-103">A prepared message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9931e-104">Opis</span><span class="sxs-lookup"><span data-stu-id="9931e-104">Description</span></span>  

 <span data-ttu-id="9931e-105">Śledzony, jeśli lokalny Menedżer transakcji jest wymagany do ponownego wysłania przygotowanego komunikatu do koordynatora wyższego, ponieważ nie otrzymał odpowiedzi w danym czasie/</span><span class="sxs-lookup"><span data-stu-id="9931e-105">Traced if the local Transaction Manager needed to resend a Prepared message to a superior coordinator because it did not receive a response in a given amount of time/</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="9931e-106">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="9931e-106">Troubleshooting</span></span>  

 <span data-ttu-id="9931e-107">Zbadaj potencjalne problemy z siecią lub produktem, które uniemożliwiają dostarczenie odpowiedzi na czas.</span><span class="sxs-lookup"><span data-stu-id="9931e-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="9931e-108">Jeśli jest widocznych wiele z tych komunikatów, może to oznaczać problemy z infrastrukturą lub czasy nietypowej odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="9931e-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="9931e-109">Oba problemy znacząco zmniejszają przepływność transakcji w ramach systemu.</span><span class="sxs-lookup"><span data-stu-id="9931e-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9931e-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9931e-110">See also</span></span>

- [<span data-ttu-id="9931e-111">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="9931e-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="9931e-112">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="9931e-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="9931e-113">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="9931e-113">Administration and Diagnostics</span></span>](../index.md)
