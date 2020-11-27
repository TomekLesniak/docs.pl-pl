---
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.date: 03/30/2017
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
ms.openlocfilehash: d5ebe3e1ccce7a85073e2de19d915d116f709b2d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286971"
---
# <a name="microsofttransactionstransactionbridgepreparemessageretry"></a><span data-ttu-id="98e18-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span><span class="sxs-lookup"><span data-stu-id="98e18-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span></span>

<span data-ttu-id="98e18-103">Do uczestnika, który nie odpowiada, wysłano ponowną próbę komunikatu przygotowania.</span><span class="sxs-lookup"><span data-stu-id="98e18-103">A prepare message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="98e18-104">Opis</span><span class="sxs-lookup"><span data-stu-id="98e18-104">Description</span></span>  

 <span data-ttu-id="98e18-105">Śledzony, jeśli lokalny Menedżer transakcji jest wymagany do ponownego wysłania komunikatu przygotowania do uczestnika podrzędnego, ponieważ nie otrzymał odpowiedzi w danym czasie.</span><span class="sxs-lookup"><span data-stu-id="98e18-105">Traced if the local Transaction Manager needed to resend a Prepare message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="98e18-106">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="98e18-106">Troubleshooting</span></span>  

 <span data-ttu-id="98e18-107">Zbadaj potencjalne problemy z siecią lub produktem, które uniemożliwiają dostarczenie odpowiedzi na czas.</span><span class="sxs-lookup"><span data-stu-id="98e18-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="98e18-108">Jeśli jest widocznych wiele z tych komunikatów, może to oznaczać problemy z infrastrukturą lub czasy nietypowej odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="98e18-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="98e18-109">Oba problemy mogą znacząco zmniejszyć przepływność transakcji w ramach systemu.</span><span class="sxs-lookup"><span data-stu-id="98e18-109">Both issues can drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e18-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="98e18-110">See also</span></span>

- [<span data-ttu-id="98e18-111">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="98e18-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="98e18-112">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="98e18-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="98e18-113">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="98e18-113">Administration and Diagnostics</span></span>](../index.md)
