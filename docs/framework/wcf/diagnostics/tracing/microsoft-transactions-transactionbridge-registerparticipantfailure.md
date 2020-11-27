---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: 2f0198d3c288b4c3833cdac8e5f943ba822c22e9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252026"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="3f4ed-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="3f4ed-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>

<span data-ttu-id="3f4ed-103">Usługa protokołu WS-AT nie może zarejestrować uczestnika dla protokołu kontroli.</span><span class="sxs-lookup"><span data-stu-id="3f4ed-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3f4ed-104">Opis</span><span class="sxs-lookup"><span data-stu-id="3f4ed-104">Description</span></span>  

 <span data-ttu-id="3f4ed-105">Śledzone, jeśli usługa MSDTC wykryje Nieprawidłowe żądanie rejestracji.</span><span class="sxs-lookup"><span data-stu-id="3f4ed-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="3f4ed-106">Przyczyną może być wiele żądań rejestracji ukończenia i błędy wewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="3f4ed-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3f4ed-107">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="3f4ed-107">Troubleshooting</span></span>  

 <span data-ttu-id="3f4ed-108">Nie próbuj rejestrować się w celu ukończenia więcej niż raz.</span><span class="sxs-lookup"><span data-stu-id="3f4ed-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="3f4ed-109">Sprawdź również ciąg stanu w komunikacie śledzenia, aby określić, czy istnieje jakikolwiek element możliwy do wykonania.</span><span class="sxs-lookup"><span data-stu-id="3f4ed-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f4ed-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3f4ed-110">See also</span></span>

- [<span data-ttu-id="3f4ed-111">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="3f4ed-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="3f4ed-112">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="3f4ed-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3f4ed-113">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="3f4ed-113">Administration and Diagnostics</span></span>](../index.md)
