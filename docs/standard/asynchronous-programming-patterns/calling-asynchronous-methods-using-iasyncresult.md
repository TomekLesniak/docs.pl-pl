---
title: Wywołanie metod asynchronicznych za pomocą interfejsu IAsyncResult
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
ms.openlocfilehash: 8e11f734410e266aa4c175551e8a3fbf5d9236c9
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888909"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a><span data-ttu-id="915ee-102">Wywołanie metod asynchronicznych za pomocą interfejsu IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="915ee-102">Calling Asynchronous Methods Using IAsyncResult</span></span>

<span data-ttu-id="915ee-103">Typy w bibliotekach .NET i bibliotekach klas innych firm mogą zapewnić metody, które pozwalają aplikacji kontynuować wykonywanie podczas wykonywania operacji asynchronicznych w wątkach innych niż główny wątek aplikacji.</span><span class="sxs-lookup"><span data-stu-id="915ee-103">Types in the .NET libraries and third-party class libraries can provide methods that allow an application to continue executing while performing asynchronous operations in threads other than the main application thread.</span></span> <span data-ttu-id="915ee-104">W poniższych sekcjach opisano i przedstawiono przykłady kodu, które przedstawiają różne sposoby wywoływania metod asynchronicznych, które używają <xref:System.IAsyncResult> wzorca projektowego.</span><span class="sxs-lookup"><span data-stu-id="915ee-104">The following sections describe and provide code examples that demonstrate the different ways you can call asynchronous methods that use the <xref:System.IAsyncResult> design pattern.</span></span>  
  
- <span data-ttu-id="915ee-105">[Blokowanie wykonywania aplikacji przez zakończenie operacji asynchronicznej](blocking-application-execution-by-ending-an-async-operation.md).</span><span class="sxs-lookup"><span data-stu-id="915ee-105">[Blocking Application Execution by Ending an Async Operation](blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
- <span data-ttu-id="915ee-106">[Blokowanie wykonywania aplikacji przy użyciu AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="915ee-106">[Blocking Application Execution Using an AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
- <span data-ttu-id="915ee-107">[Sondowanie stanu operacji asynchronicznej](polling-for-the-status-of-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="915ee-107">[Polling for the Status of an Asynchronous Operation](polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
- <span data-ttu-id="915ee-108">[Użycie delegata AsyncCallback do zakończenia operacji asynchronicznej](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="915ee-108">[Using an AsyncCallback Delegate to End an Asynchronous Operation](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="915ee-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="915ee-109">See also</span></span>

- [<span data-ttu-id="915ee-110">Asynchroniczny wzorzec oparty na zdarzeniach (EAP)</span><span class="sxs-lookup"><span data-stu-id="915ee-110">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="915ee-111">Asynchroniczny wzorzec oparty na zdarzeniach — przegląd</span><span class="sxs-lookup"><span data-stu-id="915ee-111">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)
