---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 3e4e1ff7ea8d8768c8d902dc09bd3b78646c2caf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256329"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="83ff8-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="83ff8-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>

<span data-ttu-id="83ff8-103">Usługa protokołu WS-AT nie może zarejestrować się w transakcji przy użyciu podanego kontekstu koordynacji.</span><span class="sxs-lookup"><span data-stu-id="83ff8-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="83ff8-104">Opis</span><span class="sxs-lookup"><span data-stu-id="83ff8-104">Description</span></span>  

 <span data-ttu-id="83ff8-105">Śledzone, gdy usługa MSDTC nie może zarejestrować się w transakcji dla danego protokołu 2PC.</span><span class="sxs-lookup"><span data-stu-id="83ff8-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="83ff8-106">Może się tak zdarzyć, ponieważ transakcja już nie istnieje, rejestracja nie jest już dozwolona lub zbyt wiele rejestracji już istnieje.</span><span class="sxs-lookup"><span data-stu-id="83ff8-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="83ff8-107">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="83ff8-107">Troubleshooting</span></span>  

 <span data-ttu-id="83ff8-108">Sprawdź ciąg stanu w komunikacie śledzenia, aby określić, czy istnieje jakikolwiek element możliwy do wykonania.</span><span class="sxs-lookup"><span data-stu-id="83ff8-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ff8-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="83ff8-109">See also</span></span>

- [<span data-ttu-id="83ff8-110">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="83ff8-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="83ff8-111">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="83ff8-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="83ff8-112">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="83ff8-112">Administration and Diagnostics</span></span>](../index.md)
